---
title: "OfflineAudioContext: complete event"
short-title: complete
slug: Web/API/OfflineAudioContext/complete_event
page-type: web-api-event
browser-compat: api.OfflineAudioContext.complete_event
---

{{APIRef("Web Audio API")}}

The `complete` event of the {{domxref("OfflineAudioContext")}} interface is fired when the rendering of an offline audio context is complete.

This event is not cancelable and does not bubble.

## Syntax

Use the event name in methods like {{domxref("EventTarget.addEventListener", "addEventListener()")}}, or set an event handler property.

```js-nolint
addEventListener("complete", (event) => { })

oncomplete = (event) => { }
```

## Event type

An {{domxref("OfflineAudioCompletionEvent")}}. Inherits from {{domxref("Event")}}.

{{InheritanceDiagram("OfflineAudioCompletionEvent")}}

## Event properties

_Also inherits properties from its parent, {{domxref("Event")}}_.

- {{domxref("OfflineAudioCompletionEvent.renderedBuffer")}} {{ReadOnlyInline}}
  - : An {{domxref("AudioBuffer")}} containing the result of processing an {{domxref("OfflineAudioContext")}}.

## Examples

When processing is complete, you might want to use the `complete` event handler to prompt the user that the audio can now be played, and enable the play button:

```js
const offlineAudioCtx = new OfflineAudioContext();

offlineAudioCtx.addEventListener("complete", () => {
  console.log("Offline audio processing now complete");
  alert("Song processed and ready to play");
  playBtn.disabled = false;
});
```

You can also set up the event handler using the `oncomplete` property:

```js
const offlineAudioCtx = new OfflineAudioContext();

offlineAudioCtx.oncomplete = () => {
  console.log("Offline audio processing now complete");
  alert("Song processed and ready to play");
  playBtn.disabled = false;
};
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Web Audio API](/en-US/docs/Web/API/Web_Audio_API)
