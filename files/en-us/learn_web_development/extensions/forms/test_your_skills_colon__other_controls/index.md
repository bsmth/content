---
title: "Test your skills: Other controls"
slug: Learn_web_development/Extensions/Forms/Test_your_skills:_Other_controls
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of this skill test is to assess whether you've understood our [Other form controls](/en-US/docs/Learn_web_development/Extensions/Forms/Other_form_controls) article.

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Other controls 1

In our first "other controls" assessment, we'll get you to create a multi-line text input.

1. Create a basic multi-line text input.
2. Associate it semantically with the provided "Comment" label.
3. Give the input 35 columns, and 10 rows of space in which to add comments.
4. Give the comments a maximum length of 100 characters.

To create the input, update the HTML code in the editor below:

```html live-sample___other-controls1
<form>
  <h2>Enter your comment</h2>
  <ul>
    <li>
      <label for="name">Name:</label>
      <input id="name" name="name" type="text" />
    </li>
    <li>
      <label for="comment">Comment:</label>
      <!-- add your input here  -->
    </li>
    <li>
      <button>Submit comment</button>
    </li>
  </ul>
</form>
```

{{EmbedLiveSample("other-controls1")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/html/forms/tasks/other-controls/other-controls1-download.html) to work in your own editor or in an online editor.

## Other controls 2

Now it's time to have a go at implementing a drop-down select menu, to allow a user to pick their favorite food from the choices provided.

1. Create your basic select box structure.
2. Associate it semantically with the provided "food" label.
3. Inside the list, split the choices up into 2 subgroups — "mains" and "snacks".

To create the menu, update the HTML code in the editor below:

```html live-sample___other-controls2
<form>
  <ul>
    <li>
      <label for="food">Pick your favorite food:</label>

      Salad Curry Pizza Fajitas Biscuits Crisps Fruit Breadsticks
    </li>
    <li>
      <button>Submit choice</button>
    </li>
  </ul>
</form>
```

{{EmbedLiveSample("other-controls2")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/html/forms/tasks/other-controls/other-controls2-download.html) to work in your own editor or in an online editor.

## Other controls 3

In our final task of this set, we start with much the same list of food choices. However, this time we want to do things differently:

1. Create a basic text input that is semantically associated with the provided label.
2. Put the food choices into a list that can be associated with a form input.
3. Associate the list with your text input, so that when you type characters, any of the list options that match the character sequence are given in a dropdown list as autocomplete suggestions.

To create the input, update the HTML code in the editor below:

```html live-sample___other-controls3
<form>
  <ul>
    <li>
      <label for="food">Enter your favorite food:</label>

      Salad Curry Pizza Fajitas Biscuits Crisps Fruit Breadsticks
    </li>
    <li>
      <button>Submit choice</button>
    </li>
  </ul>
</form>
```

{{EmbedLiveSample("other-controls3")}}

> [!CALLOUT]
>
> [Download the starting point for this task](https://github.com/mdn/learning-area/blob/main/html/forms/tasks/other-controls/other-controls3-download.html) to work in your own editor or in an online editor.
