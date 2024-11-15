---
title: "Test your skills: HTML text basics"
slug: Learn/HTML/Introduction_to_HTML/Test_your_skills:_HTML_text_basics
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of this skill test is to assess whether you understand how to [mark up text in HTML](/en-US/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals) to give it structure and meaning.

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Task 1

In this task, we want you to mark up the provided HTML using semantic heading and paragraph elements.

The finished example should look like this:

```html live-sample___basic-text1-finished
<body>
  <main>
    <h1>Basic HTML Animals</h1>
    <p>This is the first paragraph in our page. It introduces our animals.</p>
    <h2>The Llama</h2>
    <p>
      Our Llama is a big fan of list items. When she spies a patch of them on a
      web page, she will eat them like sweets, licking her lips as she goes.
    </p>
    <h2>The Anaconda</h2>
    <p>
      The crafty anaconda likes to slither around the page, travelling rapidly
      by way of anchors to sneak up on his prey.
    </p>
  </main>
</body>
```

```css live-sample___basic-text1-finished
* {
  box-sizing: border-box;
}

h1,
h2 {
  color: purple;
}

p {
  color: gray;
}
```

{{EmbedLiveSample("basic-text1-finished")}}

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/html/introduction-to-html/tasks/basic-text/basic-text1.html", '100%', 700)}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/html/introduction-to-html/tasks/basic-text/basic-text1-download.html) to work in your own editor or in an online editor.

## Task 2

In this task, we want you to turn the first un-marked up list into an unordered list, and the second one into an ordered list.

The finished example should look like this:

```html live-sample___basic-text2-finished
<body>
  <main>
    <h1>Looking at lists</h1>
    <p>
      Turn the following list of my favorite vegetables into an unordered list.
    </p>
    <ul>
      <li>Cucumber</li>
      <li>Broccoli</li>
      <li>Asparagus</li>
      <li>Pepper</li>
    </ul>
    <p>Turn the following directions into an ordered list.</p>
    <ol>
      <li>First knock on the door</li>
      <li>When prompted, say the magic word</li>
      <li>Wait for at least 5 seconds</li>
      <li>Turn the handle and push</li>
    </ol>
  </main>
</body>
```

```css live-sample___basic-text2-finished
* {
  box-sizing: border-box;
}

ul {
  border: 2px solid orange;
}

ol {
  border: 2px solid purple;
}

ol,
ul {
  padding: 5px 20px;
  border-radius: 4px;
}
```

{{EmbedLiveSample("basic-text2-finished")}}

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/html/introduction-to-html/tasks/basic-text/basic-text2.html", '100%', 700)}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/html/introduction-to-html/tasks/basic-text/basic-text2-download.html) to work in your own editor or in an online editor.

## Task 3

In this task, you are provided with a paragraph, and your aim is to use some inline elements to mark up a couple of appropriate words with strong importance, and a couple with emphasis.

The finished example should look like this:

```html live-sample___basic-text3-finished
<body>
  <main>
    <h1>Emphasis and importance</h1>
    <p>
      There are
      <strong> two </strong>
      things I care about —
      <strong> music </strong>
      and
      <strong> friends </strong>
      . Someday I
      <em> might </em>
      be able to get my friends interested in each other,
      <em> and </em>
      my music!
    </p>
  </main>
</body>
```

```css live-sample___basic-text3-finished
* {
  box-sizing: border-box;
}

h1,
strong {
  color: purple;
}

em {
  color: gray;
}
```

{{EmbedLiveSample("basic-text3-finished")}}

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/html/introduction-to-html/tasks/basic-text/basic-text3.html", '100%', 700)}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/html/introduction-to-html/tasks/basic-text/basic-text3-download.html) to work in your own editor or in an online editor.
