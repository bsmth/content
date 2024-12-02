---
title: "Reason: CORS disabled"
short-title: CORS disabled
slug: Web/HTTP/CORS/Errors/CORSDisabled
page-type: http-cors-error
---

{{HTTPSidebar}}

## Reason

```plain
Reason: CORS disabled
```

## What went wrong?

A request that needs to use [CORS](/en-US/docs/Web/HTTP/CORS) was attempted, but CORS is disabled in the user's browser.
When this happens, the user needs to turn CORS back on in their browser.

Browsers may allow you to change this via preferences (flags), such as `content.cors.disable` in Firefox where `true` disables CORS.

## See also

- [CORS errors](/en-US/docs/Web/HTTP/CORS/Errors)
- [CORS](/en-US/docs/Web/HTTP/CORS)
