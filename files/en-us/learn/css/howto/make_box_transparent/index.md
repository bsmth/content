---
title: How to make a box semi-transparent
slug: Learn/CSS/Howto/Make_box_transparent
page-type: learn-faq
---

{{LearnSidebar}}

This guide will help you to understand the ways to make a box semi-transparent using CSS.

## Change the opacity of the box and content

If you would like the box and all of the contents of the box to change opacity, then the CSS {{cssxref("opacity")}} property is the tool to reach for. Opacity is the opposite of transparency; therefore `opacity: 1` is fully opaque—you will not see through the box at all.

Using a value of `0` would make the box completely transparent, and values between the two will change the opacity, with higher values giving less transparency.

## Changing the opacity of the background color only

In many cases you will only want to make the background color itself partly transparent, keeping the text and other elements fully opaque. To achieve this, use a [`<color>`](/en-US/docs/Web/CSS/color_value) value that has an alpha channel, such as `rgb()`. As with `opacity`, a value of `1` for the alpha channel value makes the color fully opaque. Therefore, `background-color: rgb(0 0 0 / 50%);` will set the background color to 50% opacity.

Try changing the opacity and alpha channel values in the below examples to see more or less of the background image behind the box.

```html live-sample___opacity
<div class="wrapper">
  <div class="box box1">This box uses opacity</div>
  <div class="box box2">
    This box has a background color with an alpha channel
  </div>
</div>
```

```css live-sample___opacity
.box1 {
  background-color: #000;
  color: #fff;
  opacity: 0.5;
}

.box2 {
  background-color: rgb(0 0 0 / 0.5);
  color: #fff;
}
```

{{EmbedLiveSample("opacity")}}

> [!NOTE]
> Take care that your text retains enough contrast with the background in cases where you are overlaying an image; otherwise you may make the content hard to read.

## See also

- [Applying color to HTML elements using CSS.](/en-US/docs/Web/CSS/CSS_colors/Applying_color)
