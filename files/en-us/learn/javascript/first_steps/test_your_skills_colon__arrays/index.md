---
title: "Test your skills: Arrays"
slug: Learn/JavaScript/First_steps/Test_your_skills:_Arrays
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of this skill test is to assess whether you've understood our [Arrays](/en-US/docs/Learn/JavaScript/First_steps/Arrays) article.

> [!NOTE]
> Click **"Play"** in the code blocks below to edit the examples in the MDN Playground.
> You can also copy the code (click the clipboard icon) and paste it into an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## Arrays 1

Let's start off with some basic array practice. In this task we'd like you to create an array of three items, stored inside a variable called `myArray`. The items can be anything you want — how about your favorite foods or bands?

Next, modify the first two items in the array using simple bracket notation and assignment. Then add a new item to the beginning of the array.

Try updating the live code below to recreate the finished example:

```js live-sample___arrays1
// Add your code here

// Don't edit the code below here!

section.innerHTML = " ";
let para1 = document.createElement("p");
para1.textContent = `Array: ${myArray}`;

section.appendChild(para1);
```

{{EmbedLiveSample("arrays1")}}

<details>
<summary>Click here to show the solution</summary>

We'll start off simple; the first thing you need to do here is create an array of three items. Choose whatever items you like — your favourite bands or foods, perhaps? Store in a variable called `myArray`.

Next, modify the first two items in the array to some different items, using simple bracket notation, e.g. `myArray[0] = 'pizza'`.

Last of all, add an item to the start of the array using `.unshift()`.

The answer should look something like this:

```js
let myArray = ["cats", "dogs", "chickens"];

myArray[0] = "horses";
myArray[1] = "pigs";

myArray.unshift("crocodiles");
```

</details>

## Arrays 2

Now let's move on to another task. Here you are provided with a string to work with. We'd like you to:

1. Convert the string into an array, removing the `+` characters in the process. Save the result in a variable called `myArray`.
2. Store the length of the array in a variable called `arrayLength`.
3. Store the last item in the array in a variable called `lastItem`.

Try updating the live code below to recreate the finished example:

```js live-sample___arrays2
// Add your code here

let myString = "Ryu+Ken+Chun-Li+Cammy+Guile+Sakura+Sagat+Juri";

// Don't edit the code below here!

section.innerHTML = " ";
let para1 = document.createElement("p");
para1.textContent = `Array: ${myArray}`;

let para2 = document.createElement("p");
para2.textContent = `The length of the array is ${arrayLength}.`;

let para3 = document.createElement("p");
para3.textContent = `The last item in the array is "${lastItem}".`;

section.appendChild(para1);
section.appendChild(para2);
section.appendChild(para3);
```

{{EmbedLiveSample("arrays2")}}

<details>
<summary>Click here to show the solution</summary>

Moving on, the next task provides a string for you to work on.

Here you are expected to start by splitting the string into an array using `.split('+')`. Store the array in `myArray`.

Next, store the length of the array (`myArray.length`) in a variable called `arrayLength`.

Last up, retrieve the last item in the array with `myArray[myArray.length - 1]`; store it in `lastItem`.

The example should look something like this:

```js
let myString = "Ryu+Ken+Chun-Li+Cammy+Guile+Sakura+Sagat+Juri";

let myArray = myString.split("+");

let arrayLength = myArray.length;

let lastItem = myArray[arrayLength - 1];
```

</details>

## Arrays 3

For this array task, we provide you with a starting array, and you will work in somewhat the opposite direction. You need to:

1. Remove the last item in the array.
2. Add two new names to the end of the array.
3. Go over each item in the array and add its index number after the name inside parentheses, for example `Ryu (0)`. Note that we don't teach how to do this in the Arrays article, so you'll have to do some research.
4. Finally, join the array items together in a single string called `myString`, with a separator of `"-"`.

Try updating the live code below to recreate the finished example:

```js live-sample___arrays3
let myArray = [
  "Ryu",
  "Ken",
  "Chun-Li",
  "Cammy",
  "Guile",
  "Sakura",
  "Sagat",
  "Juri",
];

// Add your code here

// Don't edit the code below here!

section.innerHTML = " ";

let para1 = document.createElement("p");
para1.textContent = myString;

section.appendChild(para1);
```

{{EmbedLiveSample("arrays3")}}

<details>
<summary>Click here to show the solution</summary>

You should start by popping the last item off the array using `myArray.pop()`.

Next, add two new names to the end of the array using `myArray.push()`

For an added challenge, you'll need to use `.forEach()` or some kind of loop (we didn't cover these in the array article, so look them up) to go over each item in the array and add its index number after the name inside parentheses. Note that when using `forEach` you are performing operations on a copy of the array elements, not the array elements themselves, so you can't change them directly — you have to create the new array item and copy it back over.

Finally you need to stitch the array items together into a string using `myArray.join(' - ')`, and store the result in `myString`.

```js
let myArray = [
  "Ryu",
  "Ken",
  "Chun-Li",
  "Cammy",
  "Guile",
  "Sakura",
  "Sagat",
  "Juri",
];

myArray.pop();

myArray.push("Zangief");
myArray.push("Ibuki");

myArray.forEach(function (element, index) {
  let newElement = `${element} (${index})`;
  myArray[index] = newElement;
});

let myString = myArray.join(" - ");
```

</details>

## Arrays 4

For this array task, we provide you with a starting array listing the names of some birds.

- Find the index of the `"Eagles"` item, and use that to remove the `"Eagles"` item.
- Make a new array from this one, called `eBirds`, that contains only birds from the original array whose names begin with the letter "E". Note that {{jsxref("String.prototype.startsWith()", "startsWith()")}} is a great way to check whether a string starts with a given character.

If it works, you should see `"Emus,Egrets"` appear in the page.

```js live-sample___arrays4
const birds = ["Parrots", "Falcons", "Eagles", "Emus", "Caracaras", "Egrets"];

// Add your code here

// Don't edit the code below here!

section.innerHTML = " ";

const para1 = document.createElement("p");
para1.textContent = eBirds;

section.appendChild(para1);
```

{{EmbedLiveSample("arrays4")}}

<details>
<summary>Click here to show the solution</summary>

You should start by finding the index of `"Eagles"`, using `birds.indexOf()`.

Next, use the index with `birds.splice()` to remove the `"Eagles"` item.

Finally, you can use `birds.filter()` to get an array containing only birds starting with "E".

The function passed to `filter()` can use `bird.startsWith()` to test whether the bird starts with "E".

```js
const eaglesIndex = birds.indexOf("Eagles");
birds.splice(eaglesIndex, 1);

function startsWithE(bird) {
  return bird.startsWith("E");
}
const eBirds = birds.filter(startsWithE);
```

</details>
