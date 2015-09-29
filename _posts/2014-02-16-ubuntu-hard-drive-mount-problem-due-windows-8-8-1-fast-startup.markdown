---
layout: post
title: Ubuntu hard drive mount problem due to Windows 8 and 8.1 fast startup
date: '2014-02-16 19:56:33'
---

I really like windows 8 and windows 8.1. Especially if your laptop is optimized for w8, it boots up blazing fast, restarts lightning fast, shuts down incredibly fast.  However, the problem is that I don't really use w8 (only for gaming, photoshop and flash). I have just recently upgraded my w8 to w8.1 and forgot to shut down fast startup. It took me 5-6 times rebooting to understand the problem. Every time I log in to ubuntu, it could not mount NTFS drives and gave an error like "This drive is locked by windows, do not hibernate blah blah". Although I was always shutting the windows down, <em>fast startup</em> was enabled and it was not releasing the lock on the hard drives.

Ubuntu hard drive mount problem is caused by Windows 8 and 8.1 fast startup. To turn it off follow the steps here:
<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2014/02/power1.png"><img class="aligncenter" alt="" src="http://devdala.files.wordpress.com/2014/02/power1.png" width="560" height="400" /></a></p>
<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2014/02/power2.png"><img class="aligncenter" alt="" src="http://devdala.files.wordpress.com/2014/02/power2.png" width="560" height="400" /></a></p>