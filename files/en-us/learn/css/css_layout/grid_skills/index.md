---
title: "Test your skills: Grid"
slug: Learn/CSS/CSS_layout/Grid_skills
page-type: learn-module-assessment
---

{{LearnSidebar}}

The aim of this skill test is to assess whether you understand how a [grid and grid items](/en-US/docs/Learn/CSS/CSS_layout/Grids) behave. You will be working through several small tasks that use different elements of the material you have just covered.

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Task 1

In this task, you should create a grid into which the four child elements will auto-place. The grid should have three columns sharing the available space equally and a 20-pixel gap between the column and row tracks. After that, try adding more child containers inside the parent container with the class of `grid` and see how they behave by default.

Your final result should look like the image below:

![A three column grid with four items placed into it.](grid-task1.png)

Try updating the live code below to recreate the finished example:

```html live-sample___grid1
<div class="grid">
  <div>One</div>
  <div>Two</div>
  <div>Three</div>
  <div>Four</div>
</div>
```

```css live-sample___grid1
.grid {
}
```

{{EmbedLiveSample("grid1")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/grid/grid1-download.html) to work in your own editor or in an online editor.

## Task 2

In this task, we already have a grid defined. By editing the CSS rules for the two child elements, cause them to span over several grid tracks each. The second item should overlay the first as in the image below:

![A box with two items inside one overlaying the other.](grid-task2.png)

Try updating the live code below to recreate the finished example:

```html live-sample___grid2
<div class="grid">
  <div class="item1">One</div>
  <div class="item2">Two</div>
</div>
```

```css live-sample___grid2
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-template-rows: 100px 100px 100px;
  gap: 10px;
}

.item1 {
}

.item2 {
}
```

{{EmbedLiveSample("grid2")}}

Additional question:

- Can you now cause the first item to display on top without changing the order of items in the source?

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/grid/grid2-download.html) to work in your own editor or in an online editor.

## Task 3

In this task, there are four direct children in this grid. The starting point has them displayed using auto-placement. Use the grid-area and grid-template-areas properties to lay the items out as shown in the image below:

![Four items displayed in a grid.](grid-task3.png)

Try updating the live code below to recreate the finished example:

```html live-sample___grid3
<div class="grid">
  <div class="one">One</div>
  <div class="two">Two</div>
  <div class="three">Three</div>
  <div class="four">Four</div>
</div>
```

```css live-sample___grid3
.grid {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 10px;
}
```

{{EmbedLiveSample("grid3")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/grid/grid3-download.html) to work in your own editor or in an online editor.

## Task 4

In this task, you will need to use both grid layout and flexbox to recreate the example as seen in the image below. The gap between the column and row tracks should be 10px. You do not need to make any changes to the HTML in order to achieve this.

![Two rows of cards, each with an image and a set of tags.](grid-task4.png)

Try updating the live code below to recreate the finished example:

```html live-sample___grid4
<div class="container">
  <div class="card">
    <img alt="a single red balloon" src="balloons1.jpg" />
    <ul class="tags">
      <li>balloon</li>
      <li>red</li>
      <li>sky</li>
      <li>blue</li>
      <li>Hot air balloon</li>
    </ul>
  </div>
  <div class="card">
    <img alt="balloons over some houses" src="balloons2.jpg" />
    <ul class="tags">
      <li>balloons</li>
      <li>houses</li>
      <li>train</li>
      <li>harborside</li>
    </ul>
  </div>
  <div class="card">
    <img alt="close-up of balloons inflating" src="balloons3.jpg" />
    <ul class="tags">
      <li>balloons</li>
      <li>inflating</li>
      <li>green</li>
      <li>blue</li>
    </ul>
  </div>
  <div class="card">
    <img alt="a balloon in the sun" src="balloons4.jpg" />
    <ul class="tags">
      <li>balloon</li>
      <li>sun</li>
      <li>sky</li>
      <li>summer</li>
      <li>bright</li>
    </ul>
  </div>
</div>
```

```css live-sample___grid4
.container {
}

.tags {
}
```

{{EmbedLiveSample("grid4")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/grid/grid4-download.html) to work in your own editor or in an online editor.
