---
title: <animateMotion>
slug: Web/SVG/Reference/Element/animateMotion
page-type: svg-element
browser-compat: svg.elements.animateMotion
sidebar: svgref
---

The **`<animateMotion>`** [SVG](/en-US/docs/Web/SVG) element provides a way to define how an element moves along a motion path.

> [!NOTE]
> To reuse an existing path, it will be necessary to use an {{SVGElement("mpath")}} element inside the `<animateMotion>` element instead of the {{SVGAttr("path")}} attribute.

## Usage context

{{svginfo}}

## Attributes

- {{SVGAttr("keyPoints")}}
  - : This attribute indicate, in the range \[0,1], how far is the object along the path for each {{SVGAttr("keyTimes")}} associated values.
    _Value type_: [**\<number>**](/en-US/docs/Web/SVG/Guides/Content_type#number)\*; _Default value_: none; _Animatable_: **no**
- {{SVGAttr("path")}}
  - : This attribute defines the path of the motion, using the same syntax as the {{SVGAttr('d')}} attribute.
    _Value type_: **\<string>**; _Default value_: none; _Animatable_: **no**
- {{SVGAttr("rotate")}}
  - : This attribute defines a rotation applied to the element animated along a path, usually to make it pointing in the direction of the animation.
    _Value type_: [**\<number>**](/en-US/docs/Web/SVG/Guides/Content_type#number) | `auto` | `auto-reverse`; _Default value_: `0`; _Animatable_: **no**

> [!NOTE]
> For `<animateMotion>`, the default value for the {{SVGAttr("calcMode")}} attribute is `paced`.

### Animation Attributes

- [Animation timing attributes](/en-US/docs/Web/SVG/Reference/Attribute#animation_timing_attributes)
  - : {{SVGAttr("begin")}}, {{SVGAttr("dur")}}, {{SVGAttr("end")}}, {{SVGAttr("min")}}, {{SVGAttr("max")}}, {{SVGAttr("restart")}}, {{SVGAttr("repeatCount")}}, {{SVGAttr("repeatDur")}}, {{SVGAttr("fill")}}
- [Animation value attributes](/en-US/docs/Web/SVG/Reference/Attribute#animation_value_attributes)
  - : {{SVGAttr("calcMode")}}, {{SVGAttr("values")}}, {{SVGAttr("keyTimes")}}, {{SVGAttr("keySplines")}}, {{SVGAttr("from")}}, {{SVGAttr("to")}}, {{SVGAttr("by")}}
- [Other Animation attributes](/en-US/docs/Web/SVG/Reference/Attribute#animation_attributes)
  - : Most notably: {{SVGAttr("attributeName")}}, {{SVGAttr("additive")}}, {{SVGAttr("accumulate")}}
- [Animation event attributes](/en-US/docs/Web/SVG/Reference/Attribute#event_attributes)
  - : Most notably: `onbegin`, `onend`, `onrepeat`

## DOM Interface

This element implements the {{domxref("SVGAnimateMotionElement")}} interface.

## Example

```css hidden
html,
body,
svg {
  height: 100%;
  margin: 0;
  padding: 0;
  display: block;
}
```

```html
<svg viewBox="0 0 200 100" xmlns="http://www.w3.org/2000/svg">
  <path
    fill="none"
    stroke="lightgrey"
    d="M20,50 C20,-50 180,150 180,50 C180-50 20,150 20,50 z" />

  <circle r="5" fill="red">
    <animateMotion
      dur="10s"
      repeatCount="indefinite"
      path="M20,50 C20,-50 180,150 180,50 C180-50 20,150 20,50 z" />
  </circle>
</svg>
```

{{EmbedLiveSample('Example', 150, '100%')}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{SVGElement("mpath")}}
