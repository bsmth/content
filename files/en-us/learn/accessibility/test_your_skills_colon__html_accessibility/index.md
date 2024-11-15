---
title: "Test your skills: HTML accessibility"
slug: Learn/Accessibility/Test_your_skills:_HTML_accessibility
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of this skill test is to assess whether you've understood our [HTML: A good basis for accessibility](/en-US/docs/Learn/Accessibility/HTML) article.

> [!NOTE]
> Click **"Play"** in the code blocks below to edit the examples in the MDN Playground.
> You can also copy the code (click the clipboard icon) and paste it into an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## HTML accessibility 1

In this task we will test your understanding of text semantics, and why they are good for accessibility. The given text is a simple information panel with action buttons, but the HTML is really bad.

We want you to update it use appropriate semantic HTML. You don't need to worry too much about recreating the _exact_ same look and text sizing, as long as the semantics are good.

Try updating the live code below to recreate the finished example:

```html live-sample___html-a11y1
<font size="7">Need help?</font> <br /><br />
If you have any problems with our products, our support center can offer you all
the help you need, whether you want:
<br /><br />
1. Advice choosing a new product
<br />
2. Tech support on an existing product
<br />
3. Refund and cancellation assistance
<br /><br />
<font size="5">Contact us now</font>
<br /><br />
Our help center contains live chat, email addresses, and phone numbers.
<br /><br />
<div class="button">Find Contact Details</div>
<br />
<font size="5">Find out answers</font>
<br /><br />
Our Forums section contains a large knowledge base of searchable previously
asked questions, and you can always ask a new question if you can't find the
answer you're looking for.
<br /><br />
<div class="button">Access Forums</div>
```

```css live-sample___html-a11y1
.button {
  color: white;
  background-color: blue;
  border-radius: 10px;
  width: 170px;
  padding: 10px;
  text-align: center;
}
```

{{EmbedLiveSample("html-a11y1")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/accessibility/tasks/html-css/html/html-a11y1-download.html) to work in your own editor or in an online editor.

## HTML accessibility 2

In the second task, you have a form containing three input fields. You need to:

- Semantically associate the input with their labels.
- Assume that these inputs will be part of a larger form, and wrap them in an element that associates them all together as a single related group.
- Give the group a description/title that summarizes all of the information as personal data.

Try updating the live code below to recreate the finished example:

```html live-sample___html-a11y2
<form>
  <ul>
    <li>
      Name
      <input name="name" type="text" />
    </li>
    <li>
      Age
      <input name="age" type="number" />
    </li>
    <li>
      Email address
      <input name="email" type="email" />
    </li>
  </ul>
</form>
```

```css live-sample___html-a11y2
form {
  width: 400px;
}

li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
```

{{EmbedLiveSample("html-a11y2")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/accessibility/tasks/html-css/html/html-a11y2-download.html) to work in your own editor or in an online editor.

## HTML accessibility 3

In this task you are required to turn all the information links in the paragraph into good, accessible links.

- The first two links just go to regular web pages.
- The third link goes to a PDF, and it's large — 8MB.
- The fourth link goes to a Word document, so the user will need some kind of application installed that can handle that.

Try updating the live code below to recreate the finished example:

```html live-sample___html-a11y3
<p>
  For more information about our activities, check out our fundraising page (<a
    href="/fundraising"
    >click here</a
  >), education page (<a href="/education">click here</a>), sponsorship pack (<a
    href="/resources/sponsorship.pdf"
    >click here</a
  >), and assessment sheets (<a href="/resources/assessments.docx">click here</a
  >).
</p>
```

{{EmbedLiveSample("html-a11y3")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/accessibility/tasks/html-css/html/html-a11y3-download.html) to work in your own editor or in an online editor.

## HTML accessibility 4

In our final HTML accessibility task, you are given a simple image gallery, which has some accessibility problems. Can you fix them?

- The header image has an accessibility issue, and so do the gallery images.
- You could take the header image further and implement it using CSS for arguably better accessibility. Why is this better, and what would a solution look like?

Try updating the live code below to recreate the finished example:

```html live-sample___html-a11y4
<header>
  <img alt="A star that I use to decorate my page" src="images/star.png" />
  <h1>Groovy images</h1>
</header>
<main>
  <img src="images/teapot.jpg" />
  <img src="images/football.jpg" />
</main>
```

```css live-sample___html-a11y4
.preview {
  width: 400px;
  margin: 0 auto;
}

main img {
  display: block;
  width: 250px;
  margin: 20px auto;
  box-shadow: 5px 5px 0 black;
}

header {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 20px;
}
```

{{EmbedLiveSample("html-a11y4")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/accessibility/tasks/html-css/html/html-a11y4-download.html) to work in your own editor or in an online editor.
