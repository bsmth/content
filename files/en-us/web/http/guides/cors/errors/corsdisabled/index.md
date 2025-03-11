---
title: "Reason: CORS disabled"
short-title: CORS is disabled
slug: Web/HTTP/Guides/CORS/Errors/CORSDisabled
page-type: http-cors-error
---

{{HTTPSidebar}}

A request that needs to use {{Glossary("CORS")}} was attempted, but CORS is disabled in the user's browser.

## CORS error reason

```plain
Reason: CORS disabled
```

## Fixing 'CORS disabled' error

The user needs to turn CORS back on in their browser.

In Firefox, for example, the preference that disables CORS is `content.cors.disable`.
Setting this to `true` disables CORS, so whenever that's the case, CORS requests will always fail with this error.

## See also

- [CORS errors](/en-US/docs/Web/HTTP/Guides/CORS/Errors)
- Glossary: {{Glossary("CORS")}}
- [CORS introduction](/en-US/docs/Web/HTTP/Guides/CORS)
