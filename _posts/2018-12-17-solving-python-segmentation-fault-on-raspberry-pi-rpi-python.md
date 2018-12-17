---
published: true
layout: post
category: python
title: 'Solving python segmentation fault on raspberry pi #rpi #python'
---
Faced with this the other day. Out of blue, can not execute any python script; python console was working fine though. Probably I corrupted the interpreter on the due to some sd card error. Anyways virtualenv didn't resolve the issue. So found this code snippet below which took a couple of hours to finish but resolved my problem. I didn't need to reformat my sd card.

```bash
for pkg in `dpkg --get-selections | awk '{print $1}' | egrep -v '(dpkg|apt|mysql|mythtv)'` ; do apt-get -y --force-yes install --reinstall $pkg ; done
```
