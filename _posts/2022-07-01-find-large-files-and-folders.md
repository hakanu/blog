---
published: false
layout: post
category: linux
title: 'Find large files and folders '
---
I hate vps with small disk.

```bash
# General situation
du /* -hsx | sort -rh | head -20

# Check your kernel version
uname -r

# This folder is probably a culprit.
du /usr/* -hsx | sort -rh | head -20
ls /usr/src -lah

# rm the ones which are older than your kernel.

du /lib/modules/* -hsx | sort -rh | head -20


```
