---
title: "Test your skills: HTML5 controls"
slug: Learn/Forms/Test_your_skills:_HTML5_controls
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of this skill test is to assess whether you've understood our [The HTML5 input types](/en-US/docs/Learn/Forms/HTML5_input_types) article.

> [!NOTE]
> Click **"Play"** in the code blocks below to edit the examples in the MDN Playground.
> You can also copy the code (click the clipboard icon) and paste it into an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## HTML controls 1

First, let's explore some input types. Create appropriate inputs for a user to update their details for:

1. Email
2. Website
3. Phone number
4. Favorite color

Try updating the live code below to recreate the finished example:

```html live-sample___html5-controls1
<form>
  <h2>Edit your preferences</h2>
  <ul>
    <li>
      <label for="email">Email</label>
    </li>
    <li>
      <label for="website">Website</label>
    </li>
    <li>
      <label for="phone">Phone number</label>
    </li>
    <li>
      <label for="fave-color">Favorite color</label>
    </li>
    <li>
      <button>Update preferences</button>
    </li>
  </ul>
</form>
```

{{EmbedLiveSample("html5-controls1")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/html/forms/tasks/html5-controls/html5-controls1-download.html) to work in your own editor or in an online editor.

## HTML controls 2

Next, we want you to implement a slider control to allow the user to choose a maximum number of people to invite to their party.

1. Implement a basic slider control to go along with the provided label.
2. Give it a minimum value of 1, maximum value of 30, initial value of 10 and element `id` of `max-invite`.
3. Create a corresponding output element to put the current value of the slider into. Give it a class of `invite-output`, and semantically associate it with the input. If you do this correctly, the JavaScript included on the page will automatically update the output value when the slider is moved.

Try updating the live code below to recreate the finished example:

```html live-sample___html5-controls2
<form>
  <ul>
    <li>
      <label for="max-invite">Select maximum number of invitations</label>
    </li>
    <li>
      <button>Submit</button>
    </li>
  </ul>
</form>
```

{{EmbedLiveSample("html5-controls2")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/html/forms/tasks/html5-controls/html5-controls2-download.html) to work in your own editor or in an online editor.
