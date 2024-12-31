---
title: "Test your skills: Links"
slug: Learn_web_development/Core/Structuring_content/Test_your_skills:_Links
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of this skill test is to assess whether you understand how to [implement links in HTML](/en-US/docs/Learn_web_development/Core/Structuring_content/Creating_links).

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Task 1

In this task, we want you to help fill in the links on our Whales information page:

- The first link should be linked to a page called `whales.html`, which is in the same directory as the current page.
- We'd also like you to give it a tooltip when moused over that tells the user that the page includes information on Blue Whales and Sperm Whales.
- The second link should be turned into a link you can click to open up an email in the user's default mail application, with the recipient set as "whales\@example.com".
- You'll get a bonus point if you also set it so that the subject line of the email is automatically filled in as "Question about Whales".

> [!NOTE]
> The two links in the example have the `target="_blank"` attribute set on them. This is not strictly best practice, but we've done it here so that the links don't open in the embedded `<iframe>`, getting rid of your example code in the process!

Try updating the live code below to recreate the finished example:

```html live-sample___links1
<h1>Information on Whales</h1>

<p>
  For more information on our conservation activities and which Whales we study,
  see our <a target="_blank">Whales page</a>.
</p>

<p>
  If you want to ask our team more questions, feel free to
  <a target="_blank">email us</a>.
</p>
```

```css live-sample___links1
p {
  color: gray;
}
```

{{EmbedLiveSample("links1")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/html/introduction-to-html/tasks/links/links1-download.html) to work in your own editor or in an online editor.

## Task 2

In this task, we want you to fill in the four links so that they link to the appropriate places:

- The first link should link to an image called `blue-whale.jpg`, which is located in a directory called `blue` inside the current directory.
- The second link should link to an image called `narwhal.jpg`, which is located in a directory called `narwhal`, which is located one directory level above the current directory.
- The third link should link to the UK Google Image search. The base URL is `https://www.google.co.uk`, and the image search is located in a subdirectory called `imghp`.
- The fourth link should link to the paragraph at the very bottom of the current page. It has an ID of `bottom`.

> [!NOTE]
> The first three links in the example have the `target="_blank"` attribute set on them, so that when you click on them, they open the linked page in a new tab. This is not strictly best practice, but we've done it here so that the pages don't open in the embedded `<iframe>`, getting rid of your example code in the process!

Try updating the live code below to recreate the finished example:

```html live-sample___links2
<h1>List path tests</h1>

<ul>
  <li><a target="_blank">Link me to the blue whale image</a></li>
  <li><a target="_blank">Link me to the narwhal image</a></li>
  <li><a target="_blank">Link me to Google image search</a></li>
  <li><a>Link me to the paragraph at the bottom of the page</a></li>
</ul>

<div></div>

<p id="bottom">The bottom of the page!</p>
```

```css live-sample___links2
h1 {
  font-size: 2rem;
  margin: 0;
  color: purple;
}

li {
  color: gray;
  margin: 0.5em 0;
}

div {
  height: 600px;
}
```

{{EmbedLiveSample("links2")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/html/introduction-to-html/tasks/links/links2-download.html) to work in your own editor or in an online editor.

## Task 3

The following links link to an info page about Narwhals, a support email address, and a PDF factfile that is 4MB in size. In this task, we want you to:

- Take the existing paragraphs with poorly-written link text, and rewrite them so that they have good link text.
- Add a warning to any links that need a warning added.

> [!NOTE]
> The first and third links in the example have the `target="_blank"` attribute set on them, so that when you click on them, they open the linked page in a new tab. This is not strictly best practice, but we've done it here so that the pages don't open in the embedded `<iframe>`, getting rid of your example code in the process!

Try updating the live code below to recreate the finished example:

```html live-sample___links3
<p>
  We do lots of work with Narwhals. To find out more about this work,
  <a href="narwhals.html" target="_blank">click here</a>.
</p>

<p>
  You can email our support team if you have any more questions —
  <a href="mailto:whales@example.com">click here</a> to do so.
</p>

<p>
  You can also <a href="factfile.pdf" target="_blank">click here</a> to download
  our factfile, which contains lots more information, including an FAQ.
</p>
```

```css live-sample___links3
p {
  color: gray;
  margin: 0.5em 0;
}
```

{{EmbedLiveSample("links3")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/html/introduction-to-html/tasks/links/links3-download.html) to work in your own editor or in an online editor.
