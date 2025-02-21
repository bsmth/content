---
title: "HTMLDialogElement: close event"
short-title: close
slug: Web/API/HTMLDialogElement/close_event
page-type: web-api-event
browser-compat: api.HTMLDialogElement.close_event
---

{{APIRef}}

The `close` event is fired on an `HTMLDialogElement` object when the {{htmlelement("dialog")}} it represents has been closed.

This event is not cancelable and does not bubble.

## Syntax

Use the event name in methods like {{domxref("EventTarget.addEventListener", "addEventListener()")}}, or set an event handler property.

```js
addEventListener("close", (event) => {});

onclose = (event) => {};
```

## Event type

A generic {{domxref("Event")}}.

## Examples

### Closing a dialog

```html live-sample___close-dialog
<dialog class="example-dialog">
  <form method="dialog">
    <button>Close via method="dialog"</button>
  </form>
  <button class="close">Close via .close() method</button>
  <p>Or hit the <kbd>Esc</kbd> key</p>
</dialog>

<button class="open-dialog">Open dialog</button>

<div class="result"></div>
```

```css hidden live-sample___close-dialog
body {
  font: 1.2rem sans-serif;
}
button,
div {
  margin: 0.5rem;
}
```

```js live-sample___close-dialog
const result = document.querySelector(".result");

const dialog = document.querySelector(".example-dialog");
dialog.addEventListener("close", (event) => {
  result.textContent = "Dialog was closed";
});

const openDialog = document.querySelector(".open-dialog");
openDialog.addEventListener("click", () => {
  dialog.showModal();
  result.textContent = "";
});

const closeButton = document.querySelector(".close");
closeButton.addEventListener("click", () => {
  dialog.close();
});
```

{{EmbedLiveSample('close-dialog', , '300', , , , , 'allow-forms')}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- HTML [`<dialog>`](/en-US/docs/Web/HTML/Element/dialog) element
- The [`Event`](/en-US/docs/Web/API/Event) interface
