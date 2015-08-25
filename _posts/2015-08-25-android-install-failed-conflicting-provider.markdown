---

layout: post
category: android
author: Hakan Uysal
title: Solving Android's INSTALL_FAILED_CONFLICTING_PROVIDER
date: '2015-08-25 16:31:13'

---

Yet another problem that made me lose 3-4 hours. 

Well, I usually use the same code across my application, I have my basic scaffolding. It only gets better in time. However, sometimes I forget to change the package names, XML namespace definitions etc while copy/pasting. I thought this is also same problem. But I couldn't find anything.

Surprisingly, this occurs after you submit the application to the play store.

While application X is installed, Google Play Store does not let another application with the same provider to get installed.

Error it throws:

	"Some application" can not be installed. Try again, and if the problem continues, get help troubleshooting. (Error code: -505)

Troubleshooting did not help me, in product forums they only recommended cleaning up cache of google play store  app etc. But this problem is not related to neither your phone nor your play store application. It persists in different operating systems and different phone models. What you need to do is simple, follow me.

![](https://devdala.files.wordpress.com/2015/08/screenshot_2015-08-25-08-59-49-compressor.png)

### Steps to do

* Check your both applications' AndroidManifest.xml
* android:authorities tag is the problem.
* In my case I copied the same facebook content provider code from AndroidManifest.xml
*         `<provider
           android:name="com.facebook.FacebookContentProvider"
           android:authorities="com.facebook.app.FacebookContentProviderYOUR_FACEBOOK_APP_ID"
           android:exported="true" />`
* I should have changed my facebook app id because they are different apps.

As you can see, copy/pasting sometimes makes you lose more time than you gain.

Enjoy!