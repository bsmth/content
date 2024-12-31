---
title: "Test your skills: HTML text basics"
slug: Learn_web_development/Core/Structuring_content/Test_your_skills:_HTML_text_basics
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of this skill test is to assess whether you understand how to mark up text in HTML to give it structure and meaning.

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Task 1

In this task, we want you to mark up the provided HTML using semantic heading and paragraph elements.

The finished example should look like this:

{{EmbedGHLiveSample("learning-area/html/introduction-to-html/tasks/basic-text/basic-text1-finished.html", '100%', 300)}}

Try updating the live code below to recreate the finished example:

```html live-sample___basic-text1
Basic HTML Animals This is the first paragraph in our page. It introduces our
animals. The Llama Our Llama is a big fan of list items. When she spies a patch
of them on a web page, she will eat them like sweets, licking her lips as she
goes. The Anaconda The crafty anaconda likes to slither around the page,
travelling rapidly by way of anchors to sneak up on his prey.
```

```css live-sample___basic-text1
h1,
h2 {
  color: purple;
}

p {
  color: gray;
}
```

{{EmbedLiveSample("basic-text1")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/html/introduction-to-html/tasks/basic-text/basic-text1-download.html) to work in your own editor or in an online editor.

## Task 2

In this task, we want you to turn the first un-marked up list into an unordered list, and the second one into an ordered list.

The finished example should look like this:

{{EmbedGHLiveSample("learning-area/html/introduction-to-html/tasks/basic-text/basic-text2-finished.html", '100%', 400)}}

Try updating the live code below to recreate the finished example:

```html live-sample___basic-text2
<h1>Looking at lists</h1>

<p>Turn the following list of my favorite vegetables into an unordered list.</p>

Cucumber Broccoli Asparagus Pepper

<p>Turn the following directions into an ordered list.</p>

First knock on the door When prompted, say the magic word Wait for at least 5
seconds Turn the handle and push
```

```css live-sample___basic-text2
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

{{EmbedLiveSample("basic-text2")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/html/introduction-to-html/tasks/basic-text/basic-text2-download.html) to work in your own editor or in an online editor.

## Task 3

In this task, we want you to turn the provided animals and their definitions into a description list.

The finished example should look like this:

{{EmbedGHLiveSample("learning-area/html/introduction-to-html/tasks/advanced-text/advanced-text1-finished.html", '100%', 250)}}

Try updating the live code below to recreate the finished example:

```html live-sample___advanced-text1
<h1>Advanced HTML Animals</h1>

Llama Tall, woolly quadruped, pointy ears. Sometimes rideable, but grumpy and
spits a lot. Big fan of list items. Anaconda A very large constrictor snake;
travels rapidly by way of anchors to sneak up on his prey. Hippopotamus His
description is bottomless.
```

```css live-sample___advanced-text1
h1 {
  font-size: 2rem;
  margin: 0;
  color: purple;
}

dl {
  color: gray;
  margin: 0.5em 0;
}

dt {
  font-weight: bold;
  color: purple;
}
```

{{EmbedLiveSample("advanced-text1")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/html/introduction-to-html/tasks/advanced-text/advanced-text1-download.html) to work in your own editor or in an online editor.

## Task 4

In this task, you are provided with a paragraph, and your aim is to use some inline elements to mark up a couple of appropriate words with strong importance, and a couple with emphasis.

The finished example should look like this:

{{EmbedGHLiveSample("learning-area/html/introduction-to-html/tasks/basic-text/basic-text3-finished.html", '100%', 120)}}

Try updating the live code below to recreate the finished example:

```html live-sample___basic-text3
<h1>Emphasis and importance</h1>

<p>
  There are two things I care about — music and friends. Someday I might be able
  to get my friends interested in each other, and my music!
</p>
```

```css live-sample___basic-text3
h1,
strong {
  color: purple;
}

em {
  color: gray;
}
```

{{EmbedLiveSample("basic-text3")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/html/introduction-to-html/tasks/basic-text/basic-text3-download.html) to work in your own editor or in an online editor.
