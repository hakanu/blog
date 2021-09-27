---
published: true
layout: post
category: linux
title: 'Solving ERROR: Bailing out Run fsck manually in arch linux #manjaro'
---
I was happy that I was finally out of Ubuntu world and getting used to the manjaro's sweet user experience with performant xfce. However, this just happened and my workstation didn't boot. It was the black screen with this error telling me to run fsck manually with a command prompt.

What worked for me:

```bash
# Run this to find all drives attached to your machine.
blkid

# Grab the one which seems to have some inode faults.
fsck /dev/sdb2

# Hit a to yes to all approve all fixes

exit  # Reboots the system.
```

Drive label can be in the form of It can be `/dev/sd[ab][0-9]`

Sorry for the potato image:

![](https://devdala.files.wordpress.com/2021/09/img_4176.jpg)