---
title: "Test your skills: Object-oriented JavaScript"
slug: Learn/JavaScript/Objects/Test_your_skills:_Object-oriented_JavaScript
page-type: learn-module-assessment
---

{{learnsidebar}}

The aim of this skill test is to assess whether you've understood our [Classes in JavaScript](/en-US/docs/Learn/JavaScript/Objects/Classes_in_JavaScript) article.

> [!NOTE]
> You can try solutions in the interactive editors on this page or in an online editor such as [CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), or [Glitch](https://glitch.com/).
> If there is an error in your code, it will be logged into the results panel on this page or in the JavaScript console.
>
> If you get stuck, you can reach out to us in one of our [communication channels](/en-US/docs/MDN/Community/Communication_channels).

## OOJS 1

In this task we provide you with the start of a definition for a `Shape` class. It has three properties: `name`, `sides`, and `sideLength`. This class only models shapes for which all sides are the same length, like a square or an equilateral triangle.

We'd like you to:

- Add a constructor to this class. The constructor takes arguments for the `name`, `sides`, and `sideLength` properties, and initializes them.
- Add a new method `calcPerimeter()` method to the class, which calculates its perimeter (the length of the shape's outer edge) and logs the result to the console.
- Create a new instance of the `Shape` class called `square`. Give it a `name` of `square`, `4` `sides`, and a `sideLength` of `5`.
- Call your `calcPerimeter()` method on the instance, to see whether it logs the calculation result to the browser's console as expected.
- Create a new instance of `Shape` called `triangle`, with a `name` of `triangle`, `3` `sides` and a `sideLength` of `3`.
- Call `triangle.calcPerimeter()` to check that it works OK.

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/javascript/oojs/tasks/oojs/oojs1.html", '100%', 400)}}

<details>
<summary>Click here to show the solution</summary>

In this task we provide you with a `Shape` class containing only some data properties.

We want you to:

- add a constructor
- define a `calcPerimeter()` method
- create two instances of the class, a square and a triangle, and call their `calcPerimeter()` methods

Your code should look something like this:

```js
class Shape {
  name;
  sides;
  sideLength;

  constructor(name, sides, sideLength) {
    this.name = name;
    this.sides = sides;
    this.sideLength = sideLength;
  }

  calcPerimeter() {
    console.log(
      `The ${this.name}'s perimeter length is ${this.sides * this.sideLength}.`,
    );
  }
}

const square = new Shape("square", 4, 5);
square.calcPerimeter();

const triangle = new Shape("triangle", 3, 3);
triangle.calcPerimeter();
```

</details>

## OOJS 2

Next we'd like you to create a `Square` class that inherits from `Shape`, and adds a `calcArea()` method that calculates the square's area. Also set up the constructor so that the `name` property of `Square` object instances is automatically set to `square`, and the `sides` property is automatically set to `4`. When invoking the constructor, you should therefore just need to provide the `sideLength` property.

Create an instance of the `Square` class called `square` with appropriate property values, and call its `calcPerimeter()` and `calcArea()` methods to show that it works OK.

Try updating the live code below to recreate the finished example:

{{EmbedGHLiveSample("learning-area/javascript/oojs/tasks/oojs/oojs2.html", '100%', 400)}}

<details>
<summary>Click here to show the solution</summary>

Next, we'd like you to start with the `Shape` class you created in the last task.

We'd like you to create a `Square` class that inherits from `Shape`, and adds a `calcArea()` method that calculates the square's area.

Create an instance of the `Square` called square with appropriate property values, and call its `calcPerimeter()` and `calcArea()` methods to show that it works.

Your code should look something like this:

```js
class Shape {
  name;
  sides;
  sideLength;

  constructor(name, sides, sideLength) {
    this.name = name;
    this.sides = sides;
    this.sideLength = sideLength;
  }

  calcPerimeter() {
    console.log(
      `The ${this.name}'s perimeter length is ${this.sides * this.sideLength}.`,
    );
  }
}

class Square extends Shape {
  constructor(sideLength) {
    super("square", 4, sideLength);
  }

  calcArea() {
    console.log(
      `The ${this.name}'s area is ${this.sideLength * this.sideLength} squared.`,
    );
  }
}

const square = new Square(4);

square.calcPerimeter();
square.calcArea();
```

</details>
