---
title: rel=preload
slug: Web/HTML/Attributes/rel/preload
page-type: html-attribute-value
browser-compat: html.elements.link.rel.preload
---

{{HTMLSidebar}}

The `preload` value of the {{htmlelement("link")}} element's [`rel`](/en-US/docs/Web/HTML/Element/link#rel) attribute lets you declare fetch requests in the
HTML's {{htmlelement("head")}}, specifying resources that your page will need very soon, which you want to start loading early in the page lifecycle,
before browsers' main rendering machinery kicks in. This ensures they are available earlier and are less likely to block the page's render, improving performance. Even though the name contains the term _load_, it doesn't load and execute the script but only schedules it to be downloaded and cached with a higher priority.

## A basic preload example

You most commonly use `<link>` to load a CSS file to style your page with:

```html
<link rel="stylesheet" href="styles/main.css" />
```

Here however, we will use a `rel` value of `preload`, which turns `<link>` into a preloader for any resource we want.
You also need to specify:

- The path to the resource in the [`href`](/en-US/docs/Web/HTML/Element/link#href) attribute.
- The type of resource in the [`as`](/en-US/docs/Web/HTML/Element/link#as) attribute.

```html live-sample___basic-preload
<head>
  <meta charset="utf-8" />
  <title>JS and CSS preload example</title>

  <link rel="preload" href="style.css" as="style" />
  <link rel="preload" href="main.js" as="script" />

  <link rel="stylesheet" href="style.css" />
</head>

<body>
  <h1>bouncing balls</h1>
  <canvas></canvas>

  <script src="main.js" defer></script>
</body>
```

Here, we preload our CSS and JavaScript files so they will be available as soon as they are required for the rendering of the page later on.
Using `<link rel="preload">` in this exact example doesn't offer much improvement given it's size - the browser probably discovers the `<link rel="stylesheet">` and `<script>` elements in the same chunk of HTML as the preloads.
The benefits are more noticeable when resources are larger or discovered much later in the rendering process.
Good candidates to preload are:

- Resources that are referenced inside CSS, like fonts or images.
- Resources that JavaScript can request, like imported scripts.

`preload` has other advantages. Using `as` to specify the type of content to be preloaded allows the browser to:

- Store in the cache for future requests, reusing the resource if appropriate.
- Apply the correct [content security policy](/en-US/docs/Web/HTTP/CSP) to the resource.
- Set the correct {{HTTPHeader("Accept")}} request headers for it.

### What types of content can be preloaded?

Many content types can be preloaded. The possible `as` attribute values are:

- `fetch`: Resource to be accessed by a fetch or XHR request, such as an ArrayBuffer, WebAssembly binary, or JSON file.
- `font`: Font file.
- `image`: Image file.
- `script`: JavaScript file.
- `style`: CSS stylesheet.
- `track`: WebVTT file.

> [!NOTE]
> Preloading with `font` and `fetch` content types requires the `crossorigin` attribute to be set; see [CORS-enabled fetches](#cors-enabled_fetches) below.

There's more detail about these values and the web features they expect to be consumed by in the HTML spec — see [Link type "preload"](https://html.spec.whatwg.org/#match-preload-type). Also note that the full list of values the `as` attribute can take is governed by the Fetch spec — see [request destinations](https://fetch.spec.whatwg.org/#concept-request-destination).

## Preloading including a MIME type

`<link>` elements can accept a [`type`](/en-US/docs/Web/HTML/Element/link#type) attribute, which contains the MIME type ([media type](/en-US/docs/Web/HTTP/MIME_types)) of the resource the element points to. This is especially useful when preloading resources — the browser will use the `type` attribute value to work out if it supports that resource, and will only download it if so, ignoring it if not.

```html
<head>
  <meta charset="utf-8" />
  <title>Image preload example</title>

  <link rel="preload" href="flower.avif" as="image" type="image/avif" />
</head>
<body>
  <picture>
    <source src="flower.avif" type="image/avif" />
    <source src="flower.webp" type="image/webp" />
    <img src="flower.jpg" />
  </picture>
</body>
```

The code in the example above causes the `image/avif` image to be preloaded only in supporting browsers — and for users who have `image/avif` support in their browsers, causes the `image/avif` image to actually be used (since it's the first {{htmlelement("source")}} specified). That makes the image download hopefully smaller for users who have `image/avif` support in their browsers.

Note that for users whose browsers have both `image/avif` and `image/webp` support, if in that code a `<link rel="preload" href="flower.webp" as="image" type="image/webp">` element were also specified, then _both_ the `image/avif` and `image/webp` images would be preloaded — even though only one of them would actually be used.

Therefore, specifying preloading for multiple types of the same resource is discouraged. Instead, the best practice is to specify preloading only for the type the majority of your users are likely to actually use. That's why the code in the example above doesn't specify preloading for the `image/webp` image.

However, the lack of preloading doesn't prevent the `image/webp` image from actually being used by those who need it: for users whose browsers don't have `image/avif` support but do have `image/webp` support, the code in the example above does still cause the `image/webp` image to be used — but it does so without also causing it to also be preloaded unnecessarily for the majority of other users.

## CORS-enabled fetches

When preloading resources that are fetched with [CORS](/en-US/docs/Web/HTTP/CORS) enabled (e.g. [`fetch()`](/en-US/docs/Web/API/Window/fetch), [`XMLHttpRequest`](/en-US/docs/Web/API/XMLHttpRequest) or [fonts](/en-US/docs/Web/CSS/@font-face)), special care needs to be taken to setting the [`crossorigin`](/en-US/docs/Web/HTML/Element/link#crossorigin) attribute on your [`<link>`](/en-US/docs/Web/HTML/Element/link) element. The attribute needs to be set to match the resource's CORS and credentials mode, even when the fetch is not cross-origin.

As mentioned above, one interesting case where this applies is font files. Because of various reasons, these have to be fetched using anonymous-mode CORS (see [Font fetching requirements](https://drafts.csswg.org/css-fonts/#font-fetching-requirements)).

Let's use this case as an example.
Click "Play" to view and edit the code in the MDN Playground.
Note that if comment out or delete the CSS, there will still be `GET` requests made to the font URLs (you can view this in the Network panel in your browser's dev tools):

```html live-sample___font-preload
<head>
  <meta charset="utf-8" />
  <link
    rel="preload"
    href="https://mdn.github.io/shared-assets/fonts/FiraSans-Regular.woff2"
    as="font"
    type="font/woff2"
    crossorigin />
  <link
    rel="preload"
    href="https://mdn.github.io/shared-assets/fonts/LeagueMono-VF.ttf"
    as="font"
    type="font/ttf"
    crossorigin />
</head>

<body>
  <p class="one">FiraSans</p>
  <p class="two">LeagueMono</p>
</body>
```

```css live-sample___font-preload
@font-face {
  font-family: "FiraSans";
  src: url("https://mdn.github.io/shared-assets/fonts/FiraSans-Regular.woff2");
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: "LeagueMono";
  src: url("https://mdn.github.io/shared-assets/fonts/LeagueMono-VF.ttf");
  font-weight: normal;
  font-style: normal;
}

.one {
  font: 1.2em / 1.5 "FiraSans";
}

.two {
  font: 1.2em / 1.5 "LeagueMono";
}
```

{{Embedlivesample("font-preload")}}

Not only are we providing the MIME type hints in the `type` attributes, but we are also providing the `crossorigin` attribute to make sure the preload's CORS mode matches the eventual font resource request.

## Including media

One nice feature of `<link>` elements is their ability to accept [`media`](/en-US/docs/Web/HTML/Element/link#media) attributes. These can accept [media types](/en-US/docs/Web/CSS/@media#media_types) or full-blown [media queries](/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries), allowing you to do responsive preloading!

```html live-sample___media-preload
<head>
  <meta charset="utf-8" />
  <title>Responsive preload example</title>

  <link
    rel="preload"
    href="https://mdn.github.io/shared-assets/images/examples/balloons-small.jpg"
    as="image"
    type="image/jpeg"
    media="(max-width: 600px)"
    crossorigin />
  <link
    rel="preload"
    href="https://mdn.github.io/shared-assets/images/examples/puppy-header.jpg"
    as="image"
    type="image/jpeg"
    media="(min-width: 601px)"
    crossorigin />
</head>
<body>
  <header>
    <h1>My site</h1>
  </header>
</body>
```

```css live-sample___media-preload
html {
  font-family: sans-serif;
}

body {
  margin: 0 auto;
  max-width: 1200px;
}

header {
  height: 200px;
  background-position: center 0;
  background-repeat: no-repeat;
}

h1 {
  margin: 0;
  text-align: center;
  line-height: 200px;
  font-size: 4em;
}
```

```js live-sample___media-preload
const mediaQueryList = window.matchMedia("(max-width: 600px)");
const header = document.querySelector("header");

if (mediaQueryList.matches) {
  header.style.backgroundImage =
    "url(https://mdn.github.io/shared-assets/images/examples/balloons.jpg)";
  header.style.color = "white";
} else {
  header.style.backgroundImage =
    "url(https://mdn.github.io/shared-assets/images/examples/puppy-header.jpg)";
  header.style.color = "cornflowerblue";
}
```

{{Embedlivesample("media-preload")}}

We include `media` attributes on our `<link>` elements so that a narrow image is preloaded if the user has a narrow viewport, and a wider image is loaded if they have a wide viewport. We use {{domxref("Window.matchMedia")}} / {{domxref("MediaQueryList")}} to do this (see [Testing media queries](/en-US/docs/Web/CSS/CSS_media_queries/Testing_media_queries) for more).

This makes it much more likely that the font will be available for the page render, cutting down on FOUT (flash of unstyled text).

This doesn't have to be limited to images, or even files of the same type — think big! You could perhaps preload and display a simple SVG diagram if the user is on a narrow screen where bandwidth and CPU is potentially more limited, or preload a complex chunk of JavaScript then use it to render an interactive 3D model if the user's resources are more plentiful.

## Scripting and preloads

> [!NOTE]
> Use [`<link rel="modulepreload">`](/en-US/docs/Web/HTML/Attributes/rel/modulepreload) instead if you are working with [JavaScript modules](/en-US/docs/Web/JavaScript/Guide/Modules).

Another nice thing about these preloads is that you can execute them with script.
For example, here we create a {{domxref("HTMLLinkElement")}} instance, then attach it to the DOM:

```js
const preloadLink = document.createElement("link");
preloadLink.href = "myscript.js";
preloadLink.rel = "preload";
preloadLink.as = "script";
document.head.appendChild(preloadLink);
```

This means that the browser will preload the `myscript.js` file, but not actually use it yet. To use it, you could do this:

```js
const preloadedScript = document.createElement("script");
preloadedScript.src = "myscript.js";
document.body.appendChild(preloadedScript);
```

This is useful when you want to preload a script, but then defer execution until exactly when you need it.

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Speculative loading](/en-US/docs/Web/Performance/Speculative_loading) for a comparison of `<link rel="preload">` and other similar performance improvement features.
- [Preload: What Is It Good For?](https://www.smashingmagazine.com/2016/02/preload-what-is-it-good-for/) by Yoav Weiss
