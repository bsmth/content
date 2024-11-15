---
title: "Test your skills: Multimedia and embedding"
slug: Learn/HTML/Multimedia_and_embedding/Video_and_audio_content/Test_your_skills:_Multimedia_and_embedding
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of this skill test is to assess whether you understand how to [embed video and audio content in HTML](/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content), also using [object, iframe and other embedding technologies](/en-US/docs/Learn/HTML/Multimedia_and_embedding/Other_embedding_technologies).

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Task 1

In this task, we want you to embed a simple audio file onto the page. You need to:

- Add the path to the audio file to an appropriate attribute to embed it on the page. The audio is called `audio.mp3`, and it is in a folder inside the current folder called `media`.
- Add an attribute to make browsers display some default controls.
- Add some appropriate fallback text for browsers that don't support `<audio>`.

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/html/multimedia-and-embedding/tasks/media-embed/mediaembed1.html", '100%', 700)}}

<details>
<summary>Click here to show the solution</summary>

This task tests your ability to put together a simple audio player with a single source. Ideally the answer should look something like this:

```html
<h1>Basic audio embed</h1>

<audio src="media/audio.mp3" controls>
  <p>
    Your browser doesn't support HTML5 audio. Here is a
    <a href="media/audio.mp3">link to the audio</a> instead.
  </p>
</audio>
```

The filename and path must be correct for the audio to show up. The `controls` attribute should be included so we can easily play the audio, and the fallback text is also a best practice, although most browsers will support this now.

</details>

## Task 2

In this task, we want you to mark up a slightly more complex video player, with multiple sources, subtitles, and other features besides. You need to:

- Add an attribute to make browsers display some default controls.
- Add some appropriate fallback text for browsers that don't support `<video>`.
- Add multiple sources, containing the paths to the video files. The files are called `video.mp4` and `video.webm`, and are in a folder inside the current folder called `media`.
- Let the browser know in advance what video formats the sources point to, so it can make an informed choice of which one to download ahead of time.
- Give the `<video>` a width and height equal to its intrinsic size (320 by 240 pixels).
- Make the video muted by default.
- Display the text tracks contained in the `media` folder, in a file called `subtitles_en.vtt`, when the video is playing. You must explicitly set the type as subtitles, and the subtitle language to English.
- Make sure the readers can identify the subtitle language when they use the default controls.

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/html/multimedia-and-embedding/tasks/media-embed/mediaembed2.html", '100%', 700)}}

<details>
<summary>Click here to show the solution</summary>

In this next task we're doing something a bit more complex; a full-featured video player with multiple sources. The code would look something like this:

```html
<h1>Video embed</h1>

<video controls muted width="320" height="240">
  <source src="media/video.mp4" type="video/mp4" />
  <source src="media/video.webm" type="video/webm" />
  <track kind="subtitles" src="media/subtitles_en.vtt" srclang="en-US" />
  <p>
    Your browser doesn't support HTML5 video. Here is a
    <a href="media/video.mp4">link to the video</a> instead.
  </p>
</video>
```

Here we've got a number of things that need to be put in place:

- `controls` to make the controls appear.
- `width` and `height` as requested.
- `muted` to make sure no sound is played, as per the requirements.
- two separate `<source>` elements pointing to the two different video formats, to provide support in older browsers that don't support MP4 and instead support WebM. Each should be given a `type` attribute to indicate what the video's MIME type is, so the browser can tell up front if it can play with video without needing to start downloading it.
- A `<track>` element to display the subtitles, with appropriate `kind`, `src`, and `srclang` attributes.
- Suitable fallback content, as before.

Note that the subtitles will not load if you try to run the example locally, due to browser security policy. To see the subtitles you must run the example from an actual web server.

</details>

## Task 3

In this task, we want you to:

- Embed a PDF into the page. The PDF is called `my-pdf.pdf`, and is contained in the `media` folder.
- Go to a sharing site like YouTube or Google Maps, and embed a video or other media item into the page.

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/html/multimedia-and-embedding/tasks/media-embed/mediaembed3.html", '100%', 700)}}

<details>
<summary>Click here to show the solution</summary>

In task 3 the student needs to test embedding techniques.

The finished code would probably look like something this:

```html
<h1>Embedding</h1>

<object
  data="media/MyPDF.pdf"
  type="application/pdf"
  width="400"
  height="400"></object>

<hr />

<iframe
  width="560"
  height="315"
  src="https://www.youtube.com/embed/SB-qEYVdvXA"
  frameborder="0"
  allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen></iframe>
```

In the first example, you just need to look up the correct code to embed a PDF in the page, making sure you get the path to the PDF file correct.

In the second example, you'll need to go to YouTube, Google Maps, or a similar site, find the embed functionality, and copy over the embed code into the live example. This code will look markedly different depending on what service you use.

</details>
