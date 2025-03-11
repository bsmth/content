---
title: "Reason: CORS request external redirect not allowed"
short-title: External redirect not allowed
slug: Web/HTTP/Guides/CORS/Errors/CORSExternalRedirectNotAllowed
page-type: http-cors-error
---

{{HTTPSidebar}}

The {{Glossary("CORS")}} request was responded to by the server with an HTTP redirect to a URL on a different origin than the original request, which is not permitted during CORS requests.

## CORS error reason

```plain
Reason: CORS request external redirect not allowed
```

## Fixing 'CORS request external redirect not allowed' error

For example, if the page `https://service.tld/fetchdata` were requested, and
the HTTP response is "301 Moved Permanently", "307 Temporary Redirect", or "308
Permanent Redirect" with a `Location` of
`https://anotherservice.net/getdata`, the CORS request will fail in this
manner.

To fix the problem, update your code to use the new URL as reported by the redirect,
thereby avoiding the redirect.

## See also

- [CORS errors](/en-US/docs/Web/HTTP/Guides/CORS/Errors)
- Glossary: {{Glossary("CORS")}}
- [CORS introduction](/en-US/docs/Web/HTTP/Guides/CORS)
