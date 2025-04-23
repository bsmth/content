---
title: Useful string methods
short-title: String methods
slug: Learn_web_development/Core/Scripting/Useful_string_methods
page-type: learn-module-chapter
sidebar: learnsidebar
---

{{PreviousMenuNext("Learn_web_development/Core/Scripting/Strings", "Learn_web_development/Core/Scripting/Arrays", "Learn_web_development/Core/Scripting")}}

Now that we've looked at the very basics of strings, let's move up a gear and start thinking about what useful operations we can do on strings with built-in methods, such as finding the length of a text string, joining and splitting strings, substituting one character in a string for another, and more.

<table>
  <tbody>
    <tr>
      <th scope="row">Prerequisites:</th>
      <td>An understanding of <a href="/en-US/docs/Learn_web_development/Core/Structuring_content">HTML</a> and the <a href="/en-US/docs/Learn_web_development/Core/Styling_basics">fundamentals of CSS</a>. Knowledge of <a href="/en-US/docs/Learn_web_development/Core/Scripting/Strings">string basics</a>.</td>
    </tr>
    <tr>
      <th scope="row">Learning outcomes:</th>
      <td>
          String manipulation using common properties and methods built into JavaScript.
      </td>
    </tr>
  </tbody>
</table>

## Strings as objects

Most values can be used as if they are objects in JavaScript. When you create a string, for example by using

```js
const string = "This is my string";
```

although the variable itself isn't an object, it still has a large number of properties and methods available to it, by virtue of being usable as an object when accessing properties. You can see this if you go to the {{jsxref("String")}} object page and look down the list on the side of the page!

**Now, before your brain starts melting, don't worry!** You really don't need to know about most of these early on in your learning journey. But there are a few that you'll potentially use quite often that we'll look at here.

Let's enter some examples into the [browser developer console](/en-US/docs/Learn_web_development/Howto/Tools_and_setup/What_are_browser_developer_tools).

## Finding the length of a string

This is easy — you use the {{jsxref("String.prototype.length", "length")}} property. Try entering the following lines:

```js
const browserType = "mozilla";
browserType.length;
```

This should return the number 7, because "mozilla" is 7 characters long. This is useful for many reasons; for example, you might want to find the lengths of a series of names so you can display them in order of length, or let a user know that a username they have entered into a form field is too long if it is over a certain length.

## Retrieving a specific string character

On a related note, you can return any character inside a string by using **square bracket notation** — this means you include square brackets (`[]`) on the end of your variable name. Inside the square brackets, you include the number of the character you want to return, so for example to retrieve the first letter you'd do this:

```js
browserType[0];
```

Remember: computers count from 0, not 1!

To retrieve the last character of _any_ string, we could use the following line, combining this technique with the `length` property we looked at above:

```js
browserType[browserType.length - 1];
```

The length of the string "mozilla" is 7, but because the count starts at 0, the last character's position is 6; using `length-1` gets us the last character.

## Testing if a string contains a substring

Sometimes you'll want to find if a smaller string is present inside a larger one (we generally say _if a substring is present inside a string_). This can be done using the {{jsxref("String.prototype.includes()", "includes()")}} method, which takes a single {{glossary("parameter")}} — the substring you want to search for.

It returns `true` if the string contains the substring, and `false` otherwise.

```js
const browserType = "mozilla";

if (browserType.includes("zilla")) {
  console.log("Found zilla!");
} else {
  console.log("No zilla here!");
}
```

Often you'll want to know if a string starts or ends with a particular substring. This is a common enough need that there are two special methods for this: {{jsxref("String.prototype.startsWith()", "startsWith()")}} and {{jsxref("String.prototype.endsWith()", "endsWith()")}}:

```js
const browserType = "mozilla";

if (browserType.startsWith("zilla")) {
  console.log("Found zilla!");
} else {
  console.log("No zilla here!");
}
```

```js
const browserType = "mozilla";

if (browserType.endsWith("zilla")) {
  console.log("Found zilla!");
} else {
  console.log("No zilla here!");
}
```

## Finding the position of a substring in a string

You can find the position of a substring inside a larger string using the {{jsxref("String.prototype.indexOf()", "indexOf()")}} method. This method takes two {{glossary("parameter", "parameters")}} – the substring that you want to search for, and an optional parameter that specifies the starting point of the search.

If the string contains the substring, `indexOf()` returns the index of the first occurrence of the substring. If the string does not contain the substring, `indexOf()` returns `-1`.

```js
const tagline = "MDN - Resources for developers, by developers";
console.log(tagline.indexOf("developers")); // 20
```

Starting at `0`, if you count the number of characters (including the whitespace) from the beginning of the string, the first occurrence of the substring `"developers"` is at index `20`.

```js
console.log(tagline.indexOf("x")); // -1
```

This, on the other hand, returns `-1` because the character `x` is not present in the string.

So now that you know how to find the first occurrence of a substring, how do you go about finding subsequent occurrences? You can do that by passing in a value that's greater than the index of the previous occurrence as the second parameter to the method.

```js
const firstOccurrence = tagline.indexOf("developers");
const secondOccurrence = tagline.indexOf("developers", firstOccurrence + 1);

console.log(firstOccurrence); // 20
console.log(secondOccurrence); // 35
```

Here we're telling the method to search for the substring `"developers"` starting at index `21` (`firstOccurrence + 1`), and it returns the index `35`.

## Extracting a substring from a string

You can extract a substring from a string using the {{jsxref("String.prototype.slice()", "slice()")}} method. You pass it:

- the index at which to start extracting
- the index at which to stop extracting. This is exclusive, meaning that the character at this index is not included in the extracted substring.

For example:

```js
const browserType = "mozilla";
console.log(browserType.slice(1, 4)); // "ozi"
```

The character at index `1` is `"o"`, and the character at index 4 is `"l"`. So we extract all characters starting at `"o"` and ending just before `"l"`, giving us `"ozi"`.

If you know that you want to extract all of the remaining characters in a string after a certain character, you don't have to include the second parameter. Instead, you only need to include the character position from where you want to extract the remaining characters in a string. Try the following:

```js
browserType.slice(2); // "zilla"
```

This returns `"zilla"` — this is because the character position of 2 is the letter `"z"`, and because you didn't include a second parameter, the substring that was returned was all of the remaining characters in the string.

> **Note:** `slice()` has other options too; study the {{jsxref("String.prototype.slice()", "slice()")}} page to see what else you can find out.

## Changing case

The string methods {{jsxref("String.prototype.toLowerCase()", "toLowerCase()")}} and {{jsxref("String.prototype.toUpperCase()", "toUpperCase()")}} take a string and convert all the characters to lower- or uppercase, respectively. This can be useful for example if you want to normalize all user-entered data before storing it in a database.

Let's try entering the following lines to see what happens:

```js
const radData = "My NaMe Is MuD";
console.log(radData.toLowerCase());
console.log(radData.toUpperCase());
```

## Updating parts of a string

You can replace one substring inside a string with another substring using the {{jsxref("String.prototype.replace()", "replace()")}} method.

In this example, we're providing two parameters — the string we want to replace, and the string we want to replace it with:

```js
const browserType = "mozilla";
const updated = browserType.replace("moz", "van");

console.log(updated); // "vanilla"
console.log(browserType); // "mozilla"
```

Note that `replace()`, like many string methods, doesn't change the string it was called on, but returns a new string. If you want to update the original `browserType` variable, you would have to do something like this:

```js
let browserType = "mozilla";
browserType = browserType.replace("moz", "van");

console.log(browserType); // "vanilla"
```

Also note that we now have to declare `browserType` using `let`, not `const`, because we are reassigning it.

Be aware that `replace()` in this form only changes the first occurrence of the substring. If you want to change all occurrences, you can use {{jsxref("String.prototype.replaceAll()", "replaceAll()")}}:

```js
let quote = "To be or not to be";
quote = quote.replaceAll("be", "code");

console.log(quote); // "To code or not to code"
```

## Active learning examples

In this section, we'll get you to try your hand at writing some string manipulation code. In each exercise below, we have an array of strings, and a loop that processes each value in the array and displays it in a bulleted list. You don't need to understand arrays or loops right now — these will be explained in future articles. All you need to do in each case is write the code that will output the strings in the format that we want them in.

Each example comes with a "Reset" button, which you can use to reset the code if you make a mistake and can't get it working again, and a "Show solution" button you can press to see a potential answer if you get really stuck.

### Filtering greeting messages

In the first exercise, we'll start you off simple — we have an array of greeting card messages, but we want to sort them to list just the Christmas messages.

Think about how you could test whether the message in each case is a Christmas message.
What string is present in all of those messages, and what method could you use to test whether it is present?

We want you to fill in a conditional test inside the `if ()` structure to test each string and only print it in the list if it is a Christmas message:

```html live-sample___filtering-greeting
<h2>Your festive list:</h2>
<div class="output">
  <ul></ul>
</div>
```

```js live-sample___filtering-greeting
const list = document.querySelector(".output ul");
const greetings = [
  "Happy Birthday!",
  "Merry Christmas my love",
  "A happy Christmas to all the family",
  "You're all I want for Christmas",
  "Get well soon",
];

for (const greeting of greetings) {
  // Your conditional needs to go in the parentheses
  // in the next line, replacing "greeting"
  if (greeting) {
    const listItem = document.createElement("li");
    listItem.textContent = greeting;
    list.appendChild(listItem);
  }
}
```

```css hidden live-sample___filtering-greeting
body {
  font-family: sans-serif;
  margin: 10px;
}
```

{{EmbedLiveSample('filtering-greeting', , 200)}}

<details>
<summary>Click here to show the solution</summary>

You can use the string {{jsxref("String/includes", "includes()")}} method:

```js
for (const greeting of greetings) {
  if (greeting.includes("Christmas")) {
    const listItem = document.createElement("li");
    listItem.textContent = greeting;
    list.appendChild(listItem);
  }
}
```

</details>

### Fixing capitalization

In this exercise, we have the names of cities in the United Kingdom, but the capitalization is all messed up. We want you to change them so that they are all lowercase, except for a capital first letter. A good way to do this is to:

1. Convert the whole of the string contained in the `city` variable to lowercase and store it in a new variable.
2. Grab the first letter of the string in this new variable and store it in another variable.
3. Using this latest variable as a substring, replace the first letter of the lowercase string with the first letter of the lowercase string changed to upper case. Store the result of this replacement procedure in another new variable.
4. Change the value of the `result` variable to equal to the final result, not the `city`.

> [!NOTE]
> A hint — the parameters of the string methods don't have to be string literals; they can also be variables, or even variables with a method being invoked on them.

```html live-sample___fixing-capitalization
<h2>Cities list:</h2>
<div class="output">
  <ul></ul>
</div>
```

```js live-sample___fixing-capitalization
const list = document.querySelector(".output ul");
const cities = ["lonDon", "ManCHESTer", "BiRmiNGHAM", "liVERpoOL"];

for (const city of cities) {
  // Add some lines of code here so `result` contains what you need:
  const result = city;

  // Don't edit the following lines:
  const listItem = document.createElement("li");
  listItem.textContent = result;
  list.appendChild(listItem);
}
```

```css hidden live-sample___fixing-capitalization
body {
  font-family: sans-serif;
  margin: 10px;
}
```

{{EmbedLiveSample('fixing-capitalization', , 200)}}

<details>
<summary>Click here to show the solution</summary>

This solution uses the following methods:

- {{jsxref("String/toLowerCase", "toLowerCase()")}} to lowercase the entire string
- {{jsxref("String/slice", "slice()")}} to get the first letter
- {{jsxref("String/replace", "replace()")}} to convert the first letter to uppercase

```js
for (const city of cities) {
  const lower = city.toLowerCase();
  const firstLetter = lower.slice(0, 1);
  const capitalized = lower.replace(firstLetter, firstLetter.toUpperCase());
  const result = capitalized;
  const listItem = document.createElement("li");
  listItem.textContent = result;
  list.appendChild(listItem);
}
```

</details>

### Making new strings from old parts

In this last exercise, the array contains a bunch of strings containing information about train stations in the North of England. The strings are data items that contain the three-letter station code, followed by some machine-readable data, followed by a semicolon, followed by the human-readable station name. For example:

```plain
MAN675847583748sjt567654;Manchester Piccadilly
```

We want to extract the station code and name, and put them together in a string with the following structure:

```plain
MAN: Manchester Piccadilly
```

We'd recommend doing it like this:

1. Extract the three-letter station code and store it in a new variable.
2. Find the character index number of the semicolon.
3. Extract the human-readable station name using the semicolon character index number as a reference point, and store it in a new variable.
4. Concatenate the two new variables and a string literal to make the final string.
5. Change the value of the `result` variable to the final string, not the `station`.

```html live-sample___strings-from-parts
<h2>Stations list:</h2>
<div class="output">
  <ul></ul>
</div>
```

```js live-sample___strings-from-parts
const list = document.querySelector(".output ul");
const stations = [
  "MAN675847583748sjt567654;Manchester Piccadilly",
  "GNF576746573fhdg4737dh4;Greenfield",
  "LIV5hg65hd737456236dch46dg4;Liverpool Lime Street",
  "SYB4f65hf75f736463;Stalybridge",
  "HUD5767ghtyfyr4536dh45dg45dg3;Huddersfield",
];

for (const station of stations) {
  // Add some lines of code here so `result` contains what you need:
  const result = station;

  // Don't edit the following lines:
  const listItem = document.createElement("li");
  listItem.textContent = result;
  list.appendChild(listItem);
}
```

```css hidden live-sample___strings-from-parts
body {
  font-family: sans-serif;
  margin: 10px;
}
```

{{EmbedLiveSample('strings-from-parts', , 200)}}

<details>
<summary>Click here to show the solution</summary>

This solution uses the following methods:

- {{jsxref("String/slice", "slice()")}} to extract the three-letter station code (the first three characters)
- {{jsxref("String/indexOf", "indexOf()")}} to find where the `;` semicolon separator is
- {{jsxref("String/slice", "slice()")}} the string again starting from the first character after the semicolon (the `name`)
- {{jsxref("Template_literals", "template literals")}} for string formatting

```js
for (const station of stations) {
  const code = station.slice(0, 3);
  const semiColon = station.indexOf(";");
  const name = station.slice(semiColon + 1);
  const result = `${code}: ${name}`;
  const listItem = document.createElement("li");
  listItem.textContent = result;
  list.appendChild(listItem);
}
```

</details>

## Test your skills!

You've reached the end of this article, but can you remember the most important information? You can find some further tests to verify that you've retained this information before you move on — see [Test your skills: Strings](/en-US/docs/Learn_web_development/Core/Scripting/Test_your_skills/Strings).

## Conclusion

You can't escape the fact that being able to handle words and sentences in programming is very important — particularly in JavaScript, as websites are all about communicating with people. This article has given you the basics that you need to know about manipulating strings for now. This should serve you well as you go into more complex topics in the future. Next, we're going to look at the last major type of data we need to focus on in the short term — arrays.

{{PreviousMenuNext("Learn_web_development/Core/Scripting/Strings", "Learn_web_development/Core/Scripting/Arrays", "Learn_web_development/Core/Scripting")}}
