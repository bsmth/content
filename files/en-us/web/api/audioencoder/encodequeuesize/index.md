---
title: "AudioEncoder: encodeQueueSize property"
short-title: encodeQueueSize
slug: Web/API/AudioEncoder/encodeQueueSize
page-type: web-api-instance-property
browser-compat: api.AudioEncoder.encodeQueueSize
sidebar:
  - apiref:
      - WebCodecs API")}}{{AvailableInWorkers("window_and_dedicated
---

{{securecontext_header}}

The **`encodeQueueSize`** read-only property of the {{domxref("AudioEncoder")}} interface returns the number of pending encode requests in the queue.

## Value

An integer containing the number of requests.

## Examples

The following example prints the size of the queue to the console.

```js
console.log(AudioEncoder.encodeQueueSize);
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
