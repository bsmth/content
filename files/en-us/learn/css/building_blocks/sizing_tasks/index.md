---
title: "Test your skills: Sizing"
slug: Learn/CSS/Building_blocks/Sizing_tasks
page-type: learn-module-assessment
---

{{LearnSidebar}}

The aim of this skill test is to assess whether you understand the different ways of [sizing items in CSS](/en-US/docs/Learn/CSS/Building_blocks/Sizing_items_in_CSS).

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Task 1

In this task, you have two boxes. The first should be sized so that the height will be at least 100 pixels tall, even if there is less content that would cause it to grow to that height. However, the content should not overflow if there is more content than fits in 100 pixels. Test this box by removing the content from the HTML to make sure you still get a 100 pixel tall box even with no content.

The second box should be fixed at 100 pixels tall, so that content will overflow if there is too much.

![Two boxes one with overflowing content](mdn-sizing-height-min-height.png)

Try updating the live code below to recreate the finished example:

```html live-sample___height-min-height
<div class="box box1">
  <p>
    Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion
    daikon amaranth tatsoi tomatillo melon azuki bean garlic. Gumbo beet greens
    corn soko endive gumbo gourd.
  </p>
</div>

<div class="box box2">
  <p>
    Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion
    daikon amaranth tatsoi tomatillo melon azuki bean garlic. Gumbo beet greens
    corn soko endive gumbo gourd.
  </p>
</div>
```

```css live-sample___height-min-height
.box1 {
}

.box2 {
}
```

{{EmbedLiveSample("height-min-height")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/sizing/height-min-height-download.html) to work in your own editor or in an online editor.

## Task 2

In this task, you have a box, which contains another box. Your task is to make the inner box 60% of the width of the outer box. The value of the {{cssxref("box-sizing")}} property is set to `border-box`, which means that the total width includes any padding and border. You should also give the inner box padding of 10% using the width (or inline size) as the size from which that percentage is calculated.

Your final result should look like the image below:

![A box with another box nested inside](mdn-sizing-percentages.png)

Try updating the live code below to recreate the finished example:

```html live-sample___percentages
<div class="box">
  <div class="inner">Make me 60% of my parent's width.</div>
</div>
```

```css live-sample___percentages
* {
  box-sizing: border-box;
}
.inner {
}
```

{{EmbedLiveSample("percentages")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/sizing/percentages-download.html) to work in your own editor or in an online editor.

## Task 3

In this task, you have two images in boxes. One image is smaller than the box, the other is larger and breaking out of the box. If you imagine that the box is responsive and therefore could grow and shrink, which property would you apply to the image so that the large image shrinks down into the box but the small image does not stretch.

Your final result should look like the images below:

![Two boxes with images in](mdn-sizing-max-width.png)

Try updating the live code below to recreate the finished example:

```html live-sample___max-width
<div class="box">
  <img alt="star" src="star.png" />
</div>

<div class="box">
  <img alt="balloons" src="balloons.jpg" />
</div>
```

```css live-sample___max-width
img {
}
```

{{EmbedLiveSample("max-width")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/sizing/max-width-download.html) to work in your own editor or in an online editor.
