---
title: "Test your skills: Math"
slug: Learn/JavaScript/First_steps/Test_your_skills:_Math
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of the tests on this page is to assess whether you've understood the [Basic math in JavaScript — numbers and operators](/en-US/docs/Learn/JavaScript/First_steps/Math) article.

> [!NOTE]
> Click **"Play"** in the code blocks below to edit the examples in the MDN Playground.
> You can also copy the code (click the clipboard icon) and paste it into an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Math 1

Let's start out by testing your knowledge of basic math operators.
You will create four numeric values, add two together, subtract one from another, then multiply the results.
Finally, we need to write a check that proves that this value is an even number.

Try updating the live code below to recreate the finished example by following these steps:

1. Create four variables that contain numbers. Call the variables something sensible.
2. Add the first two variables together and store the result in another variable.
3. Subtract the fourth variable from the third and store the result in another variable.
4. Multiply the results from steps **2** and **3** and store the result in a variable called `finalResult`.
5. Check if `finalResult` is an even number using one of the [arithmetic operators](/en-US/docs/Learn/JavaScript/First_steps/Math#arithmetic_operators). Store the result (`0` for even, `1` for odd) in a variable called `evenOddResult`.

To pass this test, `finalResult` should have a value of `48` and `evenOddResult` should have a value of `0`.

```js live-sample___math1
let finalResult;

let evenOddResult;

// Add your code here

// Don't edit the code below here!

section.innerHTML = " ";
const para1 = document.createElement("p");
const finalResultCheck =
  finalResult === 48 ? `Yes, well done!` : `No, it is ${finalResult}`;
para1.textContent = `Is the finalResult 48? ${finalResultCheck}`;
const para2 = document.createElement("p");
const evenOddResultCheck =
  evenOddResult === 0
    ? "The final result is even!"
    : "The final result is odd. Hrm.";
para2.textContent = evenOddResultCheck;

section.appendChild(para1);
section.appendChild(para2);
```

{{EmbedLiveSample("math1")}}

<details>
<summary>Click here to show the solution</summary>

In this task you need to create four variables that contain numbers. The first two need to be added together and stored, while the fourth needs to be subtracted from the third and the result stored. The two results of these operations need to be multiplied together to create another result, 48, which should be stored in the variable `finalResult`.

Finally, you need to write a calculation that checks whether this number is even or odd, with the result stored in `evenOddCheck`. The operator you need here is modulo (`%`). If your value modulo 2 equals 0, you know it is even.

The answer should look something like this:

```js
const number1 = 4;
const number2 = 8;
const number3 = 12;
const number4 = 8;

const additionResult = number1 + number2;
const subtractionResult = number3 - number4;

finalResult = additionResult * subtractionResult;

evenOddResult = finalResult % 2;
```

This task also tests your variable naming abilities. An extra mark if the variables have sensible names that follow best practices (lower camel case, descriptive, not too long).

</details>

## Math 2

In the second task, you are provided with two calculations with the results stored in the variables `result` and `result2`.
You need to take the calculations, multiply them, and format the result to two decimal places.

Try updating the live code below to recreate the finished example by following these steps:

1. Multiply `result` and `result2` and assign the result back to `result` (use assignment shorthand).
2. Format `result` so that it has two decimal places and store it in a variable called `finalResult`.
3. Check the data type of `finalResult` using `typeof`. If it's a `string`, convert it to a `number` type and store the result in a variable called `finalNumber`.

To pass this test, `finalNumber` should have a result of `4633.33`.

```js live-sample___math2
// Final result should be 4633.33
// Add/update your code here

let result = 7 + 13 / 9 + 7;
let result2 = (100 / 2) * 6;

// Don't edit the code below here!

section.innerHTML = " ";
const para1 = document.createElement("p");
para1.textContent = `Your finalResult is ${finalResult}`;
const para2 = document.createElement("p");
const finalNumberCheck =
  typeof finalNumber === "number"
    ? "finalNumber is a number type. Well done!"
    : `Ooops! finalNumber is not a number.`;
para2.textContent = finalNumberCheck;

section.appendChild(para1);
section.appendChild(para2);
```

{{EmbedLiveSample("math2")}}

<details>
<summary>Click here to show the solution</summary>

In our second task for this article we need to consider operator precedence and use parentheses to make the first two calculations give the result we were expecting.

Next, we ideally need to use the multiplication assignment operator to multiply the two results together and then assign the product of this back to `result`.

After that we need to use the `toFixed()` method available on numbers to round `result` to 2 decimal places, storing the product of this in a `finalResult` variable.

Finally, using `typeof` we can test if a variable contains a string. We need to use `Number()` to convert `finalResult` to a number type. This final number needs to be stored in a variable called `finalNumber`.

The result should look something like this:

```js
let result = (7 + 13) / (9 + 7);
let result2 = 100 / (2 * 6);

result *= result2;

const finalResult = result.toFixed(2);

const finalNumber = Number(finalResult);
```

</details>

## Math 3

In the final task for this article, we want you to write some tests.
There are three groups, each consisting of a statement and two variables.
For each one, write a test that proves or disproves the statement made.
Store the results of those tests in variables called `weightComparison`, `heightComparison`, and `pwdMatch`, respectively.

```js live-sample___math3
// Statement 1: The elephant weighs less than the mouse
const eleWeight = 1000;
const mouseWeight = 2;

// Statement 2: The Ostrich is taller than the duck
const ostrichHeight = 2;
const duckHeight = 0.3;

// Statement 3: The two passwords match
const pwd1 = "stromboli";
const pwd2 = "stROmBoLi";

// Add your code here

// Don't edit the code below here!

section.innerHTML = " ";
const para1 = document.createElement("p");
const para2 = document.createElement("p");
const para3 = document.createElement("p");

const weightTest = weightComparison
  ? "True — elephants weigh less than mice!?"
  : "False — of course an elephant is heavier than a mouse!";
const heightTest = heightComparison
  ? "True — an ostrich is indeed taller than a duck!"
  : "False — apparently a duck is taller than an ostrich!?";
const pwdTest = pwdMatch
  ? "True — the passwords match."
  : "False — the passwords do not match; please check them";

para1.textContent = weightTest;
section.appendChild(para1);
para2.textContent = heightTest;
section.appendChild(para2);
para3.textContent = pwdTest;
section.appendChild(para3);
```

{{EmbedLiveSample("math3")}}

<details>
<summary>Click here to show the solution</summary>

This last task tests the student's ability to use comparison operators. Here we need to write some tests to show that mathematically prove or disprove the statements in the question.

The test results should be stored inside variables called `weightComparison`, `heightComparison`, and `pwdMatch`, respectively.

Your code should look something like this:

```js
const weightComparison = eleWeight < mouseWeight;

const heightComparison = ostrichHeight > duckHeight;

const pwdMatch = pwd1 === pwd2;
```

</details>
