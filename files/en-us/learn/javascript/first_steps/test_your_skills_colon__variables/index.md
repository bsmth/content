---
title: "Test your skills: variables"
slug: Learn/JavaScript/First_steps/Test_your_skills:_variables
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of this skill test is to assess whether you've understood our [Storing the information you need — Variables](/en-US/docs/Learn/JavaScript/First_steps/Variables) article.

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
> If there is an error in your code, it will be logged into the results panel on this page or in the JavaScript console.
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Variables 1

In this task we want you to:

- Declare a variable called `myName`.
- Initialize `myName` with a suitable value, on a separate line (you can use your actual name, or something else).
- Declare a variable called `myAge` and initialize it with a value, on the same line.

Try updating the live code below to recreate the finished example:

```js live-sample___variables1
// Add your code here

// Don't edit the code below here!

section.innerHTML = " ";
const para1 = document.createElement("p");
para1.textContent = myName;
const para2 = document.createElement("p");
para2.textContent = myAge;
section.appendChild(para1);
section.appendChild(para2);
```

{{EmbedLiveSample("variables1")}}

<details>
<summary>Click here to show the solution</summary>

This task covers basic understanding of declaring a variable with a value, and initializing it — both separately and at the same time. Ideally your code should look something like this:

```js
let myName;
myName = "Chris";
let myAge = 42;
```

`let` is ideal for both declarations. `const` is not really appropriate, as such values might change, and it won't work in the first instance. `var` is not OK.

The `myAge` value will work whether you've initialised it with a numeric (no quotes) or string (quotes) value, however it is a numeric value, so using quotes for it isn't correct.

</details>

## Variables 2

In this task you need to add a new line to correct the value stored in the existing `myName` variable to your own name.

Try updating the live code below to recreate the finished example:

```js live-sample___variables2
// Add your code here

let myName = "Paul";

// Don't edit the code below here!

section.innerHTML = " ";
const para = document.createElement("p");
para.textContent = myName;
section.appendChild(para);
```

{{EmbedLiveSample("variables2")}}

<details>
<summary>Click here to show the solution</summary>

In task 2 the student needs to add a new line to correct the `myName` variable value so that it outputs their name on the screen.

The finished code should look something like this:

```js
let myName = "Paul";
myName = "Chris";
```

</details>

## Variables 3

The final task for now — in this case you are provided with some existing code, which has two errors present in it. The results panel should be outputting the name `Chris`, and a statement about how old Chris will be in 20 years' time. How can you fix the problem and correct the output?

Try updating the live code below to recreate the finished example:

```js live-sample___variables3
// Add your code here

const myName = "Default";
myName = "Chris";

let myAge = "42";

// Don't edit the code below here!

section.innerHTML = " ";
const para1 = document.createElement("p");
const para2 = document.createElement("p");
para1.textContent = myName;
para2.textContent = `In 20 years, I will be ${myAge + 20}`;
section.appendChild(para1);
section.appendChild(para2);
```

{{EmbedLiveSample("variables3")}}

<details>
<summary>Click here to show the solution</summary>

The last task in this article focuses around fixing some variable-related errors. Basically:

1. The `myName` variable is not being outputted correctly because it is being declared once using `const`, and then an attempt is being made to change the value.
2. The result of the sum is not being outputted correctly because the `myAge` variable is being declared as a number. It needs to have the quotes removed.

The solution should look something like this:

```js
let myName = "Default";
myName = "Chris";

let myAge = 42;
```

</details>
