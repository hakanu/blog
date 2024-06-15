---
published: true
layout: post
category: android
title: Fixing always portrait apps in Huawei Tablet (Harmony OS)
---
I got a cheap Huawei Tablet (Mate Pad Air) last year with very very good hardware, amazing screen, super snappy. All my tablet-worthy apps (photo/video editing and kids coloring pages apps) work great so it's definitely a good deal for me. Among all the annoying things (no Google Play Store, not-as-apple-pencil quality stylus, inferior OS experience etc), the apps lock themselves into portrait mode regardless of the orientation of the tablet. Well it's a tablet with keyboard which is always in the landscape mode. However, apps like Reddit, DJI Mimo etc always open themselves in portrait, forcing me to tilt the tablet with keyboard (or instead throw it to the wall).

I tried multiple things to solve the issue. Nothing helped, finally I stumbled upon a reddit post, I immediately opened it in my tablet, boom it got portrait-ed, I didn't give up and read the post.

Apparently this is a common issue with wide devices, especially foldables and tablets. Since the manifacturers are lazy enough to fix these (small?) annoyance, Google introduced a method where the actual users can fix issue themselves, which is making the tablet ignore apps' specification of rotation.

Steps are easy in the post, I need to connect via adb and then run this adb command. however nothing is easy.

1. Get the adb for windows, I'm nice enough so putting a [link here](https://dl.google.com/android/repository/platform-tools-latest-windows.zip) to download and use adb without installing Android Studio and other gigabytes of software.
1. Now unzip and open terminal inside
1. ./adb.exe devices => Nothing happens. Because you didn't enable usb debugging in the tablet yet.
1. Go to tablet => Settings => System => Touch Software version multiple times to enable developer options.

![Screenshot_20240615_234007.jpg]({{site.baseurl}}/images/Screenshot_20240615_234007.jpg)

1. Enable usb debugging, hopefully once you do that if you have data + charging usb-c cable, your tablet should prompt you if it should trust this computer. If this doesn't show up, sorry, more steps are coming. Try to unplug and re-plug the cable, consider enabling usb debugging while charging too, maybe dangerous so don't make it permanent.
1. Then if it still doesn't work, try this, this did the trick for me: modify USB configuration from MTP (Media Transfer Protocol) to RNDIS (USB ethernet), then boom it asked if it should trust my pc. I approved and adb devices started to show my tablet.

![Screenshot_20240615_234748.jpg]({{site.baseurl}}/images/Screenshot_20240615_234748.jpg)

1. And then finally we can run the magical command: .\adb.exe shell wm set-ignore-orientation-request -d 0 true

1. It should silently finish, no errors. Then fire up reddit app while your tablet is in landscape mode.

![]({{site.baseurl}}/images/Screenshot_20240615_235054_com.reddit.frontpage.jpg)

Looks ugly, doesn't use all the estate but who cares, I don't need to rotate the tablet physically anymore.
