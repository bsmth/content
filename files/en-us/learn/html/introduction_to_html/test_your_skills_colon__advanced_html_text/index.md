---
title: "Test your skills: Advanced HTML text"
slug: Learn/HTML/Introduction_to_HTML/Test_your_skills:_Advanced_HTML_text
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of this skill test is to assess whether you understand how to use [lesser-known HTML elements to mark up advanced semantic features](/en-US/docs/Learn/HTML/Introduction_to_HTML/Advanced_text_formatting).

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Task 1

In this task, we want you to turn the provided animals and their definitions into a description list.

The finished example should look like this:

```html live-sample___advanced-text1-finished
<body>
  <h1>Advanced HTML Animals</h1>
  <dl>
    <dt>Llama</dt>
    <dd>
      Tall, woolly quadruped, pointy ears. Sometimes rideable, but grumpy and
      spits a lot. Big fan of list items.
    </dd>
    <dt>Anaconda</dt>
    <dd>
      A very large constrictor snake; travels rapidly by way of anchors to sneak
      up on his prey.
    </dd>
    <dt>Hippopotamus</dt>
    <dd>His description is bottomless.</dd>
  </dl>
</body>
```

```css live-sample___advanced-text1-finished
body {
  background-color: #fff;
  color: #333;
  font:
    1em / 1.4 Helvetica Neue,
    Helvetica,
    Arial,
    sans-serif;
  padding: 1em;
  margin: 0;
}

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

* {
  box-sizing: border-box;
}
```

{{EmbedLiveSample("advanced-text1-finished")}}

{{EmbedGHLiveSample("learning-area/html/introduction-to-html/tasks/advanced-text/advanced-text1.html", '100%', 700)}}

## Task 2

In this task, we want you to add some semantics to the provided HTML as follows:

- Turn the second paragraph into a block-level quote, and semantically indicate that the quote is taken from [Accessibility](/en-US/docs/Learn/Accessibility).
- Semantically mark up "HTML" and "CSS" as acronyms, providing expansions as tooltips.
- Use subscript and superscript to provide correct semantics for the chemical formulae and dates, and make them display correctly.
- Semantically associate machine-readable dates with the dates in the text.

The finished example should look like this:

```html live-sample___advanced-text2-finished
<body>
  <h1>Advanced text semantics</h1>
  <p>Let's start with a quote:</p>
  <blockquote
    cite="https://developer.mozilla.org/en-US/docs/Learn/Accessibility">
    <p>
      <abbr title="HyperText Markup Language"> HTML </abbr>
      , Hypertext Markup Language is by default accessible, if used correctly.
    </p>
  </blockquote>
  <p>
    <abbr title="Cascading Style Sheets"> CSS </abbr>
    , Cascading Style Sheets, can also be used to make web pages more, or less,
    accessible.
  </p>
  <p>
    Chemical Formulae: H
    <sub> 2 </sub>
    O (Water), C
    <sub> 2 </sub>
    H
    <sub> 6 </sub>
    O (Ethanol).
  </p>
  <p>
    Dates:
    <time datetime="2019-12-25">
      December 25
      <sup> th </sup>
      2019
    </time>
    (Christmas Day),
    <time datetime="2019-11-02">
      November 2
      <sup> nd </sup>
      2019
    </time>
    (Día de los Muertos).
  </p>
</body>
```

```css live-sample___advanced-text2-finished
body {
  background-color: #fff;
  color: #333;
  font:
    1em / 1.4 Helvetica Neue,
    Helvetica,
    Arial,
    sans-serif;
  padding: 1em;
  margin: 0;
}

h1 {
  font-size: 2rem;
  margin: 0;
  color: purple;
}

p {
  margin: 0.5em 0;
}

abbr,
time {
  color: green;
}
```

{{EmbedLiveSample("advanced-text2-finished")}}

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/html/introduction-to-html/tasks/advanced-text/advanced-text2.html", '100%', 700)}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/html/introduction-to-html/tasks/advanced-text/advanced-text2-download.html) to work in your own editor or in an online editor.
