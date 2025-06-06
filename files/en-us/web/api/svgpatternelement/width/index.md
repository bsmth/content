---
title: "SVGPatternElement: width property"
short-title: width
slug: Web/API/SVGPatternElement/width
page-type: web-api-instance-property
browser-compat: api.SVGPatternElement.width
---

{{APIRef("SVG")}}

The **`width`** read-only property of the {{domxref("SVGPatternElement")}} interface describes the width of the pattern as an {{domxref("SVGAnimatedLength")}}. It reflects the computed value of the {{SVGAttr("width")}} attribute on the {{SVGElement("pattern")}} element.

The attribute value can be a [`<length>`](/en-US/docs/Web/SVG/Guides/Content_type#length), [`<percentage>`](/en-US/docs/Web/SVG/Guides/Content_type#percentage), or [`<number>`](/en-US/docs/Web/SVG/Guides/Content_type#number). The numeric value of the {{domxref("SVGAnimatedLength.baseVal")}} represents the width of the pattern in the user coordinate system.

## Value

An {{domxref("SVGAnimatedLength")}}.

## Example

Given the following SVG:

```html
<svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <!-- First pattern -->
    <pattern
      id="pattern1"
      x="50"
      height="20"
      width="20"
      patternUnits="userSpaceOnUse">
      <circle cx="10" cy="10" r="10" fill="blue" />
    </pattern>
    <!-- Second pattern -->
    <pattern
      id="pattern2"
      x="100"
      height="40"
      width="40"
      patternUnits="userSpaceOnUse">
      <circle cx="20" cy="20" r="10" fill="red" />
    </pattern>
  </defs>
  <!-- Using the patterns -->
  <rect x="0" y="0" width="100" height="100" fill="url(#pattern1)" />
  <rect x="100" y="0" width="100" height="100" fill="url(#pattern2)" />
</svg>
```

We can access the computed values of the `x` attributes:

```js
const patterns = document.querySelectorAll("pattern");

console.log(patterns[0].width.baseVal.value); // output: 20
console.log(patterns[1].width.baseVal.value); // output: 40
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{domxref("SVGPatternElement.height")}}
- {{domxref("SVGAnimatedLength.baseVal")}}
