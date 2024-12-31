---
title: "Test your skills: Advanced HTML text"
slug: Learn_web_development/Core/Structuring_content/Test_your_skills:_Advanced_HTML_text
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of this skill test is to assess whether you understand how to use [lesser-known HTML elements to mark up advanced semantic features](/en-US/docs/Learn_web_development/Core/Structuring_content/Advanced_text_features).

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Task 1

In this task, we want you to add some semantics to the provided HTML as follows:

- Turn the second paragraph into a block-level quote, and semantically indicate that the quote is taken from [Accessibility](/en-US/docs/Learn_web_development/Core/Accessibility).
- Semantically mark up "HTML" and "CSS" as acronyms, providing expansions as tooltips.
- Use subscript and superscript to provide correct semantics for the chemical formulae and dates, and make them display correctly.
- Semantically associate machine-readable dates with the dates in the text.

The finished example should look like this:

```html hidden live-sample___advanced-text2-finished
<body>
  <h1>Advanced text semantics</h1>
  <p>Let's start with a quote:</p>
  <blockquote
    cite="https://developer.mozilla.org/en-US/docs/Learn/Accessibility">
    <p>
      <abbr title="HyperText Markup Language">HTML</abbr>, Hypertext Markup
      Language is by default accessible, if used correctly.
    </p>
  </blockquote>
  <p>
    <abbr title="Cascading Style Sheets">CSS</abbr>, Cascading Style Sheets, can
    also be used to make web pages more, or less, accessible.
  </p>
  <p>
    Chemical Formulae: H<sub>2</sub>O (Water), C<sub>2</sub>H<sub>6</sub>O
    (Ethanol).
  </p>
  <p>
    Dates:
    <time datetime="2019-12-25">December 25 <sup>th</sup> 2019 </time>
    (Christmas Day),
    <time datetime="2019-11-02">November 2<sup>nd</sup>2019</time>
    (Día de los Muertos).
  </p>
</body>
```

```css hidden live-sample___advanced-text2-finished
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

```html live-sample___advanced-text2
<h1>Advanced text semantics</h1>

<p>Let's start with a quote:</p>

<p>
  HTML, Hypertext Markup Language is by default accessible, if used correctly.
</p>

<p>CSS can also be used to make web pages more, or less, accessible.</p>

<p>Chemical Formulae: H2O (Water), C2H6O (Ethanol).</p>

<p>
  Dates: December 25th 2019 (Christmas Day), November 2nd 2019 (Día de los
  Muertos).
</p>
```

```css live-sample___advanced-text2
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

{{EmbedLiveSample("advanced-text2")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/html/introduction-to-html/tasks/advanced-text/advanced-text2-download.html) to work in your own editor or in an online editor.
