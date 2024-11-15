---
title: "Test your skills: Links"
slug: Learn/HTML/Introduction_to_HTML/Test_your_skills:_Links
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of this skill test is to assess whether you understand how to [implement hyperlinks in HTML](/en-US/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks).

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

{{EmbedGHLiveSample("learning-area/html/introduction-to-html/tasks/links/links1.html", '100%', 700)}}

<details>
<summary>Click here to show the solution</summary>

The first task covers some link basics — setting a link destination, giving it a descriptive title, and creating an email link. The solution should look something like this:

```html
<h1>Information on Whales</h1>

<p>
  For more information on our conservation activities and which Whales we study,
  see our
  <a
    href="whales.html"
    target="_blank"
    title="includes information on Blue Whales and Sperm Whales"
    >Whales page</a
  >.
</p>

<p>
  If you want to ask our team more questions, feel free to
  <a href="mailto:whales@example.com?subject=Question%20about%20Whales"
    >email us</a
  >.
</p>
```

The title needs to contain some supplemental information about the page that is useful but not essential for knowing what the linked page is about. If the subject was included on the email link, it really needs `%20` escape characters included so that you get spaces in the subject line.

</details>

## Task 2

In this task, we want you to fill in the four links so that they link to the appropriate places:

- The first link should link to an image called `blue-whale.jpg`, which is located in a directory called `blue` inside the current directory.
- The second link should link to an image called `narwhal.jpg`, which is located in a directory called `narwhal`, which is located one directory level above the current directory.
- The third link should link to the UK Google Image search. The base URL is `https://www.google.co.uk`, and the image search is located in a subdirectory called `imghp`.
- The fourth link should link to the paragraph at the very bottom of the current page. It has an ID of `bottom`.

> [!NOTE]
> The first three links in the example have the `target="_blank"` attribute set on them, so that when you click on them, they open the linked page in a new tab. This is not strictly best practice, but we've done it here so that the pages don't open in the embedded `<iframe>`, getting rid of your example code in the process!

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/html/introduction-to-html/tasks/links/links2.html", '100%', 800)}}

<details>
<summary>Click here to show the solution</summary>

Our second task here tests the student's knowledge of absolute and relative paths, as well as link fragments

The finished list code should look like this:

```html
<h1>List path tests</h1>

<ul>
  <li>
    <a href="blue/blue-whale.jpg" target="_blank">
      Link me to the blue whale image
    </a>
  </li>
  <li>
    <a href="../narwhal/narwhal.png" target="_blank">
      Link me to the narwhal image
    </a>
  </li>
  <li>
    <a href="https://www.google.co.uk/imghp" target="_blank">
      Link me to Google image search
    </a>
  </li>
  <li>
    <a href="#bottom">Link me to the paragraph at the bottom of the page</a>
  </li>
</ul>
```

</details>

## Task 3

The following links link to an info page about Narwhals, a support email address, and a PDF factfile that is 4MB in size. In this task, we want you to:

- Take the existing paragraphs with poorly-written link text, and rewrite them so that they have good link text.
- Add a warning to any links that need a warning added.

> [!NOTE]
> The first and third links in the example have the `target="_blank"` attribute set on them, so that when you click on them, they open the linked page in a new tab. This is not strictly best practice, but we've done it here so that the pages don't open in the embedded `<iframe>`, getting rid of your example code in the process!

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/html/introduction-to-html/tasks/links/links3.html", '100%', 700)}}

<details>
<summary>Click here to show the solution</summary>

Our final task in this set is concerned with good practices for link text; the code should look something like this:

```html
<p>
  We do lots of work with Narwhals. To find out more, visit our
  <a href="narwhals.html" target="_blank">Narwhals page</a>.
</p>

<p>
  You can <a href="mailto:whales@example.com">email our support team</a> if you
  have any more questions.
</p>

<p>
  You can also
  <a href="factfile.pdf" target="_blank">download our factfile (PDF, 4MB)</a>
  for lots more information, including an FAQ.
</p>
```

Basically, all three paragraphs need to be rewritten with good link text, and the third one needs to have a warning added to the link to say that it is a large download.

</details>
