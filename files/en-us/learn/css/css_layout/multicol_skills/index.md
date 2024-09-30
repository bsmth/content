---
title: "Test your skills: Multicol"
slug: Learn/CSS/CSS_layout/Multicol_skills
page-type: learn-module-assessment
---

{{LearnSidebar}}

The aim of this skill test is to assess whether you understand [CSS multiple-column layout](/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout), including the {{CSSxRef("column-count")}}, {{CSSxRef("column-width")}}, {{CSSxRef("column-gap")}}, {{CSSxRef("column-span")}} and {{CSSxRef("column-rule")}} properties and values. You will be working through three small tasks that use different elements of the material you have just covered.

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Task 1

In this task, we want you to create three columns, with a 50px gap between each column.

Your final result should look like the image below:

![Three columns of text](multicol-task1.png)

Try updating the live code below to recreate the finished example:

```html live-sample___multicol1
<div class="container">
  <p>
    Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion
    daikon amaranth tatsoi tomatillo melon azuki bean garlic.
  </p>

  <p>
    Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette
    tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato.
    Dandelion cucumber earthnut pea peanut soko zucchini.
  </p>

  <p>
    Turnip greens yarrow ricebean rutabaga endive cauliflower sea lettuce
    kohlrabi amaranth water spinach avocado daikon napa cabbage asparagus winter
    purslane kale. Celery potato scallion desert raisin horseradish spinach
    carrot soko. Lotus root water spinach fennel kombu maize bamboo shoot green
    bean swiss chard seakale pumpkin onion chickpea gram corn pea.
  </p>
</div>
```

```css live-sample___multicol1
.container {
}
```

{{EmbedLiveSample("multicol1")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/multicol/multicol1-download.html) to work in your own editor or in an online editor.

## Task 2

In this task, we want you to create columns which have a minimum width of 200px. Then, add a 5px grey rule between each column, ensuring there is 10px of space between the edge of the rule and the column content.

Your final result should look like the image below:

![Three columns of text with a grey rule between them.](multicol-task2.png)

Try updating the live code below to recreate the finished example:

```html live-sample___multicol2
<div class="container">
  <p>
    Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion
    daikon amaranth tatsoi tomatillo melon azuki bean garlic.
  </p>

  <p>
    Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette
    tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato.
    Dandelion cucumber earthnut pea peanut soko zucchini.
  </p>

  <p>
    Turnip greens yarrow ricebean rutabaga endive cauliflower sea lettuce
    kohlrabi amaranth water spinach avocado daikon napa cabbage asparagus winter
    purslane kale. Celery potato scallion desert raisin horseradish spinach
    carrot soko. Lotus root water spinach fennel kombu maize bamboo shoot green
    bean swiss chard seakale pumpkin onion chickpea gram corn pea.
  </p>
</div>
```

```css live-sample___multicol2
.container {
}
```

{{EmbedLiveSample("multicol2")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/multicol/multicol2-download.html) to work in your own editor or in an online editor.

## Task 3

In this task, we want you to cause the element containing the heading and subheading to span across all columns so it looks like the image below:

![Three columns of text with a heading and subheading spanning all three in the middle.](multicol-task3.png)

Try updating the live code below to recreate the finished example:

```html live-sample___multicol3
<div class="container">
  <p>
    Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion
    daikon amaranth tatsoi tomatillo melon azuki bean garlic.
  </p>

  <p>
    Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette
    tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato.
    Dandelion cucumber earthnut pea peanut soko zucchini.
  </p>
  <div class="box">
    <h2>I am a level 2 heading</h2>
    <div class="subhead">Lotus root water spinach fennel</div>
  </div>
  <p>
    Turnip greens yarrow ricebean rutabaga endive cauliflower sea lettuce
    kohlrabi amaranth water spinach avocado daikon napa cabbage asparagus winter
    purslane kale. Celery potato scallion desert raisin horseradish spinach
    carrot soko. Lotus root water spinach fennel kombu maize bamboo shoot green
    bean swiss chard seakale pumpkin onion chickpea gram corn pea.
  </p>
</div>
```

```css live-sample___multicol3
.container {
  column-count: 3;
}

.box {
}

h2 {
}
```

{{EmbedLiveSample("multicol3")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/multicol/multicol3-download.html) to work in your own editor or in an online editor.
