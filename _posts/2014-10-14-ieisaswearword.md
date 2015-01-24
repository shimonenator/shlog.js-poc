---
layout: post
title: Internet Explorer is a swearword
subtitle: Future of The Notorious Browser
permalink: ie-is-a-swearword
---


Not so long ago I've listened to [Brendan Eich in JavaScript Jabber (Ep. 124)](http://javascriptjabber.com/124-jsj-the-origin-of-javascript-with-brendan-eich/) talk about the origin of JavaScript. While talking about Netscape and IE back in the day he remembered:


> Mike Homer the marketing VP at Netscape said the monster truck was in our rearview mirror. Netscape’s in its little Yugo, the pedal to the metal going, topping out at 50 miles an hour heading toward distant horizon. And behind us is the monster truck that’s creeping up.


Internet Explorer was going to overtake the market, and in its monster truck, that was only a matter of time. As some of you might know, Yugo is not much of car (*I know, I have one*). But if you pull over, it's bound to pass you by sooner or later. Since then Internet Explorer *stopped* and has become a synonym for a bunch of very nasty words in the mouth of every web developer. *No, it became a swearword on its own.*


My interest in web standards and IE related issues, has always gotten me in trouble of being in charge of cross-browser normalization. What that really means is "Internet Explorer normalization".


Now, the motivation for writing this article are the changes I have experienced in my workflow since Internet Explorer 11 came out, as Internet Explorer 8 has been phased out from the mind of clients and the web in general. The article could easily be titled "My thoughts on Internet Explorer's future" but who would read that mellow garbage?

## Present and future of Internet Explorer

Due to a phylosophy I nurture about development and performance, which I won't discuss in detail now, I test and sometimes develop on a low-end, low-power laptop with a [AMD C-50](http://www.notebookcheck.net/AMD-C-50-Notebook-Processor.40960.0.html) CPU which really trains your patience, and makes you renounce the idea of multitasking. That laptop is the major culprit for my daily usage of Internet Explorer 11.


What really got me to pin it to taskbar is that it felt snappier, it rendered faster and it made my life a bit easier on Windows. That's what you get when you develop a browser for your own platform; it shouldn't fall short in any of these parameters. Especially when you consider it's utilizing stuff like Prefetech and Direct2D which give that home court advantage to it. Not just that, all the tech it uses under the hood has been writen and optimized for Windows. There are a lot of features and improvements, I'd like to see in it, as a developer. However, from a user point of view, the list is getting managable lately.


Speaking of features, couple of weeks ago I've read ["Updates to our platform roadmap"](http://blogs.msdn.com/b/ie/archive/2014/09/18/updates-to-our-platform-roadmap.aspx) on the Internet Explorer Blog, which pointed me to further explore [IE's Web platform status](http://blogs.msdn.com/b/ie/archive/2014/09/18/updates-to-our-platform-roadmap.aspx). It gave me a better insight to what's yet to come in Internet Explorer, and to be honest, I wasn't thrilled.


I felt *(and still feel)* like that list was missing some of the components and APIs that will shape the Web of the future and fundamentally change its ecosystem. Stuff like:

 - [Web compontents](http://webcomponents.org/) (Shadow DOM, Templates, HTML Imports and Custom Elements)
 - WebRTC
 - Web Notifications API
 - Push API
 - Web Crypto API
 - Plugin platform
 - WOFF2
 - WebM & WebP
 - `<picture>`
 - SVG favicon *(I'm super cerial)*
 - Better `<input>` support


I could go on to add *WebSQL*, *ASM.js*, *Dart* or even *TypeScript* native VM, `<menu>` support, and I'd still have a long way to go. Also, the option to sync on multiple devices without *OneDrive* and Windows integration would be nice, although, I don't mind doing it over a *Microsoft* Live ID.

### Uservoice

With the release of *Windows Technical Preview*, *Microsoft* also created a great portal &ndash; [IE Dev Feedback](http://uservoice.modern.ie) &ndash; for the particular purpose of including users in the roadmap creation process. There you can vote for most of the things I've mentioned above, or add your own suggestions.


I don't want to be the one to put words in your mouth but we could use stuff like better support for DOM4 *(does `.remove()` method ring any bells?)*, fixing the FOUT in Internet Explorer 11 (*if not Font Loading API then at least the 3s display delay*), maybe fixing bugs with width calculation and overflow in flexbox children.


Don't get me wrong, there's a huge deal of things *Microsoft* did really well, and even better than the others.


 - [MSDN's Internet Explorer Dev Center](http://msdn.*Microsoft*.com/en-us/library/ie/bg125382) - Great resource for developers working with IE
 - [modern.ie](http://modern.ie) - Provides great resources for developers including VMs for Internet Explorer testing
 - Aforementioned Uservoice feedback platform
 - Windows integration

### Internet Explorer on Linux and Mac OS X

Being a Ubuntu user, I was thrilled to find the **free pre-deployed VMs for Internet Explorer testing over at [modern.ie](https://www.modern.ie/en-us/virtualization-tools#downloads)**. Compared with Safari, and Apple's strategy for Web improvement (*which seems non-existant*), Microsoft exited its comfort zone and provided developers on other platforms a way to keep Internet Explorer on their mind while they code.

<div class="ta-c">
<figure>
<img src="http://marxo.me/public/upload/ie11onubuntuvm.png" alt="Internet Explorer 11 on Ubuntu (using VirtualBox)">
<figcaption>Internet Explorer 11 on Ubuntu (using VirtualBox)</figcaption>
</figure>
</div>

### Windows integration

Some might not think a great deal of these features, but I find them very useful, and **I think that users would greatly benefit from OS integration if other browsers were to implement it**. *Microsoft*'s flagship web product is the one to promote Pinned Sites, Live Tiles, Jump Lists, colorization of the UI chrome, and `that's only logical`.


Exactly why I mentioned the SVG favicons earlier. **If we were to standardize and minify the meta behind these features, they'd probably get accepted earlier both by users and developers.** To be completely honest, as a developer, I'm not particularly fond of creating a dozen of meta declarations and raster images to accomodate each browser and resolution that will be obsolete in a year or so. I like to color IE's controls, it's good for branding, but when I end up with a 100 line `<head>` tag and single browser support, enthusiasm fades out.

## The F word &ndash; F12 Tools

<div class="ta-c">
<figure>
<img src="http://marxo.me/public/upload/f12_blank.png" alt="F12 Tools on Windows 8.1">
<figcaption>F12 Tools on Windows 8.1</figcaption>
</figure>
</div>

On broad shoulders of promise I've waited for the new Developer Tools in *Internet Explorer 11*. The only way to describe what I've got is &ndash; *Chrome's WebKit-era DevTools in a Metro UI*. And that's the least of my problems. I could use them, if they wouldn't crash on page refresh, on being idle for a minute, if it wasn't for random crashes and memory leaks. To be honest, there is a feature I like better than in *Chrome*, and that's the quick *CSS difference*. It doesn't have revision control but its UX is far better than in *Chrome*. Skipping only through your code exceptions in JS debugger was a cool feature, and Google copied it over in a heartbeat.


It's really not that hard to come up with stuff to add to those tools that no one else has, and that's the main reason for disappointment in F12 Tools for me. **We need better CSS profiling tools, performance analysis, refactoring tools &amp; linters, APIs to hook editors to, maybe an Emmet implementation in editor** To be fair, the F12 Tools are usable, when they actually work. I'd probably rename them to **F12 Tools (BETA)**, because that's the level of stability they provide.

## To put it all together

### Should Internet Explorer be a swearword?

```html
<!--[if lte IE 9]> Yes <![endif]-->
<!--[if gt IE 9]><!--> No <![endif]-->
```
**The main problem for Internet Explorer is its slow release cycle.** First and most voted feedback on Uservoice is to force automatic updates to older version of Internet Explorer. The best thing for IE is to switch to a rolling-release, and I bet that all developers will be ecstatic, less frustrated, and users will get a better UX and a safer web. It's a matter of evolution. Web is a living standard and releasing versions with year(s) long gaps is unacceptable.

I haven't mentioned IE 10 and older versions until now, because the nightmares should be left at work, and this article is a ray of hope for the future. Internet Explorer 11 is a decent step forward, but Microsoft needs to run and run fast. Internet Explorer Dev Feedback has some general, non-feature related ideas for the project ranging from "Switch to Blink" to "Force rolling-release updates". These will forge the future of Internet Explorer, and we can all participate. In case you need a way to target **browser** in CSS check out my post on [targeting Internet Explorer 10 and 11 in CSS](/target-ie-in-css/).**What do you think about these ideas?** [Check out the submissions](https://wpdev.uservoice.com/forums/257854-internet-explorer-platform?filter=top), comment below and share your thoughts.


Dif-tor heh smusma!