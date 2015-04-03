---
layout: post
title: Ubuntu USB mouse scrolling problem workaround
date: '2013-11-11 23:26:03'
---

<a href="http://devdala.files.wordpress.com/2013/11/ane17yg_460sa.gif"><img class="aligncenter" alt="" src="http://devdala.files.wordpress.com/2013/11/ane17yg_460sa.gif" width="390" height="264" /></a>

In Ubuntu 13.10, If you are using desktop based viewport switching which basically makes you change virtual desktops by scrolling to switch to next/previous desktop, you will possibly see this bug. Some of the core ubuntu apps are not getting scroll events if you are using a usb mouse. On the other hand, touchpad works just fine.

Here are some of the buggy apps which are affected by ubuntu usb mouse scrolling problem:
<ul>
	<li>nautilus</li>
	<li>gedit</li>
	<li>synaptic</li>
</ul>
Name: Regression: <em>Enabling typical bindings in "Desktop-based Viewport Switching" breaks scrollwheel scrolling in some windows with a usb mouse on a laptop</em>

Here is the bug: <a href="https://bugs.launchpad.net/compiz/+bug/1200829">https://bugs.launchpad.net/compiz/+bug/1200829</a>

What I understand is that it's related to gtk and the only way to solve is disabling desktop based viewport switching from compizconfig settings manager. To install it:

<code>sudo apt-get install compizconfig-settings-manager</code>

Let's wait for next ubuntu update.

PS: I have just updated my ubuntu 13.10, and still no fix of the bug.

&nbsp;