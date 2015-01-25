---
layout: post
title: Target Internet Explorer in CSS
subtitle: A cup of graceful degradation anyone?
permalink: target-ie-in-css
---

*Browser specific CSS is not everyone's cup of tea.*

However, since you can't rely on conditional comments anymore, I've came up with a script that lets you write CSS specific for Internet Explorer 10 and Internet Explorer 11. I combined UA sniffing with feature detection for Pointer Events to detect the browser and add the appropriate class to the `<html>` element. I've seen a lot of hacks, but none were elegant enough, and I find this to be a decent, non-hacky method to detect a specific version of IE.

```javascript
// Detect IE and append class to <html> element
var UA = navigator.userAgent;
var html = document.documentElement;
if (UA.indexOf("IEMobile") === -1) {
    if ((UA.indexOf("rv:11.") !== -1) && (!html.classList.contains('ie11')) && window.navigator.msPointerEnabled) {
        html.classList.add("ie11");
    } else if ((UA.indexOf("MSIE 10.") !== -1) && (!html.classList.contains('ie10')) && window.navigator.msPointerEnabled) {
        html.classList.add("ie10");
    }
}
```

After it's applied, you will be able to target Internet Explorer 10 and Internet Explorer 11 with CSS classes.

```css
.ie11 .flex-child,
.ie10 .flex-child {
	height: 100%;
	flex: 0 1 auto;
	-ms-flex: 0 1 auto;
}
```
Some features:

 - Won't affect Internet Explorer Mobile
 - Works for Internet Explorer 10 and Internet Explorer 11
 - Stops working when you change the UA
 - Won't work if you pretend to be IE from another browser
 - Plays nice with Compatibility Mode for testing

It will obviously stop working for anyone who changes their UA. They know what they're doing. I've tested it out and used it in production for a couple of large websites, although I tend not to write browser specific CSS, with IE it's sometimes a necessity.