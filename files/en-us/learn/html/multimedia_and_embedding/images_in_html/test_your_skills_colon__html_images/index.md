---
title: "Test your skills: HTML images"
slug: Learn/HTML/Multimedia_and_embedding/Images_in_HTML/Test_your_skills:_HTML_images
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of this skill test is to assess whether you understand [images and how to embed them in HTML](/en-US/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML).

> [!NOTE]
> Click **"Play"** in the code blocks below to edit the examples in the MDN Playground.
> You can also copy the code (click the clipboard icon) and paste it into an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Task 1

In this task, we want you to embed a simple image of some Blueberries into the page. You need to:

- Add the path to the image to an appropriate attribute to embed it on the page. The image is called `blueberries.jpg`, and it is in a folder inside the current folder called `images`.
- Add some alternative text to an appropriate attribute to describe the image, for people that cannot see it.
- Give the `<img>` element an appropriate `width` and `height` so that it displays at the correct {{glossary("aspect ratio")}}, and enough space is left on the page to display it. The image's {{glossary("intrinsic size")}} is 615 x 419 pixels.

Try updating the live code below to recreate the finished example:

```html live-sample___images1
<h1>Basic image embed</h1>
<img />
```

```css live-sample___images1
img {
  border: 1px solid black;
}
```

{{EmbedLiveSample("images1")}}

<details>
<summary>Click here to show the solution</summary>

This task tests your ability to embed a simple image on the page, give it some alternative text, and give it some `width` and `height` attributes. Ideally the answer should look something like this:

```html
<h1>Basic image embed</h1>

<img
  src="images/blueberries.jpg"
  alt="A pile of blueberries, small, round, blue berries"
  width="615"
  height="419" />
```

The filename and path must be correct for the image to show up. The `alt` text should describe the visual appearance of image for those that can't see it. Finally, the `width` and `height` attributes should contain the same values as the image's intrinsic width and height, so it displays at the correct size.

</details>

## Task 2

In this task, you already have a full-featured image, but we'd like you to add a tooltip that appears when the image is moused over. You should put some appropriate information into the tooltip.

Try updating the live code below to recreate the finished example:

```html live-sample___images2
<h1>Basic image title</h1>

<img alt="Several tall evergreen trees called larches" src="larch.jpg" />
```

```css live-sample___images2
img {
  border: 1px solid black;
  max-width: 100%;
}
```

{{EmbedLiveSample("images2")}}

<details>
<summary>Click here to show the solution</summary>

Here the student needs to add a `title` to the `<image>` element to create a tooltip that appears when moused over. The code would look something like this:

```html
<h1>Basic image title</h1>

<img
  src="larch.jpg"
  alt="Several tall evergreen trees called larches"
  title="Number 1 in Monty Python's How to recognise different trees from quite a long way away" />
```

Because screenreader support is unreliable and potentially unhelpful, information contained in the `title` attributes should be non-essential. Here were are just having a bit of fun.

</details>

## Task 3

In this task, you are provided with both a full-featured image and some caption text. What you need to do here is add elements that will associate the image with the caption.

Try updating the live code below to recreate the finished example:

```html live-sample___images3
<h1>Image and caption</h1>

<img
  alt="An abstract flaming fox wrapping around a blue sphere"
  height="460"
  src="firefox.png"
  width="446" />
The Firefox logo, newly abstracted for 2019!
```

{{EmbedLiveSample("images3")}}

<details>
<summary>Click here to show the solution</summary>

In task 3 the student needs to create an image that is associated with a caption inside the HTML itself.

The finished would probably look like this:

```html
<h1>Image and caption</h1>

<figure>
  <img
    src="firefox.png"
    alt="An abstract flaming fox wrapping around a blue sphere"
    width="446"
    height="460" />
  <figcaption>The Firefox logo, newly abstracted for 2019!</figcaption>
</figure>
```

Note that the caption should contain additional information, and not just repeat the image description found in the `alt` text.

</details>
