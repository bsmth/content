---
title: "Reason: Multiple CORS header 'Access-Control-Allow-Origin' not allowed"
short-title: Multiple 'Access-Control-Allow-Origin' headers
slug: Web/HTTP/Guides/CORS/Errors/CORSMultipleAllowOriginNotAllowed
page-type: http-cors-error
---

{{HTTPSidebar}}

More than one {{HTTPHeader("Access-Control-Allow-Origin")}} header was sent by the server.

## CORS error reason

```plain
Reason: Multiple CORS header 'Access-Control-Allow-Origin' not allowed
```

## Fixing 'Multiple `Access-Control-Allow-Origin` not allowed' error

If you have access to the server you can change your implementation to echo back an
origin in the `Access-Control-Allow-Origin` header. You cannot send back a
list of origins, because browsers only accept a value that is either a single origin or
null

## See also

- [CORS errors](/en-US/docs/Web/HTTP/Guides/CORS/Errors)
- Glossary: {{Glossary("CORS")}}
- [CORS introduction](/en-US/docs/Web/HTTP/Guides/CORS)
- [Enable CORS: I want to add CORS support to my server](https://enable-cors.org/server.html)
