---
title: Connection management in HTTP/1.x
slug: Web/HTTP/Connection_management_in_HTTP_1.x
page-type: guide
---

{{HTTPSidebar}}

Connection management is a key topic in HTTP: opening and maintaining connections largely impacts the performance of websites and web applications.
In HTTP/1.x, there are several models: _short-lived connections_, _persistent connections_, and _HTTP pipelining._

HTTP relies on TCP for its transport protocol to provide a connection between the client and the server (until HTTP/3).
In its infancy, HTTP used a single model to handle such connections.
These connections were short-lived: a new TCP connection was created for each request and the TCP connection was closed once the answer had been received by the client.

This introduced a few problems because opening a TCP connection is a resource-consuming operation.
Modern web pages typically require a dozen or more request-response exchanges to be able to serve and render content.
Browsers typically allow 6 parallel TCP connections between the client and server, so parallel requests have to wait for previous ones to finish (head-of-line blocking).
Additionally, opening and closing a TCP connection for each HTTP exchange is very inefficient and results in significant latency and overhead.

To help solve these problems, two newer models were created in HTTP/1.1.
A persistent-connection model keeps connections opened between successive requests, meaning there are much fewer TCP connections opened between the client and server.
For head-of-line blocking, HTTP pipelining was introduces so that a browser could send several successive requests without waiting for any response to be received at all:

> [!NOTE]
> HTTP pipelining proved tricky to get right, and is not used very often due to the complexity it introduced.
> In HTTP/2, the inherent performance problems are mostly solved in the protocol level; so these models are not applicable.

![Compares the performance of the three HTTP/1.x connection models: short-lived connections, persistent connections, and HTTP pipelining.](http1_x_connections.png)

It's important to note that connection management in HTTP applies to the connection between two consecutive nodes, which is [hop-by-hop](/en-US/docs/Web/HTTP/Headers#hop-by-hop_headers) and not [end-to-end](/en-US/docs/Web/HTTP/Headers#end-to-end_headers). The model used in connections between a client and its first proxy may differ from the model between a proxy and the destination server (or any intermediate proxies). The HTTP headers involved in defining the connection model, like {{HTTPHeader("Connection")}} and {{HTTPHeader("Keep-Alive")}}, are [hop-by-hop](/en-US/docs/Web/HTTP/Headers#hop-by-hop_headers) headers with their values able to be changed by intermediary nodes.

A related topic is the concept of HTTP connection upgrades, wherein an HTTP/1.1 connection is upgraded to a different protocol, such as TLS/1.0, WebSocket, or even HTTP/2 in cleartext. This [protocol upgrade mechanism](/en-US/docs/Web/HTTP/Protocol_upgrade_mechanism) is documented in more detail elsewhere.

## Short-lived connections

The original model of HTTP, and the default one in HTTP/1.0, is _short-lived connections_. Each HTTP request is completed on its own connection; this means a TCP handshake happens before each HTTP request, and these are serialized.

The TCP handshake itself is time-consuming, but a TCP connection becomes more efficient with a sustained (or warm) connection due to a mechanism called slow start.
Short-lived connections do not make use of this efficiency feature of TCP, and performance degrades from optimum by choosing to transmit over a new, cold connection for each request/response.

This model is the default model used in HTTP/1.0 (if there is no {{HTTPHeader("Connection")}} header, or if its value is set to `close`).
In HTTP/1.1, short-lived connections are only used when the {{HTTPHeader("Connection")}} header is sent with a value of `close`.

> [!NOTE]
> Unless dealing with a very old system, which doesn't support a persistent connection, there is no compelling reason to use short-lived connections in HTTP/1.1.

## Persistent connections

Short-lived connections have two major inefficiencies: the time taken to establish a new connection is significant, and performance of the underlying TCP connection gets better only when this connection has been in use for some time (warm connection). To ease these problems, the concept of a _persistent connection_ (also known as a _keep-alive connection_) has been designed.

A persistent connection is one that remains open for a period of time, and can be reused for several requests, saving the need for a new TCP handshake, and utilizing TCP's performance capabilities on long-lived connections.
This connection will not stay open forever: idle connections are closed after some time (a server may use the {{HTTPHeader("Keep-Alive")}} header to specify a minimum time the connection should be kept open).

Persistent connections also have drawbacks; even when idling they consume server resources, and under heavy load, {{glossary("DoS attack", "DoS attacks")}} can be conducted. In such cases, using non-persistent connections, which are closed as soon as they are idle, can provide better performance.

HTTP/1.0 connections are not persistent by default. Setting {{HTTPHeader("Connection")}} to anything other than `close`, usually `retry-after`, will make them persistent.

In HTTP/1.1, persistence is the default, and the header is no longer needed (but it is often added as a defensive measure against cases requiring a fallback to HTTP/1.0).

## HTTP pipelining

> [!NOTE]
> HTTP pipelining is not activated by default in modern browsers:
>
> - Buggy {{glossary("Proxy_server", "proxies")}} are still common and these lead to strange and erratic behaviors that web developers cannot foresee and diagnose easily.
> - Pipelining is complex to implement correctly: the size of the resource being transferred, the effective {{glossary("Round_Trip_Time", "RTT")}} that will be used, as well as the effective bandwidth, have a direct incidence on the improvement provided by the pipeline. Without knowing these, important messages may be delayed behind unimportant ones. The notion of important even evolves during page layout! HTTP pipelining therefore brings a marginal improvement in most cases only.
> - Pipelining is subject to the [HOL](https://en.wikipedia.org/wiki/Head-of-line_blocking) problem.
>
> For these reasons, pipelining has been superseded by a better model, request _multiplexing_, that is used by HTTP/2.

In HTTP/1.X requests are issued sequentially.
The next request is issued once the response to the previous request has been received.
As they are affected by network latencies and bandwidth limitations, this can result in significant delay before the next request is _seen_ by the server.

Pipelining is the process to send successive requests over the same persistent connection without waiting for the answer.
Theoretically, performance could also be improved if two HTTP requests were to be packed into the same TCP message.
The typical [MSS](https://en.wikipedia.org/wiki/Maximum_segment_size) (Maximum Segment Size), is big enough to contain several simple requests, although the demand in size of HTTP requests continues to grow.

Not all types of HTTP requests can be pipelined: only {{glossary("idempotent")}} methods, that is {{HTTPMethod("GET")}}, {{HTTPMethod("HEAD")}}, {{HTTPMethod("PUT")}} and {{HTTPMethod("DELETE")}}, can be replayed safely. Should a failure happen, the pipeline content can be repeated.

Every HTTP/1.1-compliant proxy and server should support pipelining, although many have limitations in practice, which is mainly why no modern browser activates this feature by default.

## Domain sharding

> [!NOTE]
> Unless you have a very specific immediate need, don't use this deprecated technique; switch to HTTP/2 instead. In HTTP/2, domain sharding is no longer useful: the HTTP/2 connection is able to handle parallel unprioritized requests very well. Domain sharding is even detrimental to performance. Most HTTP/2 implementations use a technique called [connection coalescing](https://daniel.haxx.se/blog/2016/08/18/http2-connection-coalescing/) to revert eventual domain sharding.

As an HTTP/1.x connection is serializing requests, even without any ordering, it can't be optimal without large enough available bandwidth. As a solution, browsers open several connections to each domain, sending parallel requests. Default was once 2 to 3 connections, but this has now increased to a more common use of 6 parallel connections. There is a risk of triggering [DoS](/en-US/docs/Glossary/DOS_attack) protection on the server side if attempting more than this number.

If the server wishes a faster website or application response, it is possible for the server to force the opening of more connections. For example, instead of having all resources on the same domain, say `www.example.com`, it could split over several domains, `www1.example.com`, `www2.example.com`, `www3.example.com`. Each of these domains resolves to the _same_ server, and the web browser will open 6 connections to each (in our example, boosting the connections to 18). This technique is called _domain sharding_.

![Without domain sharding, a client requests six images from a domain with a maximum of two requests taking place in parallel. With domain sharding, the images are available from two domains and the client can run four requests in parallel, downloading the images in less time.](httpsharding.png)

## Conclusion

TCP connection management allows for better performance in HTTP.
HTTP/1.1 uses a persistent connection model by default, which leads to better performance when the number of requests increases.
The failure of HTTP pipelining as a practical solution to head-of-line blocking has lead to designing superior connection management models, which have been incorporated directly into HTTP/2.
Domain sharding was another technique to increase the amount of parallel connections a browser could maintain to a website.
This also proved tricky to implement, and can actually degrade performance under certain circumstances.

HTTP/2 uses a mechanism called request multiplexing, which allows a browser to combine and interleave multiple HTTP requests and responses on the same TCP connection.
This solves the head-of-line blocking problem on the protocol level, leading to better performance and user experience.
When it comes to tuning connection performance, the downsides and complexities of domain sharding and pipelining are usually overshadowed by switching protocols from HTTP/1.1 to HTTP/2 or above.
