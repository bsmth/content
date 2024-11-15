---
title: "Test your skills: Strings"
slug: Learn/JavaScript/First_steps/Test_your_skills:_Strings
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of this skill test is to assess whether you've understood our [Handling text — strings in JavaScript](/en-US/docs/Learn/JavaScript/First_steps/Strings) and [Useful string methods](/en-US/docs/Learn/JavaScript/First_steps/Useful_string_methods) articles.

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

> [!NOTE]
> In the examples below, if there is an error in your code it will be outputted into the results panel on the page, to help you try to figure out the answer (or into the browser's JavaScript console, in the case of the downloadable version).

## Strings 1

In our first strings task, we start off small. You already have half of a famous quote inside a variable called `quoteStart`; we would like you to:

1. Look up the other half of the quote, and add it to the example inside a variable called `quoteEnd`.
2. Concatenate the two strings together to make a single string containing the complete quote. Save the result inside a variable called `finalQuote`.

You'll find that you get an error at this point. Can you fix the problem with `quoteStart`, so that the full quote displays correctly?

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/javascript/introduction-to-js-1/tasks/strings/strings1.html", '100%', 400)}}

<details>
<summary>Click here to show the solution</summary>

The first task asks you to store a new string in a variable to go along with the existing one, which contains the missing half of the famous quote. Call the new variable you add `quoteEnd`.

You'll also need to escape the apostrophe in the existing string so that it doesn't throw an error.

Finally, you'll need to concatenate the two strings together, and store the result in a variable called `finalQuote`.

The answer should look something like this:

```js
const quoteStart = "Don't judge each day by the harvest you reap ";
const quoteEnd = "but by the seeds that you plant.";

const finalQuote = `${quoteStart}${quoteEnd}`;
```

</details>

## Strings 2

In this task you are provided with two variables, `quote` and `substring`, which contain two strings. We would like you to:

1. Retrieve the length of the quote, and store it in a variable called `quoteLength`.
2. Find the index position where `substring` appears in `quote`, and store that value in a variable called `index`.
3. Use a combination of the variables you have and available string properties/methods to trim down the original quote to "I do not like green eggs and ham.", and store it in a variable called `revisedQuote`.

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/javascript/introduction-to-js-1/tasks/strings/strings2.html", '100%', 400)}}

<details>
<summary>Click here to show the solution</summary>

Next up, task 2 requires the student to:

- Check the length of the provided string using `.length`, and store the result in a variable called `quoteLength`.
- Find the index of the substring 'green eggs and ham' using `.indexOf` and store it in `index`.
- Use a combination of the variables you have, `.length`, and `.slice()`, to trim down the original quote to 'I do not like green eggs and ham.', and store it in `revisedQuote`.

```js
const quote = "I do not like green eggs and ham. I do not like them, Sam-I-Am.";
const substring = "green eggs and ham";

const quoteLength = quote.length;

const index = quote.indexOf(substring);

const revisedQuote = quote.slice(0, index + substring.length + 1);
```

</details>

## Strings 3

In the next string task, you are given the same quote that you ended up with in the previous task, but it is somewhat broken! We want you to fix and update it, like so:

1. Change the casing to correct sentence case (all lowercase, except for upper case first letter). Store the new quote in a variable called `fixedQuote`.
2. In `fixedQuote`, replace "green eggs and ham" with another food that you really don't like.
3. There is one more small fix to do — add a period to the end of the quote, and save the final version in a variable called `finalQuote`.

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/javascript/introduction-to-js-1/tasks/strings/strings3.html", '100%', 400)}}

<details>
<summary>Click here to show the solution</summary>

For our next string task, we return to our Green Eggs and Ham revised quote, which someone has messed up. You need to:

- Fix the casing. The best way to do this is to put it all in lower case using `.toLowerCase()`, and then put the first letter in uppercase using `replace()`, `slice()`, and `toUpperCase()`. Store the new quote in `fixedQuote`.
- Replace `green eggs and ham` with whatever food you really don't like using `replace()`.
- Add a full stop to the end of the sentence using some means.

Your code should look something like this:

```js
const quote = "I dO nOT lIke gREen eGgS anD HAM";

let fixedQuote = quote.toLowerCase();
const firstLetter = fixedQuote.slice(0, 1);
fixedQuote = fixedQuote.replace(firstLetter, firstLetter.toUpperCase());

fixedQuote = fixedQuote.replace("green eggs and ham", "pickled onions");

const finalQuote = `${fixedQuote}.`;
```

</details>

## Strings 4

In the final string task, we have given you the name of a theorem, two numeric values, and an incomplete string (the bits that need adding are marked with asterisks (`*`)). We want you to change the value of the string as follows:

1. Change it from a regular string literal into a template literal.
2. Replace the four asterisks with four template literal placeholders. These should be:

   1. The name of the theorem.
   2. The two number values we have.
   3. The length of the hypotenuse of a right-angled triangle, given that the two other side lengths are the same as the two values we have. You'll need to look up how to calculate this from what you have. Do the calculation inside the placeholder.

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/javascript/introduction-to-js-1/tasks/strings/strings4.html", '100%', 400)}}

<details>
<summary>Click here to show the solution</summary>

Our final string task looks at your ability to use template literals. Your answer is expected to take the existing string literal, `myString`, turn it into a template literal, and include four placeholders in place of the asterisks:

- The `theorem` string.
- The value of `a`.
- The value of `b`.
- The length of the hypotenuse, if `a` and `b` are the lengths of the two shortest sides of a right-angled triangle. You can use pythagoras' theorem to work this out.

Your code should look something like this:

```js
const theorem = "Pythagorean theorem";

const a = 5;
const b = 8;

const myString = `Using ${theorem}, we can work out that that if the two shortest sides of a right-angled triangle have lengths of ${a} and ${b}, the length of the hypotenuse is ${Math.sqrt(
  a ** 2 + b ** 2,
)}.`;
```

You could use a different form of the fourth placeholder, such as `Math.sqrt(Math.pow(a, 2) + Math.pow(b, 2))` or `${ Math.sqrt((a * a) + (b * b)) }`.

</details>
