---
layout: post
title: My First Native Android App
date: '2014-03-23 23:24:31'
---

Learning new stuff, leaving your comfort zone is always hard. I like python, I like my python frameworks, I like html, css and javascript. Why would I learn yet another framework? Native SDK of android was something I have been running away for a long time. However, after trying 3 alternative frameworks which are <a href="http://kivy.org/">Kivy</a>, <a href="http://x.appgyver.com/">steroids</a> and <a href="http://www.appcelerator.com/">titanium</a>. Finally, I decided to try native. I will write a comparison among those 3 frameworks soon.

Here is the application:

<a href="https://play.google.com/store/apps/details?id=co.hakanu.karikaturcu2">https://play.google.com/store/apps/details?id=co.hakanu.karikaturcu2</a>
<p style="text-align: center;"><a href="https://lh5.ggpht.com/KRGrEZka9lz-dtgpEV61-69JXhTwoijVch8kwidr9HoXvcQPMVnCksXxna72-84AphY=h900-rw"><img class="aligncenter" alt="" src="https://lh5.ggpht.com/KRGrEZka9lz-dtgpEV61-69JXhTwoijVch8kwidr9HoXvcQPMVnCksXxna72-84AphY=h900-rw" width="324" height="540" /></a></p>
It's not saving the world, just showing some random comics, making you save your favorites into local storage and share via your apps. It was a good training application for me.

There is a big misunderstanding among newbie mobile developers. Going with html or js is not always good. It depends on your use case. Sometimes putting a share button would be a real pain with html (phonegap and steroids). However, with native SDK, you can have an easy share button with a couple of lines of code. You don't need to write to code share with different applications. One button to rule them all!

Another thing is monetization. It's always painful with non-native apps. There are a couple of plugins for phonegap for admob. There is an official plugin for titanium. For kivy, the best way to integrate admob is fetching url manually and creating the widget by yourself, no plugin as far as I remember.

Even if my app looks so simple, there are significant number of challenges I have faced during the development:
<ul>
	<li>Tabbed swipe view: Eclipse creates it when you choose navigation type. Needs some learning curve to customize it. I'm still trying to figure out</li>
	<li>Fragments: Each swiped view is a fragment.</li>
	<li>SQLiteHelper: Local sqlite storage to store favorite comics.</li>
	<li>Async tasks: Download images without blocking the UI.</li>
	<li>Custom listview: Default listview only shows lines of texts in the list. I needed to show image and two buttons in each row. ArrayAdapter is your friend here.</li>
	<li>Share button: This one is easy. I'm gonna share it's code soon.</li>
	<li>Share menu button: Add share button ad the top. This one is also easy.</li>
	<li>Updating an application in play store: Surprisingly yes, that one was tough. I need to sign it with my previously uploaded app's keystore and alias. Ok, this is not the hard part. The problem was that I don't really remember what was my keystore and alias password.</li>
</ul>
&nbsp;