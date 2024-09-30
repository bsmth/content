---
title: "Test your skills: Flexbox"
slug: Learn/CSS/CSS_layout/Flexbox_skills
page-type: learn-module-assessment
---

{{LearnSidebar}}

The aim of this skill test is to assess whether you understand how [flexbox and flex items](/en-US/docs/Learn/CSS/CSS_layout/Flexbox) behave. Below are four common design patterns that you might use flexbox to create. Your task is to build them.

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Task 1

In this task, the list items are the navigation for a site. They should be laid out as a row, with an equal amount of space between each item.

Your final result should look like the image below:

![Flex items laid out as a row with space between them.](flex-task1.png)

Try updating the live code below to recreate the finished example:

```html live-sample___flexbox1
<nav>
  <ul>
    <li><a href="/">Home</a></li>
    <li><a href="/about">About Us</a></li>
    <li><a href="/products">Our Products</a></li>
    <li><a href="/contact">Contact Us</a></li>
  </ul>
</nav>
```

```css live-sample___flexbox1
nav ul {
}
```

{{EmbedLiveSample("flexbox1")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/flexbox/flexbox1-download.html) to work in your own editor or in an online editor.

## Task 2

In this task, the list items are all different sizes, but we want them to be displayed as three equal sized columns, no matter what content is in each item.

Your final result should look like the image below:

![Flex items laid out as three equal size columns with different amounts of content.](flex-task2.png)

Try updating the live code below to recreate the finished example:

```html live-sample___flexbox2
<ul>
  <li>I am small</li>
  <li>I have more content than the very small item.</li>
  <li>
    I have lots of content. So much content that I don't know where it is all
    going to go. I'm glad that CSS is pretty good at dealing with situations
    where we end up with more words than expected!
  </li>
</ul>
```

```css live-sample___flexbox2
ul {
}

li {
}
```

{{EmbedLiveSample("flexbox2")}}

Additional question:

- Can you now make the first item twice the size of the other items?

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/flexbox/flexbox2-download.html) to work in your own editor or in an online editor.

## Task 3

In this task, there are two elements in the HTML below, a `<div>` element with a class of `parent` which contains another `<div>` element with a class of `child`. Use flexbox to center the child inside the parent. Note that there is not just one possible solution here.

Your final result should look like the image below:

![A box centered inside another box.](flex-task3.png)

Try updating the live code below to recreate the finished example:

```html live-sample___flexbox3
<div class="parent">
  <div class="child">Center me.</div>
</div>
```

```css live-sample___flexbox3
.parent {
}

.child {
}
```

{{EmbedLiveSample("flexbox3")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/flexbox/flexbox3-download.html) to work in your own editor or in an online editor.

## Task 4

In this task, we want you to arrange these items into rows as in the image below:

![A set of items displayed as rows.](flex-task4.png)

Try updating the live code below to recreate the finished example:

```html live-sample___flexbox4
<ul>
  <li>Turnip</li>
  <li>greens</li>
  <li>yarrow</li>
  <li>ricebean</li>
  <li>rutabaga</li>
  <li>endive</li>
  <li>cauliflower</li>
  <li>sea lettuce</li>
  <li>kohlrabi</li>
  <li>amaranth</li>
</ul>
```

```css live-sample___flexbox4
ul {
}

li {
}
```

{{EmbedLiveSample("flexbox4")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/flexbox/flexbox4-download.html) to work in your own editor or in an online editor.
