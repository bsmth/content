---
title: "Test your skills: Selectors"
slug: Learn/CSS/Building_blocks/Selectors/Selectors_Tasks
page-type: learn-module-assessment
---

{{LearnSidebar}}

The aim of this skill test is to assess whether you understand [CSS selectors](/en-US/docs/Learn/CSS/Building_blocks/Selectors).

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Task 1

In this task, use CSS to do the following things, without changing the HTML:

- Make `<h1>` headings blue.
- Give `<h2>` headings a blue background and white text.
- Cause text wrapped in a `<span>` to have a font-size of 200%.

Your final result should look like the image below:

![Text with the CSS applied for the solution to task 1.](selectors1.jpg)

Try updating the live code below to recreate the finished example:

```html live-sample___type
<div class="container">
  <h1>This is a heading</h1>
  <p>
    Veggies es <span>bonus vobis</span>, proinde vos postulo essum magis
    kohlrabi welsh onion daikon amaranth tatsoi tomatillo melon azuki bean
    garlic.
  </p>
  <h2>A level 2 heading</h2>
  <p>
    Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette
    tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato.
    Dandelion cucumber earthnut pea peanut soko zucchini.
  </p>
</div>
```

```css live-sample___type
No CSS block found
```

{{EmbedLiveSample("type")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/selectors/type-download.html) to work in your own editor or in an online editor.

## Task 2

In this task, we want you to make the following changes to the look of the content in this example, without changing the HTML:

- Give the element with an id of `special` a yellow background.
- Give the element with a class of `alert` a 1px grey border.
- If the element with a class of `alert` also has a class of `stop`, make the background red.
- If the element with a class of `alert` also has a class of `go`, make the background green.

Your final result should look like the image below:

![Text with the CSS applied for the solution to task 2.](selectors2.jpg)

Try updating the live code below to recreate the finished example:

```html live-sample___class-id
<div class="container">
  <h1>This is a heading</h1>
  <p>
    Veggies es <span class="alert">bonus vobis</span>, proinde vos postulo
    <span class="alert stop">essum magis</span> kohlrabi welsh onion daikon
    amaranth tatsoi tomatillo melon azuki bean garlic.
  </p>
  <h2 id="special">A level 2 heading</h2>
  <p>Gumbo beet greens corn soko endive gumbo gourd.</p>
  <h2>Another level 2 heading</h2>
  <p>
    <span class="alert go">Parsley shallot</span> courgette tatsoi pea sprouts
    fava bean collard greens dandelion okra wakame tomato. Dandelion cucumber
    earthnut pea peanut soko zucchini.
  </p>
</div>
```

```css live-sample___class-id
No CSS block found
```

{{EmbedLiveSample("class-id")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/selectors/class-id-download.html) to work in your own editor or in an online editor.

## Task 3

In this task, we want you to make the following changes without adding to the HTML:

- Style links, making the link-state orange, visited links green, and remove the underline on hover.
- Make the first element inside the container font-size: 150% and the first line of that element red.
- Stripe every other row in the table by selecting these rows and giving them a background color of #333 and foreground of white.

Your final result should look like the image below:

![Text with the CSS applied for the solution to task 3.](selectors3.jpg)

Try updating the live code below to recreate the finished example:

```html live-sample___pseudo
<div class="container">
  <p>
    Veggies es <a href="http://example.com">bonus vobis</a>, proinde vos postulo
    essum magis kohlrabi welsh onion daikon amaranth tatsoi tomatillo melon
    azuki bean garlic.
  </p>
  <p>
    Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette
    tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato.
    Dandelion cucumber earthnut pea peanut soko zucchini.
  </p>
  <table>
    <tbody>
      <tr>
        <th>Fruits</th>
        <th>Vegetables</th>
      </tr>
      <tr>
        <td>Apple</td>
        <td>Potato</td>
      </tr>
      <tr>
        <td>Orange</td>
        <td>Carrot</td>
      </tr>
      <tr>
        <td>Tomato</td>
        <td>Parsnip</td>
      </tr>
      <tr>
        <td>Kiwi</td>
        <td>Onion</td>
      </tr>
      <tr>
        <td>Banana</td>
        <td>Beet</td>
      </tr>
    </tbody>
  </table>
</div>
```

```css live-sample___pseudo
No CSS block found
```

{{EmbedLiveSample("pseudo")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/selectors/pseudo-download.html) to work in your own editor or in an online editor.

## Task 4

In this task, we want you to do the following:

- Make any paragraph that directly follows an `<h2>` element red.
- Remove the bullets and add a 1px grey bottom border only to list items that are a direct child of the ul with a class of `list`.

Your final result should look like the image below:

![Text with the CSS applied for the solution to task 4.](selectors4.jpg)

Try updating the live code below to recreate the finished example:

```html live-sample___combinators
<div class="container">
  <h2>This is a heading</h2>
  <p>This paragraph comes after the heading.</p>
  <p>This is the second paragraph.</p>

  <h2>Another heading</h2>
  <p>This paragraph comes after the heading.</p>
  <ul class="list">
    <li>One</li>
    <li>
      Two
      <ul>
        <li>2.1</li>
        <li>2.2</li>
      </ul>
    </li>
    <li>Three</li>
  </ul>
</div>
```

```css live-sample___combinators
No CSS block found
```

{{EmbedLiveSample("combinators")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/selectors/combinators-download.html) to work in your own editor or in an online editor.

## Task 5

In this task, add CSS using attribute selectors to do the following:

- Target the `<a>` element with a `title` attribute and make the border pink (`border-color: pink`).
- Target the `<a>` element with an `href` attribute that contains the word `contact` somewhere in its value and make the border orange (`border-color: orange`).
- Target the `<a>` element with an `href` value starting with `https` and give it a green border (`border-color: green`).

Your final result should look like the image below:

![Four links with different color borders.](selectors-attribute.png)

Try updating the live code below to recreate the finished example:

```html live-sample___attribute-links
<ul>
  <li><a href="https://example.com">Link 1</a></li>
  <li><a href="http://example.com" title="Visit example.com">Link 2</a></li>
  <li><a href="/contact">Link 3</a></li>
  <li><a href="../contact/index.html">Link 4</a></li>
</ul>
```

```css live-sample___attribute-links
a {
  border: 5px solid grey;
}
```

{{EmbedLiveSample("attribute-links")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/selectors/attribute-links-download.html) to work in your own editor or in an online editor.
