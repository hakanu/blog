---
published: true
layout: post
category: raspberrypi
title: Enable x265 (HEVC) hardware decoding in  Raspberry Pi 4
---
My Emby Server struggles a lot during playing x265 formatted videos, it gets stutters every 3-4 seconds. Very annoying. I resolved like this:

* Edit `/boot/config.txt`: sudo vim /boot/config.txt
* Add this line to the end

```
dtoverlay=rpivid-v4l2
```
(More details about [v4l2](https://www.reddit.com/r/jellyfin/comments/wpaxl8/raspberry_pi_4_using_v4l2/))

* Save the file.
* Reboot the pi: `sudo reboot now`

If this doesn't solve your problem, check out the HEVC support in your browser. The client consuming emby content should also be compatible.
