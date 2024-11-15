---
title: "Test your skills: Form validation"
slug: Learn/Forms/Test_your_skills:_Form_validation
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of this skill test is to assess whether you've understood our [Client-side form validation](/en-US/docs/Learn/Forms/Form_validation) article.

> [!NOTE]
> Click **"Play"** in the code blocks below to edit the examples in the MDN Playground.
> You can also copy the code (click the clipboard icon) and paste it into an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Form validation 1

In this task, we are providing you with a simple support query form, and we want you to add some validation features to it:

1. Make all of the input fields mandatory to complete before the form can be submitted.
2. Change the type of the "Email address" and "Phone number" fields to make the browser apply some more specific validation suitable for the data being asked for.
3. Give the "User name" field a required length of between 5 and 20 characters, the "Phone number" field a maximum length of 15 characters, and the "Comment" field a maximum length of 200 characters.

Try submitting your form — it should refuse to submit until the above constraints are followed, and give suitable error messages. To help, you might want to consider adding some simple CSS to show when a form field is valid or invalid.

<details>
<summary>Click here to show the solution</summary>

In this task, we are providing you with a simple support query form, and we want you to add some validation features to it:

1. Make all of the input fields mandatory to complete before the form can be submitted. This is simple — just use the `required` attribute.
2. Change the type of the "Email address" and "Phone number" fields to make the browser apply some more specific validation suitable for the data being asked for. The `email` and `tel` types are most suitable for these fields.
3. Give the "User name" field a required length of between 5 and 20 characters, the "Phone number" field a maximum length of 15 characters, and the "Comment" field a maximum length of 200 characters. The first and last of these three take string data, so require the `minlength` and `maxlength` attributes. The second one is slightly more tricky — you'd think a phone number would constitute a numeric field, so would require the `max` attribute, but it is the number of digits in a phone number that matter, not the value of the number. This one requires `maxlength` too.

Try submitting your form — it should refuse to submit until the above constraints are followed, and give suitable error messages. To help, you might want to consider adding some simple CSS to show when a form field is valid or invalid.

The finished markup should look something like this:

```html
<form>
  <h2>Enter your support query</h2>
  <ul>
    <li>
      <label for="uname">User name:</label>
      <input
        type="text"
        name="uname"
        id="uname"
        required
        minlength="5"
        maxlength="20" />
    </li>
    <li>
      <label for="email">Email address:</label>
      <input type="email" name="email" id="email" required />
    </li>
    <li>
      <label for="phone">Phone number:</label>
      <input type="tel" name="phone" id="phone" required maxlength="15" />
    </li>
    <li>
      <label for="comment">Comment:</label>
      <textarea name="comment" id="comment" required maxlength="200"></textarea>
    </li>
    <li>
      <button>Submit comment</button>
    </li>
  </ul>
</form>
```

</details>

## Form validation 2

Now we want you to take the same form you saw in the previous task (use your previous answer if you want to), and add some more specific pattern validation to the first three fields using regular expressions.

1. All of the user names in our application consist of a single letter, followed by a dot, followed by three or more letters or numbers. All letters should be lowercase.
2. All of the email addresses for our users consist of one or more letters (lower or upper case) or numbers, followed by "@bigcorp.eu".
3. Remove the length validation from the phone number field if it is present, and set it so that it accepts 10 digits — either 10 digits in a row, or a pattern of three digits, three digits, then four digits, separated by either spaces, dashes, or dots.

> [!NOTE]
> Regular expressions are really challenging if you are new to them, but don't despair — have a go and see where you get to; there is no shame in asking for some help. You can find everything you need to answer these questions at our [regular expression reference](/en-US/docs/Web/JavaScript/Guide/Regular_expressions), and by searching on [Stack Overflow](https://stackoverflow.com/).

Again, to help you might want to consider adding some simple CSS to show when a form field is valid or invalid.

<details>
<summary>Click here to show the solution</summary>

Now we want you to take the same form you saw in the previous task (use your previous answer if you want to), and add some more specific pattern validation to the first three fields.

1. All of the user names in our application consist of a single letter, followed by a dot, followed by three or more letters or numbers. All letters should be lowercase. This will work — `pattern="[a-z]{1}\.[a-z0-9]{3,}"`.
2. All of the email addresses for our users consist of one or more letters (lower or upper case) or numbers, followed by "@bigcorp.eu". This will work — `[a-zA-Z0-9]+@bigcorp\.eu`.
3. Remove the length validation from the phone number field if it is present, and set it so that it accepts 10 digits — either 10 digits in a row, or a pattern of three digits, three digits, then four digits, separated by either spaces, dashes, or dots. The following will work for this — `pattern="[0-9]{10}|[0-9]{3}[\-. ][0-9]{3}[\-. ][0-9]{4}"` — although bear in mind that it will work if the separators are not all the same (e.g. one dot and two dashes). This is OK for the purposes of this task — you'd be unlikely to get people entering numbers like this anyway, and it would be easy to sanitize the data on the server.

Try submitting your form — it should refuse to submit until the above constraints are followed, and give suitable error messages. To help, you might want to consider adding some simple CSS to show when a form field is valid or invalid.

The finished markup should look something like this:

```html
<form>
  <h2>Enter your support query</h2>
  <ul>
    <li>
      <label for="uname">User name:</label>
      <input
        type="text"
        name="uname"
        id="uname"
        required
        pattern="[a-z]{1}\.[a-z0-9]{3,}" />
    </li>
    <li>
      <label for="email">Email address:</label>
      <input
        type="text"
        name="email"
        id="email"
        required
        pattern="[A-z0-9]+@bigcorp.eu" />
    </li>
    <li>
      <label for="phone">Phone number:</label>
      <input
        type="text"
        name="phone"
        id="phone"
        required
        pattern="[0-9]{10}|[0-9]{3}[\-. ][0-9]{3}[\-. ][0-9]{4}" />
    </li>
    <li>
      <label for="comment">Comment:</label>
      <textarea name="comment" id="comment" required> </textarea>
    </li>
    <li>
      <button>Submit comment</button>
    </li>
  </ul>
</form>
```

</details>

## Form validation 3

In our final task for this set, we are providing you with a similar example to what you saw in the accompanying article — a simple email address entry input. We would like you to use the constraint validation API, plus some form validation attributes, to program some custom error messages.

1. Make the input mandatory to fill in, and give it a minimum length of 10 characters.
2. Add an event listener that checks whether the inputted value is an email address, and whether it is long enough. If it doesn't look like an email address or is too short, provide the user with appropriate custom error messages.

<details>
<summary>Click here to show the solution</summary>

In our final task for this set, we are providing you with a similar example to what you saw in the accompanying article — a simple email address entry input. We would like you to use the constraint validation API, plus some form validation attributes, to program some custom error messages.

1. Make the input mandatory to fill in, and give it a minimum length of 10 characters.
2. Add an event listener that checks whether the inputted value is an email address, and whether it is long enough. If it doesn't look like an email address or is too short, provide the user with appropriate custom error messages.

The finished markup should look something like this:

```html
<form>
  <label for="mail">
    I would like you to provide me with an email address:
  </label>
  <input type="email" id="mail" name="mail" required minlength="10" />
  <button>Submit</button>
</form>
```

And the JavaScript should look something like this:

```js
const email = document.getElementById("mail");

email.addEventListener("input", function (event) {
  if (email.validity.typeMismatch) {
    email.setCustomValidity("I am expecting an email address!");
  } else if (email.validity.tooShort) {
    email.setCustomValidity("Your email address is too short!!");
  } else {
    email.setCustomValidity("");
  }
});
```

</details>
