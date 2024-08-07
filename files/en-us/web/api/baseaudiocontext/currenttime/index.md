---
title: "BaseAudioContext: currentTime property"
short-title: currentTime
slug: Web/API/BaseAudioContext/currentTime
page-type: web-api-instance-property
browser-compat: api.BaseAudioContext.currentTime
---

{{ APIRef("Web Audio API") }}

The `currentTime` read-only property of the {{ domxref("BaseAudioContext") }}
interface returns a double representing an ever-increasing hardware timestamp in seconds that
can be used for scheduling audio playback, visualizing timelines, etc. It starts at 0.

## Value

A floating point number.

## Examples

```js
const audioCtx = new AudioContext();
// Older webkit/blink browsers require a prefix

// …

console.log(audioCtx.currentTime);
```

## Reduced time precision

To offer protection against timing attacks and [fingerprinting](/en-US/docs/Glossary/Fingerprinting), the precision of `audioCtx.currentTime` might get rounded depending on browser settings. In Firefox, the `privacy.reduceTimerPrecision` preference is enabled by default and defaults to 2ms. You can also enable `privacy.resistFingerprinting`, in which case the precision will be 100ms or the value of `privacy.resistFingerprinting.reduceTimerPrecision.microseconds`, whichever is larger.

For example, with reduced time precision, the result of `audioCtx.currentTime` will always be a multiple of 0.002, or a multiple of 0.1 (or `privacy.resistFingerprinting.reduceTimerPrecision.microseconds`) with `privacy.resistFingerprinting` enabled.

```js
// reduced time precision (2ms) in Firefox 60
audioCtx.currentTime;
// Might be:
// 23.404
// 24.192
// 25.514
// …

// reduced time precision with `privacy.resistFingerprinting` enabled
audioCtx.currentTime;
// Might be:
// 49.8
// 50.6
// 51.7
// …
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Using Web Audio API](/en-US/docs/Web/API/Web_Audio_API/Using_Web_Audio_API)
