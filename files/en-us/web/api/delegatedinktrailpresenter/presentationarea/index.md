---
title: "DelegatedInkTrailPresenter: presentationArea property"
short-title: presentationArea
slug: Web/API/DelegatedInkTrailPresenter/presentationArea
page-type: web-api-instance-property
status:
  - experimental
browser-compat: api.DelegatedInkTrailPresenter.presentationArea
---

{{APIRef("Ink API")}}{{SeeCompatTable}}

The **`presentationArea`** read-only property of the {{domxref("DelegatedInkTrailPresenter")}} interface returns the {{domxref("Element")}} inside which rendering of ink strokes is confined.

If the preceding {{domxref("Ink.requestPresenter", "Ink.requestPresenter()")}} method call included a specific `presentationArea` element definition, then that will be the element returned. Otherwise, the default is returned, which is the containing viewport.

This area is always the client coordinates for the element's border box, so moving the element or scrolling the element requires no recalculation on the developer's part.

### Value

An {{domxref("Element")}}.

## Example

```js
async function inkInit() {
  const ink = navigator.ink;
  const presenter = await ink.requestPresenter({ presentationArea: canvas });
  console.log(presenter.presentationArea);

  // …
}
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
