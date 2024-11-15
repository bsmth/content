---
title: "Test your skills: Events"
slug: Learn/JavaScript/Building_blocks/Test_your_skills:_Events
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of this skill test is to assess whether you've understood our [Introduction to events](/en-US/docs/Learn/JavaScript/Building_blocks/Events) article.

> [!NOTE]
> You can try solutions by downloading the code and putting it in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
> If there is an error, it will be logged in the results panel on the page or into the browser's JavaScript console to help you.
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## DOM manipulation: considered useful

Some of the questions below require you to write some [DOM](/en-US/docs/Glossary/DOM) manipulation code to complete them — such as creating new HTML elements, setting their text contents to equal specific string values, and nesting them inside existing elements on the page — all via JavaScript.

We haven't explicitly taught this yet in the course, but you'll have seen some examples that make use of it, and we'd like you to do some research into what DOM APIs you need to successfully answer the questions. A good starting place is our [Manipulating documents](/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Manipulating_documents) tutorial.

## Events 1

In our first events-related task, you need to create a simple event handler that causes the text inside the button (`btn`) to change when it is clicked on, and change back when it is clicked again.

The HTML should not be changed; just the JavaScript.

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/javascript/building-blocks/tasks/events/events1.html", '100%', 400)}}

<details>
<summary>Click here to show the solution</summary>

In our first events-related task, you need to create a simple event handler that causes the text inside the button to change when it is clicked on, and change back when it is clicked again.

The HTML should not be changed; just the JavaScript.

The finished code should look something like this:

```js
const btn = document.querySelector("button");

btn.addEventListener("click", () => {
  if (btn.className === "on") {
    btn.textContent = "Machine is off";
    btn.className = "off";
  } else {
    btn.textContent = "Machine is on";
    btn.className = "on";
  }
});
```

</details>

## Events 2

Now we'll look at keyboard events. To pass this assessment you need to build an event handler that moves the circle around the provided canvas when the WASD keys are pressed on the keyboard. The circle is drawn with the function `drawCircle()`, which takes the following parameters as inputs:

- `x` — the x coordinate of the circle.
- `y` — the y coordinate of the circle.
- `size` — the radius of the circle.

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/javascript/building-blocks/tasks/events/events2.html", '100%', 650)}}

<details>
<summary>Click here to show the solution</summary>

Now we'll look at keyboard events. To pass this assessment you need to build an event handler that moves the circle around the provided canvas when the WASD keys are pressed on the keyboard. The circle is drawn with the function `drawCircle()`.

The finished code should look something like this:

```js
const canvas = document.querySelector("canvas");
const ctx = canvas.getContext("2d");

function drawCircle(x, y, size) {
  ctx.fillStyle = "white";
  ctx.fillRect(0, 0, canvas.width, canvas.height);

  ctx.beginPath();
  ctx.fillStyle = "black";
  ctx.arc(x, y, size, 0, 2 * Math.PI);
  ctx.fill();
}

let x = 50;
let y = 50;
const size = 30;

drawCircle(x, y, size);

// Add your code here

window.addEventListener("keydown", (e) => {
  switch (e.key) {
    case "a":
      x -= 2;
      break;
    case "d":
      x += 2;
      break;
    case "w":
      y -= 2;
      break;
    case "s":
      y += 2;
      break;
  }

  drawCircle(x, y, size);
});
```

</details>

## Events 3

In the next events-related task, you need to set an event listener on the `<button>`s' parent element (`<div class="button-bar"> … </div>`), which when invoked by clicking any of the buttons will set the background of the `button-bar` to the color contained in the button's `data-color` attribute.

We want you to solve this without looping through all the buttons and giving each one their own event listener.

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/javascript/building-blocks/tasks/events/events3.html", '100%', 600)}}

<details>
<summary>Click here to show the solution</summary>

Our final events-related task involves making use of bubbling and event objects. You need to set a click listener on the buttons' parent element, which when invoked by clicking any of the buttons will use `e.target` to grab the `data-color` attribute of the particular button that was clicked, and set the background of the `button-bar` to that color.

You should be able to solve this without looping through all the buttons and giving each one their own event listener.

The code should look like this:

```js
const buttonBar = document.querySelector(".button-bar");

// Add your code here

function setColor(e) {
  buttonBar.style.backgroundColor = e.target.getAttribute("data-color");
}

buttonBar.addEventListener("click", setColor);
```

</details>
