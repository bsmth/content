---
title: "Test your skills: Writing modes and logical properties"
slug: Learn/CSS/Building_blocks/Writing_Modes_Tasks
page-type: learn-module-assessment
---

{{LearnSidebar}}

The aim of this skill test is to assess whether you understand how to [handle different text directions using writing modes and logical properties in CSS](/en-US/docs/Learn/CSS/Building_blocks/Handling_different_text_directions).

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Task 1

In this task, the box is displayed with a horizontal writing mode. Can you add a line of CSS to change it so it uses a vertical writing mode with right to left text?

Your final result should look like the image below:

![A box with a vertical writing mode](mdn-writing-modes1.png)

Try updating the live code below to recreate the finished example:

```html live-sample___writing-mode
<div class="box">Turn me on my side.</div>
```

```css live-sample___writing-mode
.box {
  border: 5px solid rebeccapurple;
  background-color: lightgray;
  padding: 40px;
  margin: 40px;
}
```

{{EmbedLiveSample("writing-mode")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/writing-modes/writing-mode-download.html) to work in your own editor or in an online editor.

## Task 2

In this task, we want you to use logical properties to replace `width` and `height` in order to maintain the {{glossary("aspect ratio")}} of the box as it is turned vertically.

Your final result should look like the image below:

![Two boxes one horizontal the other vertical](mdn-writing-modes2.png)

Try updating the live code below to recreate the finished example:

```html live-sample___logical-width-height
<div class="box">Horizontal.</div>
<div class="box vertical">Vertical.</div>
```

```css live-sample___logical-width-height
.box {
  border: 5px solid rebeccapurple;
  background-color: lightgray;
  padding: 40px;
  margin: 40px;
  width: 200px;
  height: 100px;
}
```

{{EmbedLiveSample("logical-width-height")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/writing-modes/logical-width-height-download.html) to work in your own editor or in an online editor.

## Task 3

In this task, we want you to use logical versions of the margin, border, and padding properties so that the edges of the box relate to the text rather than following top, left, bottom and right.

Your final result should look like the image below:

![Two boxes one horizontal one vertical with different margin, border and padding](mdn-writing-modes3.png)

Try updating the live code below to recreate the finished example:

```html live-sample___logical-mbp
<div class="box">Horizontal.</div>
<div class="box vertical">Vertical.</div>
```

```css live-sample___logical-mbp
.box {
  width: 150px;
  height: 150px;
  border-top: 5px solid rebeccapurple;
  border-right: 5px solid grey;
  border-bottom: 5px dotted red;
  border-left: 5px dotted blue;
  padding-top: 40px;
  margin-bottom: 30px;
}
```

{{EmbedLiveSample("logical-mbp")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/writing-modes/logical-mbp-download.html) to work in your own editor or in an online editor.
