---
title: Browser detection using the user agent
slug: Web/HTTP/Browser_detection_using_the_user_agent
page-type: guide
---

{{HTTPSidebar}}

Serving different Web pages or services to different browsers is usually a bad idea. The Web is meant to be accessible to everyone, regardless of which browser or device they're using. There are ways to develop your website to progressively enhance itself based on the availability of features rather than by targeting specific browsers.

But browsers and standards are not perfect, and there are still some edge cases where detecting the browser is needed. Using the user agent to detect the browser looks simple, but doing it well is, in fact, a very hard problem. This document will guide you in doing this as correctly as possible.

> [!NOTE]
> It's worth re-iterating: it's very rarely a good idea to use user agent sniffing. You can almost always find a better, more broadly compatible way to solve your problem!

## Considerations before using browser detection

When considering using the user agent string to detect which browser is being used, your first step is to try to avoid it if possible. Start by trying to identify **why** you want to do it.

- Are you trying to work around a specific bug in some version of a browser?
  - : Look, or ask, in specialized forums: you're unlikely to be the first to hit this problem. Also, experts, or people with another point of view, can give you ideas for working around the bug. If the problem seems uncommon, it's worth checking if this bug has been reported to the browser vendor via their bug tracking system ([Mozilla](https://bugzilla.mozilla.org/); [WebKit](https://bugs.webkit.org/); [Blink](https://www.chromium.org/issue-tracking/); [Opera](https://bugs.opera.com/)). Browser makers do pay attention to bug reports, and the analysis may hint about other workarounds for the bug.
- Are you trying to check for the existence of a specific feature?
  - : Your site needs to use a specific Web feature that some browsers don't yet support, and you want to send those users to an older website with fewer features but that you know will work. This is the worst reason to use user agent detection because odds are eventually all the other browsers will catch up. In addition, it is not practical to test every one of the less popular browsers and test for those Web features. You should **never** do user agent sniffing. There is **always** the alternative of doing [feature detection](/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection) instead.
- Do you want to provide different HTML depending on which browser is being used?
  - : This is usually a bad practice, but there are some cases in which this is necessary. In these cases, you should first analyze your situation to be sure it's really necessary. Can you prevent it by adding some non-semantic {{ HTMLElement("div") }} or {{ HTMLElement("span") }} elements? The difficulty of successfully using user agent detection is worth a few disruptions to the purity of your HTML. Also, rethink your design: can you use progressive enhancement or fluid layouts to help remove the need to do this?

## Avoiding user agent detection

If you want to avoid using user agent detection, you have options!

- **Feature detection**

  - : [Feature detection](/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection) is where you don't try to figure out which browser is rendering your page, but instead, you check to see if the specific feature you need is available. If it's not, you use a fallback. In those rare cases where behavior differs between browsers, instead of checking the user agent string, you should instead implement a test to detect how the browser implements the API and determine how to use it from that.
    There is **always** a way to test browser support without user agent sniffing. There is **never** any reason to check the user agent string for this.

    Don't unintentionally use the API you are testing for in unsupported browsers. This may sound obvious, but this may cause parser errors in browsers that don't support the feature.

- **Progressive enhancement**
  - : This design technique involves developing your website in 'layers', using a bottom-up approach, starting with a simpler layer and improving the capabilities of the site in successive layers, each using more features.
- **Graceful degradation**
  - : This is a top-down approach in which you build the best possible site using all the features you want, then tweak it to make it work on older browsers. This can be harder to do, and less effective, than progressive enhancement, but may be useful in some cases.
- **Mobile device detection**

  - : Arguably the most common use and misuse of user agent sniffing is to detect if the device is a mobile device. However, people too often overlook what they are really after.
    People use user agent sniffing to detect if the users' device is touch-friendly and has a small screen so they can optimize their website accordingly. While user agent sniffing can sometimes detect these, not all devices are the same: some mobile devices have big screen sizes, some desktops have a small touchscreen, some people use smart TV's which are an entirely different ballgame altogether, and some people can dynamically change the width and height of their screen by flipping their tablet on its side! So, user agent sniffing is definitely not the way to go.

    Thankfully, there are much better alternatives. Use [`Navigator.maxTouchPoints`](/en-US/docs/Web/API/Navigator/maxTouchPoints) to detect if the user's device has a touchscreen. Then, default back to checking the user agent screen only `if (!("maxTouchPoints" in navigator)) { /* Code here */ }`. Using this information of whether the device has a touchscreen, do not change the entire layout of the website just for touch devices: you will only create more work and maintenance for yourself. Rather, add in touch conveniences such as bigger, more easily clickable buttons (you can do this using CSS by increasing the font size). Here is an example of code that increases the padding of `#exampleButton` to `1em` on mobile devices.

    ```js
    let hasTouchScreen = false;
    if ("maxTouchPoints" in navigator) {
      hasTouchScreen = navigator.maxTouchPoints > 0;
    } else if ("msMaxTouchPoints" in navigator) {
      hasTouchScreen = navigator.msMaxTouchPoints > 0;
    } else {
      const mQ = matchMedia?.("(pointer:coarse)");
      if (mQ?.media === "(pointer:coarse)") {
        hasTouchScreen = !!mQ.matches;
      } else if ("orientation" in window) {
        hasTouchScreen = true; // deprecated, but good fallback
      } else {
        // Only as a last resort, fall back to user agent sniffing
        const UA = navigator.userAgent;
        hasTouchScreen =
          /\b(BlackBerry|webOS|iPhone|IEMobile)\b/i.test(UA) ||
          /\b(Android|Windows Phone|iPad|iPod)\b/i.test(UA);
      }
    }

    if (hasTouchScreen) {
      document.getElementById("exampleButton").style.padding = "1em";
    }
    ```

Layouts like [Flexboxes](/en-US/docs/Learn/CSS/CSS_layout/Flexbox) and [multicolumn](/en-US/docs/Web/CSS/Layout_cookbook/Column_layouts) are useful for many types of designs, and have sensible fallbacks for the rare cases that they're not supported on old browsers.

## Making the best of user agent sniffing

After reviewing all of the above better alternatives to user agent sniffing, there are still some potential cases where user agent sniffing is appropriate and justified.
One such case is using user agent sniffing as a fallback when detecting if the device has a touch screen. See the [Mobile Device Detection](#mobile_device_detection) section for more information.
Another case is adding workarounds for bugs that exist in older browsers or browsers that do not automatically update.

## Which part of the user agent contains the information you are looking for?

As there is no uniformity of the different part of the user agent string, this is the tricky part.

### Browser Name and version

When people say they want "browser detection", often they want "rendering engine detection". Do you want to detect Firefox, as opposed to SeaMonkey, or Chrome as opposed to Chromium? Or do you want to see if the browser is using the Gecko or the WebKit rendering engine?

Most browsers set the name and version in the format _BrowserName/VersionNumber_. But as the name is not the only information in a user agent string that is in that format, you can not discover the name of the browser, you can only check if the name you are looking for exists. But note that some browsers are lying: Chrome for example reports both as Chrome and Safari. So to detect Safari you have to check for the Safari string and the absence of the Chrome string, Chromium often reports itself as Chrome too or Seamonkey sometimes reports itself as Firefox.

Also, pay attention not to use a simple regular expression on the BrowserName, user agents also contain strings outside the Keyword/Value syntax. Safari & Chrome contain the string 'like Gecko', for instance.

| Browser name                    | Must contain    | Must not contain               |
| ------------------------------- | --------------- | ------------------------------ |
| Firefox                         | `Firefox/xyz`   | `Seamonkey/xyz`                |
| Seamonkey                       | `Seamonkey/xyz` |                                |
| Chrome                          | `Chrome/xyz`    | `Chromium/xyz` or `Edg.*/xyz`  |
| Chromium                        | `Chromium/xyz`  |                                |
| Safari                          | `Safari/xyz`    | `Chrome/xyz` or `Chromium/xyz` |
| Opera 15+ (Blink-based engine)  | `OPR/xyz`       |                                |
| Opera 12- (Presto-based engine) | `Opera/xyz`     |                                |

\[1] Safari gives two version numbers: one technical in the `Safari/xyz` token, and one user-friendly in a `Version/xyz` token.

Of course, there is absolutely no guarantee that another browser will not hijack some of these things (like Chrome hijacked the Safari string in the past). That's why browser detection using the user agent string is unreliable and should be done only with the check of the version number (hijacking of past versions is less likely).

### Rendering engine

As seen earlier, in most cases, looking for the rendering engine is a better way to go. This will help to not exclude lesser known browsers. Browsers sharing a common rendering engine will display a page in the same way: it is often a fair assumption that what will work in one will work in the other.

There are three active major rendering engines: Blink, Gecko, and WebKit. As sniffing the rendering engines names is common, a lot of user agents added other rendering names to trigger detection. It is therefore important to pay attention not to trigger false-positives when detecting the rendering engine.

| Engine   | Must contain      | Comment                                                                                                                                                                                      |
| -------- | ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Blink    | `Chrome/xyz`      |                                                                                                                                                                                              |
| Gecko    | `Gecko/xyz`       |                                                                                                                                                                                              |
| WebKit   | `AppleWebKit/xyz` | Pay attention, WebKit browsers add a 'like Gecko' string that may trigger false positive for Gecko if the detection is not careful.                                                          |
| Presto   | `Opera/xyz`       | Obsolete; Presto is no longer used in Opera browser builds >= version 15 (see 'Blink')                                                                                                       |
| EdgeHTML | `Edge/xyz`        | The non-Chromium Edge puts its engine version after the _Edge/_ token, not the application version. Obsolete; EdgeHTML is no longer used in Edge browser builds >= version 79 (see 'Blink'). |

## Rendering engine version

Most rendering engines put the version number in the _RenderingEngine/VersionNumber_ token, with the notable exception of Gecko. Gecko puts the Gecko version number in the comment part of the User Agent after the `rv:` string. From Gecko 14 for the mobile version and Gecko 17 for the desktop version, it also puts this value in the `Gecko/version` token (previous version put there the build date, then a fixed date called the GeckoTrail).

## OS

The Operating System is given in most User Agent strings (although not web-focused platforms like Firefox OS), but the format varies a lot. It is a fixed string between two semicolons, in the comment part of the User Agent. These strings are specific for each browser. They indicate the OS, but also often its version and information on the relying hardware (32 or 64 bits, Intel/PPC for Mac, or x86/ARM CPU architecture for Windows PCs).

Like in all cases, these strings may change in the future, one should use them only in conjunction with the detection of already released browsers. A technological survey must be in place to adapt the script when new browser versions are coming out.

### Mobile, Tablet or Desktop

The most common reason to perform user agent sniffing is to determine which type of device the browser runs on. The goal is to serve different HTML to different device types.

- Never assume that a browser or a rendering engine only runs on one type of device. Especially don't make different defaults for different browsers or rendering engines.
- Never use the OS token to define if a browser is on mobile, tablet or desktop. The OS may run on more than one type of device (for example, Android runs on tablets as well as phones).

The following table summarizes the way common browser vendors indicate that their browsers are running on a mobile device:

| Browser                                                           | Rule                                                 | Example                                                                                                                                                          |
| ----------------------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Mozilla (Gecko, Firefox)                                          | `Mobile` or `Tablet` inside the comment.             | `Mozilla/5.0 (Android; Mobile; rv:13.0) Gecko/13.0 Firefox/13.0`                                                                                                 |
| WebKit-based (Android, Safari)                                    | `Mobile Safari` token outside the comment.           | `Mozilla/5.0 (Linux; U; Android 4.0.3; de-ch; HTC Sensation Build/IML74K) AppleWebKit/534.30 (KHTML, like Gecko) Version/4.0 Mobile Safari/534.30`               |
| Blink-based (Chromium, Google Chrome, Opera 15+, Edge on Android) | `Mobile Safari` token outside the comment.           | `Mozilla/5.0 (Linux; Android 4.4.2; Nexus 5 Build/KOT49H) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/33.0.1750.117 Mobile Safari/537.36 OPR/20.0.1396.72047`  |
| Presto-based (Opera 12-)                                          | `Opera Mobi/xyz` token inside the comment.           | `Opera/9.80 (Android 2.3.3; Linux; Opera Mobi/ADR-1111101157; U; es-ES) Presto/2.9.201 Version/11.50`                                                            |
| Edge on Windows 10 Mobile                                         | `Mobile/xyz` and `Edge/` tokens outside the comment. | `Mozilla/5.0 (Windows Phone 10.0; Android 6.0.1; Xbox; Xbox One) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Mobile Safari/537.36 Edge/16.16299` |

In summary, we recommend looking for the string `Mobi` anywhere in the User Agent to detect a mobile device.

> [!NOTE]
> If the device is large enough that it's not marked with `Mobi`, you should serve your desktop site (which, as a best practice, should support touch input anyway, as more desktop machines are appearing with touchscreens).
