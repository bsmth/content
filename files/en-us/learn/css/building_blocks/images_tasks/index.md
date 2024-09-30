---
title: "Test your skills: Images and form elements"
slug: Learn/CSS/Building_blocks/Images_tasks
page-type: learn-module-assessment
---

{{LearnSidebar}}

The aim of this skill test is to assess whether you understand how special elements like [images, media and form elements are treated in CSS](/en-US/docs/Learn/CSS/Building_blocks/Images_media_form_elements).

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Task 1

In this task, you have an image that is overflowing the box. We want the image to scale down to fit inside the box without any extra white space, but we do not mind if some part of the image is cropped.

Your final result should look like the image below:

![An image in a box](mdn-images-object-fit.png)

Try updating the live code below to recreate the finished example:

```html live-sample___object-fit
<div class="box">
  <img alt="balloons" src="balloons.jpg" />
</div>
```

```css live-sample___object-fit
img {
}
```

{{EmbedLiveSample("object-fit")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/images/object-fit-download.html) to work in your own editor or in an online editor.

## Task 2

In this task, you have a simple form. Your task is to make the following changes:

- Use attribute selectors to target the search field and button inside `.myform`.
- Make the form field and button use the same text size as the rest of the form.
- Give the form field and button 10 px of padding.
- Give the button a background of `rebeccapurple`, white foreground, no border and rounded corners of 5px.

Your final result should look like the image below:

![A single line form](mdn-images-form.png)

Try updating the live code below to recreate the finished example:

```html live-sample___form
<form action="" class="myform" method="post">
  <div>
    <label for="fldSearch">Keywords</label>
    <input id="fldSearch" name="keywords" type="search" />
    <input name="btnSubmit" type="submit" value="Search" />
  </div>
</form>
```

```css live-sample___form
.myform {
  border: 2px solid #000;
  padding: 5px;
}
```

{{EmbedLiveSample("form")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/css-examples/blob/main/learn/tasks/images/form-download.html) to work in your own editor or in an online editor.
