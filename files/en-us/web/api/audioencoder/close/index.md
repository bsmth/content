---
title: "AudioEncoder: close() method"
short-title: close()
slug: Web/API/AudioEncoder/close
page-type: web-api-instance-method
browser-compat: api.AudioEncoder.close
sidebar:
  - apiref:
      - WebCodecs API
---

{{AvailableInWorkers("window_and_dedicated")}}{{securecontext_header}}

The **`close()`** method of the {{domxref("AudioEncoder")}} interface ends all pending work and releases system resources.

## Syntax

```js-nolint
close()
```

### Parameters

None.

### Return value

None ({{jsxref("undefined")}}).

## Examples

The following example closes the `AudioEncoder`.

```js
AudioEncoder.close();
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
