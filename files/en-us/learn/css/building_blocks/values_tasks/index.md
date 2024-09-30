---
title: "Test your skills: Values and units"
slug: Learn/CSS/Building_blocks/Values_tasks
page-type: learn-module-assessment
---

{{LearnSidebar}}

The aim of this skill test is to assess whether you understand different types of [values and units used in CSS properties](/en-US/docs/Learn/CSS/Building_blocks/Values_and_units).

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Task 1

In this task, the first list item has been given a background color using a hex color code. Your task is to complete the CSS using the same color in different formats, plus a final list item where you should make the background semi-opaque.

- The second list item should use RGB color.
- The third should use HSL color.
- The fourth should use RGB color but with the alpha channel set to `0.6`.

You can find conversions for the hex color at [this link](https://convertingcolors.com/hex-color-86DEFA.html). You need to figure out how to use the values in CSS. Your final result should look like the image below:

![Four list items. The first three with the same background color and the last with a lighter background.](mdn-value-color.png)

Try updating the live code below to recreate the finished example:

```html live-sample___color
<ul>
  <li class="hex">hex color</li>
  <li class="rgb">RGB color</li>
  <li class="hsl">HSL color</li>
  <li class="transparency">Alpha value 0.6</li>
</ul>
```

```css live-sample___color
.hex {
  background-color: #86defa;
}

.rgb {
}

.hsl {
}

.transparency {
}
```

{{EmbedLiveSample("color")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/values/color-download.html) to work in your own editor or in an online editor.

## Task 2

In this task, we want you to set the size of various items of text, as described below:

- The `<h1>` element should be 50 pixels.
- The `<h2>` element should be 2em.
- All `<p>` elements should be 16 pixels.
- A `<p>` element that is directly after an `<h1>` should be 120%.

Your final result should look like the image below:

![Some text at varying sizes.](mdn-value-length.png)

Try updating the live code below to recreate the finished example:

```html live-sample___length
<h1>Level 1 heading</h1>
<p>
  Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion
  daikon amaranth tatsoi tomatillo melon azuki bean garlic.
</p>
<h2>Level 2 heading</h2>
<p>
  Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette
  tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato.
  Dandelion cucumber earthnut pea peanut soko zucchini.
</p>
```

```css live-sample___length
h1 {
}

h2 {
}

p {
}

h1 + p {
}
```

{{EmbedLiveSample("length")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/values/length-download.html) to work in your own editor or in an online editor.

## Task 3

In this task, we want you to move the background image so that it is centered horizontally and is 20% from the top of the box.

Your final result should look like the image below:

![A stat centered horizontally in a box and a short distance from the top of the box.](mdn-value-position.png)

Try updating the live code below to recreate the finished example:

```html live-sample___position
<div class="box"></div>
```

```css live-sample___position
.box {
  background-image: url(star.png);
  background-repeat: no-repeat;
}
```

{{EmbedLiveSample("position")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/values/position-download.html) to work in your own editor or in an online editor.
