---
title: "Test your skills: Positioning"
slug: Learn/CSS/CSS_layout/Position_skills
page-type: learn-module-assessment
---

{{LearnSidebar}}

The aim of this skill test is to assess whether you understand [positioning in CSS](/en-US/docs/Learn/CSS/CSS_layout/Positioning) using the CSS {{CSSxRef("position")}} property and values. You will be working through two small tasks that use different elements of the material you have just covered.

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Task 1

In this task, we want you to position the item with a class of `target` to the top and right of the container, which has the 5px grey border.

Your final result should look like the image below:

![The green box is at the top right of a container with a grey border.](position-task1.png)

Try updating the live code below to recreate the finished example:

```html live-sample___position1
<div class="container">
  <p>
    Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion
    daikon amaranth tatsoi tomatillo melon azuki bean garlic.
  </p>
  <div class="target">Target</div>
  <p>
    Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette
    tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato.
    Dandelion cucumber earthnut pea peanut soko zucchini.
  </p>
</div>
```

```css live-sample___position1
.container {
}

.target {
}
```

{{EmbedLiveSample("position1")}}

Additional question:

- As an extra challenge, can you change the target to display underneath the text?

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/position/position1-download.html) to work in your own editor or in an online editor.

## Task 2

In this task, if you scroll the box in the example below, the sidebar scrolls with the content. Change it so that the sidebar stays in place and only the content scrolls.

![The content is scrolled but the sidebar has stayed in place.](position-task2.png)

Try updating the live code below to recreate the finished example:

```html live-sample___position2
<div class="container">
  <div class="sidebar">
    <p>
      This is the sidebar. It should remain in position as the content scrolls.
    </p>
  </div>
  <div class="content">
    <p>
      Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh
      onion daikon amaranth tatsoi tomatillo melon azuki bean garlic.
    </p>
    <p>
      Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette
      tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato.
      Dandelion cucumber earthnut pea peanut soko zucchini.
    </p>
    <p>
      Turnip greens yarrow ricebean rutabaga endive cauliflower sea lettuce
      kohlrabi amaranth water spinach avocado daikon napa cabbage asparagus
      winter purslane kale. Celery potato scallion desert raisin horseradish
      spinach carrot soko. Lotus root water spinach fennel kombu maize bamboo
      shoot green bean swiss chard seakale pumpkin onion chickpea gram corn pea.
      Brussels sprout coriander water chestnut gourd swiss chard wakame kohlrabi
      beetroot carrot watercress. Corn amaranth salsify bunya nuts nori azuki
      bean chickweed potato bell pepper artichoke.
    </p>
  </div>
</div>
```

```css live-sample___position2
.container {
}

.sidebar {
}
```

{{EmbedLiveSample("position2")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/position/position2-download.html) to work in your own editor or in an online editor.
