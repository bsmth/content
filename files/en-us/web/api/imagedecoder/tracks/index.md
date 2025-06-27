---
title: "ImageDecoder: tracks property"
short-title: tracks
slug: Web/API/ImageDecoder/tracks
page-type: web-api-instance-property
browser-compat: api.ImageDecoder.tracks
sidebar:
  - apiref:
      - WebCodecs API")}}{{AvailableInWorkers("window_and_dedicated
---

{{securecontext_header}}

The **`tracks`** read-only property of the {{domxref("ImageDecoder")}} interface returns a list of the tracks in the encoded image data.

## Value

An {{domxref("ImageTrackList")}}.

## Examples

The following example prints the value of `tracks` to the console. This will be an {{domxref("ImageTrackList")}} object.

```js
console.log(imageDecoder.tracks);
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
