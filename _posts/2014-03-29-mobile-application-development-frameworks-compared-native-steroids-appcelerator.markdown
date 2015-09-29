---
layout: post
title: Mobile Application Development Frameworks Compared - Native, Steroids, Appcelerator,
  Kivy
date: '2014-03-29 00:49:46'
---

<a href="http://devdala.files.wordpress.com/2014/03/tumblr_n2k138yetg1st5lhmo1_1280.jpg"><img class="aligncenter" alt="" src="http://devdala.files.wordpress.com/2014/03/tumblr_n2k138yetg1st5lhmo1_1280.jpg" width="1280" height="844" /></a>

<em>Disclaimer: I'm not an expert on mobile application development. Just a newbie leaning towards the direction of the strong blaze.</em>

I would like write my trials with the frameworks that I've tried to use to make mobile applications, especially for android. In this process, I had some hands on experience with Appgyver Steroids, Titanium Appcelerator and finally native android SDK.

Some background: Steroids is a framework developed on top of Adobe's phonegap which gives you chance to create platform agnostic mobile apps by using HTML, CSS and Javascript. While doing this, it uses Apache cordova.js to connect with low level phone APIs like camera, accelerometer, gyro etc.

&nbsp;
<h1 style="text-align: center;">Native</h1>
<h2>Outcome</h2>
Fully native and optimized app
<h2>Development speed</h2>
Initially slow, after ramping up on SDK, decent.
<h2>App performance</h2>
Superfast
<h2>Environment</h2>
ADT(Android Development Tools), Android Studio
<h2>Debugging</h2>
Super easy with Eclipse java debugging capabilities
<h2>Emulator</h2>
Large variety of emulators
<h2>Performance factors</h2>
Java is a beast. You can do all fancy thread stuff here. Of course there are rules around threading to make Android safer.
<h2>Trial run on real device</h2>
Need to connect real device to computer at all times. Emulators starting times are so painful
<h2>Ease of use of advanced device capabilities</h2>
Just modify AndroidManifest.xml and that's it
<h2>Monetization</h2>
Full support of Google AdMob and Analytics.
<h2>Creating apk</h2>
Happens on your local, extremely easy signing, unsigned apk creating, zipaligning.
<h2>Is it free?</h2>
Free, Google Play Store developer account 25$
<h2>Based on</h2>
Java
<h2>Community</h2>
Almost everything is replied in stackoverflow, google has large documentation of frameworks
<h2>Cons</h2>
You only create application for android, creating layouts are taking a lot of time. Java is full of boilerplate code.
<h2>Pros</h2>
Superfast applications compliant with the standards

&nbsp;
<h1 style="text-align: center;">Steroids (Phonegap)</h1>
<h2>Outcome</h2>
App with native tab bar and navigation bar placed around native WebViews which renders designed HTML pages
<h2>Development speed</h2>
Initially increadibly fast, when fine tunes starts everything becomes slower. Adding a share button is like a torture
<h2>App performance</h2>
Decent if you optimize your logic and CSS correctly
<h2>Environment</h2>
Wherever you can write JS:P Preferably Webstorm or Sublime Text
<h2>Debugging</h2>
Without mac and xcode, increadibly painful. Browser debugging is ok until some point but it does not provide necessary features like phone.
<h2>Emulator</h2>
Only iphone emulator which needs mac and xcode. Good luck for linux developers.
<h2>Performance factors</h2>
So hard to optimize the app after some point. You are stuck with stock browser capabilities. Android devices have whopping CPU and RAM but ios devices' browsers are not capable of rendering at the same speed.
<h2>Trial run on real device</h2>
Steroids system is awesome. It generates a QR code and you can it with appgyver scanner from your device, boom! The app starts in your device without connecting any cable. Everytime you modify the code and hit enter in the console, it reloads the app from all open tabs and devices. Saves a lot of time
<h2>Ease of use of advanced device capabilities</h2>
Cordova.js is so advanced but even small operations like taking photo sometimes becomes so painful to run.
<h2>Plugins</h2>
The most powerful part of phonegap and steroids. There a lot of plugins outside. However this is also a weakness. It's hard to find which one will work for you. A simple example: Pull to refresh. You can find 100 pull to refresh js library. It's so hard to make one to work for you as if native.
<h2>Monetization</h2>
A couple of admob plugins.
<h2>Creating apk</h2>
Need to use free appgyver service. You need upload your keystore and write your keystore and alias password.
<h2>Is it free?</h2>
Free but there are paid official plugins, Google Play Store developer account 25$
<h2>Based on</h2>
Nodejs
<h2>Community</h2>
There is a forum but getting a decent answer is tough. There are lots of questions asked
<h2>Cons</h2>
Still early stages, major changes between versions. Needs careful optimization. Highly dependent on stock browser performance.
<h2>Pros</h2>
Platform independent applications developed with fully HTML, CSS and JS
<h2></h2>
<h1 style="text-align: center;">Appcelerator Titanium</h1>
I need to admit that I didn't have much experience with this.
<h2>Outcome</h2>
Fully native app created from javascript code written by developer
<h2>Development speed</h2>
Small learning curve of titanium js framework (alloy)
<h2>App performance</h2>
As fast as native maybe because it's native:P
<h2>Environment</h2>
Dedicated IDE with designer view, modified version of eclipse
<h2>Debugging</h2>
Should be easy from dedicated IDE
<h2>Plugins</h2>
Official plugins seriously supported
<h2>Monetization</h2>
Official AdMob plugin
<h2>Creating apk</h2>
Need to use free service
<h2>Is it free?</h2>
Free
<h2>Based on</h2>
Javascript (Alloy MVC framework)
<h2>Cons</h2>
Apps look so last corporate: <a href="http://www.appcelerator.com/customers/app-showcase/" target="_blank">http://www.appcelerator.com/customers/app-showcase/</a>
<h2>Pros</h2>
Write in one language (JS) and create applications for 3 major mobile platforms

&nbsp;
<h1 style="text-align: center;">Kivy</h1>
Ok, I didn't have intention to write about kivy but I think it deserves to write a corner in this post. Kivy is my first lover. It's python UI framework which outputs for all of the platforms you can imagine:) Android, IOS, Windows, Mac OS, Linux etc.

I like python and I was so lazy to learn a new framework which is Native framework of Android; I started with this little guy. The development iterations are incredibly fast, because you write the code and run on the terminal directly, no need to connect device check adb logcat. Everything is on the terminal. A bit of a learning to understand the interaction of kv files and python code. However it is like normal UI design philosophy: Separate designer and coder. In my case I was both. I wrote my first game which is a pong in 20 minutes with the first tutorial. Site also provides you a VMs to output an apk, exe, ipa(not sure about this one) locally. I setup my computer and did not use VM. I got my apk, signed it and installed in my phone. Everything was good. App works with decent performance. However, I feel like this framework is mostly for making games. Not good for creating apps with multiple views. After all, it's in my heart because it's python &lt;3

<a href="http://kivy.org/#home" target="_blank">http://kivy.org/#home</a>
<h1 style="text-align: center;">Conclusion</h1>
Well, I'm not going to say this is the best. It highly depends on your needs. If you would like to create some proof of concept platform independent mobile application, go for steroids or phonegap (Your apps' beauty will highly be dependent on your design skills). If you are doing a job in enterprise level (boring looking apps:P), go for appcelerator. Will save you a lot of time. If you need to something rock solid and stable (this does not mean that other frameworks are unstable), go for native sdk.

By the way, there is a fact that we can not disregard, platform agnostic applications are getting some serious traction these days. You can see this from Mozilla's <a href="https://www.mozilla.org/en-US/firefox/os/" target="_blank">Firefox OS</a> which is fully using web standards, Google's exciting <a href="http://blog.chromium.org/2014/01/run-chrome-apps-on-mobile-using-apache.html" target="_blank">Chrome Apps on Mobile</a> framework. These two examples show that people are running away from writing native. They just don't want to make the same application for 3 different platform by writing in 3 different language which are Java for Android, Objective C for IOS, C# for WP (and Qt-C++ for blackberry).

I would like to talk about security. Of course it's developers' app security. If you use steroids, everybody can fully see your html, css and js files. No kidding it's real. Just check your file system. However, this statement is a little misleading. Because even native apk files are decompilable. As long as, you obfusticate your code and don't store any sensitive information like passwords in the code or in local database, you will be fine. You have to sign steroids apps as well.

My apps are here:
<a href="https://play.google.com/store/search?q=hakan%20uysal" target="_blank">https://play.google.com/store/search?q=hakan%20uysal</a>

With kivy: <a href="https://play.google.com/store/apps/details?id=co.hakanu.kliseci" target="_blank">https://play.google.com/store/apps/details?id=co.hakanu.kliseci</a>

With native sdk (formerly with steroids): <a href="https://play.google.com/store/apps/details?id=co.hakanu.karikaturcu2" target="_blank">https://play.google.com/store/apps/details?id=co.hakanu.karikaturcu2</a>

While writing this post, and here it is, yet another framework claims that it's better than phonegap:

<a href="https://trigger.io/" target="_blank">https://trigger.io/</a>

Some of my sources:

<a href="http://steroids.appgyver.com" target="_blank">http://steroids.appgyver.com</a>

<a href="http://www.appcelerator.com/" target="_blank">http://www.appcelerator.com/</a>

<a href=" http://www.quora.com/PhoneGap-Vs-Titanium" target="_blank">http://www.quora.com/PhoneGap-Vs-Titanium</a>

<a href="http://www.quora.com/Appcelerator-Titanium-vs-PhoneGap-which-produces-better-native-apps" target="_blank">http://www.quora.com/Appcelerator-Titanium-vs-PhoneGap-which-produces-better-native-apps</a>