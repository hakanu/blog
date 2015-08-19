---
layout: post
title: Solving Android java.lang.NoClassDefFoundError: android.support.v7.appcompat.R$attr? Once for All for pre-Lollipop devices
date: '2015-05-03 16:31:13'
---


This secret recipe makes your apps work on pre-lollipop devices. You may be developing on Android 5.0+ and you would not realize that your app is breaking at the start for other versions of Android which are lower than Lollipop.

Trick is that Apps with lots of dependencies (well they don't have to a lot but if you have google play services as dependency which is needed for admob, you should apply this method) need multidex enabled for building. Otherwise they work fine on L devices and fails at the startup for pre-L devices.

[Android Twitter Crashes with Appcompat v7 on API 19 and lower]https://twittercommunity.com/t/android-twitter-crashes-with-appcompat-v7-on-api-19-and-lower/34121

[Building Apps with Over 65K Methods
](https://developer.android.com/tools/building/multidex.html)

https://twittercommunity.com/t/android-twitter-crashes-with-appcompat-v7-on-api-19-and-lower/34121

https://twittercommunity.com/t/noclass-found-error-in-android-studio-lower-than-5-0/33518/3

[Why am I still getting java.lang.NoClassDefFoundError: android.support.v7.appcompat.R$attr?](http://www.metaandroid.com/question/why-am-i-still-getting-java-lang-noclassdeffounderror-android-support-v7-appcompat-rattr/)

## Don't do this:

`<application
    ...
    android:theme="@style/Theme.AppCompat" >`

## Do This

1. Change AndroidManifest.xml

`<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.android.multidex.myapplication">
    <application
        ...
        android:name="android.support.multidex.MultiDexApplication">
        ...
    </application>
</manifest>`

2. Add this to the build.gradle

`defaultConfig {
        applicationId "net.guldum.caps"
        minSdkVersion 16
        targetSdkVersion 22
        versionCode 9
        versionName "1.8"
        multiDexEnabled true
    }`
    
`dependencies {
    compile 'com.android.support:multidex:1.0.0'
}`