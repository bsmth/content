---
title: "HTMLFormControlsCollection: namedItem() method"
short-title: namedItem()
slug: Web/API/HTMLFormControlsCollection/namedItem
page-type: web-api-instance-method
browser-compat: api.HTMLFormControlsCollection.namedItem
---

{{APIRef("HTML DOM")}}

The **`HTMLFormControlsCollection.namedItem()`** method returns
the {{domxref("RadioNodeList")}} or the {{domxref("Element")}} in the collection whose
`name` or `id` match the specified name, or `null` if
no node matches.

Note that this version of `namedItem()` hides the one inherited from
{{domxref("HTMLCollection")}}. Like that one, in JavaScript, using the array bracket
syntax with a {{jsxref("String")}}, like `collection["value"]` is
equivalent to `collection.namedItem("value")`.

## Syntax

```js-nolint
namedItem(name)
[name]
```

### Parameters

- `name`
  - : A string which will be used to match against the `name` or `id` attributes of the controls in this `HTMLFormControlsCollection` object.

### Return value

- A {{domxref("RadioNodeList")}}, {{domxref("Element")}}, or [`null`](/en-US/docs/Web/JavaScript/Reference/Operators/null).

## Examples

### Using `namedItem()`

```html live-sample___named-item
<form>
  <label for="notes">Notes:</label>
  <input id="notes" name="my-form-control" type="text" />
</form>
<pre id="output"></pre>
```

```js live-sample___named-item
const form = document.querySelector("form");
const firstItem = form.elements.namedItem("my-form-control");
const output = document.querySelector("#output");

output.textContent = `My item: ${firstItem.id}`;

form.addEventListener("submit", (event) => {
  event.preventDefault();
  location.reload();
});
```

{{EmbedLiveSample('named-item', , , , , , , 'allow-forms')}}

### `namedItem()` vs. `.elements`

To get all items with the same name, access it like a property:

```html live-sample___named-item-elements
<form action="" method="POST">
  <label for="notes">Notes:</label>
  <input id="notes" name="my-form-control" type="text" />
  <label for="start">Start date:</label>
  <input id="start" name="my-form-control" type="date" />
</form>
<pre id="output"></pre>
```

```js live-sample___named-item-elements
const form = document.querySelector("form");
const allItems = form.elements["my-form-control"];
const output = document.querySelector("#output");

const itemIDs = Array.from(allItems)
  .map((item) => `"${item.id}"`)
  .join(", ");

output.textContent = `My items: ${itemIDs}`;

form.addEventListener("submit", (event) => {
  event.preventDefault();
  location.reload();
});
```

{{EmbedLiveSample('named-item-elements', , , , , , , 'allow-forms')}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{domxref("HTMLCollection.namedItem")}} that it replaces
