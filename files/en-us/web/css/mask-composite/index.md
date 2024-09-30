---
title: mask-composite
slug: Web/CSS/mask-composite
page-type: css-property
browser-compat: css.properties.mask-composite
---

{{CSSRef}}

The **`mask-composite`** [CSS](/en-US/docs/Web/CSS) property represents a compositing operation used on the current mask layer with the mask layers below it.

## Syntax

```css
/* Keyword values */
mask-composite: add;
mask-composite: subtract;
mask-composite: intersect;
mask-composite: exclude;

/* Global values */
mask-composite: inherit;
mask-composite: initial;
mask-composite: revert;
mask-composite: revert-layer;
mask-composite: unset;
```

One or more of the keyword values listed below, separated by commas.

### Values

For the composition the current mask layer is referred to as _source_, while all layers below it are referred to as _destination_.

- `add`
  - : The source is placed over the destination.
- `subtract`
  - : The source is placed, where it falls outside of the destination.
- `intersect`
  - : The parts of source that overlap the destination, replace the destination.
- `exclude`
  - : The non-overlapping regions of source and destination are combined.

## Formal definition

{{cssinfo}}

## Formal syntax

{{csssyntax}}

## Examples

### Compositing mask layers with addition

```html live-sample___mask-composite
<div class="masked"></div>
```

```css live-sample___mask-composite
.masked {
  -webkit-mask-image: url(MDN.svg), url(star.svg);
  mask-image: url(MDN.svg), url(star.svg);
  -webkit-mask-size: 100% 100%;
  mask-size: 100% 100%;
  -webkit-mask-composite: source-over;
  mask-composite: add;
}
```

{{EmbedLiveSample("mask-composite")}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Clipping and Masking in CSS](https://css-tricks.com/clipping-masking-css/)
