---
title: ":read-write"
slug: Web/CSS/:read-write
page-type: css-pseudo-class
browser-compat: css.selectors.read-write
---

{{CSSRef}}

The **`:read-write`** [CSS](/en-US/docs/Web/CSS) [pseudo-class](/en-US/docs/Web/CSS/Pseudo-classes) represents an element (such as `input` or `textarea`) that is editable by the user.

{{EmbedInteractiveExample("pages/tabbed/pseudo-class-read-write.html", "tabbed-shorter")}}

## Syntax

```css
:read-write {
  /* ... */
}
```

## Examples

### Confirming form information in read-only/read-write controls

One use of `readonly` form controls is to allow the user to check and verify information that they may have entered in an earlier form (for example, shipping details), while still being able to submit the information along with the rest of the form. We do just this in the example below.

The `:read-only` pseudo-class is used to remove all the styling that makes the inputs look like clickable fields, making them look more like read-only paragraphs. The `:read-write` pseudo-class on the other hand is used to provide some nicer styling to the editable `<textarea>`.

```css
input:-moz-read-only,
textarea:-moz-read-only,
input:read-only,
textarea:read-only {
  border: 0;
  box-shadow: none;
  background-color: white;
}

textarea:-moz-read-write,
textarea:read-write {
  box-shadow: inset 1px 1px 3px #ccc;
  border-radius: 5px;
}
```

You can find the full source code at [readonly-confirmation.html](https://github.com/mdn/learning-area/blob/main/html/forms/pseudo-classes/readonly-confirmation.html); this renders like so:

```html live-sample___readonly-confirmation
<body>
  <form>
    <fieldset>
      <legend>Check shipping details</legend>
      <div>
        <label for="name"> Name: </label>
        <input id="name" name="name" readonly="" type="text" value="Mr Soft" />
      </div>
      <div>
        <label for="address"> Address: </label>
        <textarea id="address" name="address" readonly="">
23 Elastic Way,
Viscous,
Bright Ridge,
CA
</textarea
        >
      </div>
      <div>
        <label for="pcode"> Zip/postal code: </label>
        <input id="pcode" name="pcode" readonly="" type="text" value="94708" />
      </div>
    </fieldset>
    <fieldset>
      <legend>Final instructions</legend>
      <div>
        <label for="sms-confirm"> Send confirmation by SMS? </label>
        <input id="sms-confirm" name="sms-confirm" type="checkbox" />
      </div>
      <div>
        <label for="instructions"> Any special instructions? </label>
        <textarea id="instructions" name="instructions"></textarea>
      </div>
    </fieldset>
    <div>
      <button type="button">Amend details</button>
    </div>
    <div>
      <button type="submit">Submit</button>
    </div>
  </form>
</body>
```

```css live-sample___readonly-confirmation
body {
  font-family: "Josefin Sans", sans-serif;
  margin: 20px auto;
  max-width: 460px;
}

fieldset {
  padding: 10px 30px 0;
  margin-bottom: 20px;
}

legend {
  color: white;
  background: black;
  padding: 5px 10px;
}

fieldset > div {
  margin-bottom: 20px;
  display: flex;
  justify-content: space-between;
}

button,
label,
input[type="text"],
textarea {
  display: block;
  font-family: inherit;
  font-size: 100%;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  padding: 5px;
  height: 30px;
}

input[type="text"],
textarea {
  width: 50%;
}

textarea {
  height: 110px;
  resize: none;
}

label {
  width: 40%;
}

input:hover,
input:focus,
textarea:hover,
textarea:focus {
  background-color: #eee;
}

button {
  width: 60%;
  margin: 20px auto;
}

input:read-only,
textarea:read-only {
  border: 0;
  box-shadow: none;
  background-color: white;
}

textarea:read-write {
  box-shadow: inset 1px 1px 3px #ccc;
  border-radius: 5px;
}
```

{{EmbedLiveSample("readonly-confirmation")}}

### Styling read-write non-form controls

This selector doesn't just select {{htmlElement("input")}}/{{htmlElement("textarea")}} elements — it will select _any_ element that can be edited by the user, such as a {{htmlelement("p")}} element with [`contenteditable`](/en-US/docs/Web/HTML/Global_attributes/contenteditable) set on it.

```html
<p contenteditable>This paragraph is editable; it is read-write.</p>

<p>This paragraph is not editable; it is read-only.</p>
```

```css
p {
  font-size: 150%;
  padding: 5px;
  border-radius: 5px;
}

p:read-only {
  background-color: red;
  color: white;
}

p:read-write {
  background-color: lime;
}
```

{{EmbedLiveSample('Styling_read-write_non-form_controls', '100%', 400)}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{cssxref(":read-only")}}
- HTML [`contenteditable`](/en-US/docs/Web/HTML/Global_attributes/contenteditable) attribute
