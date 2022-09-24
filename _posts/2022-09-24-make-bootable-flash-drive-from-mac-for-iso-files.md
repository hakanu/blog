---
published: true
layout: post
category: linux
title: Make bootable flash drive from mac for ISO files
---

* Download the iso file somewhere online. In this example I will do manjaro bootable usb pen drive from xfce minimal image.
* Fire up the terminal, run these commands.

```bash
# Find which one is your flash drive
diskutil list

# In my case it was /dev/disk3
diskutil secureErase 1 /dev/disk3

cd Downloads/
ls
hdiutil convert manjaro-xfce-21.3.7-minimal-220816-linux515.iso -format UDRW -o manjaro-xfce-21.3.7-minimal-220816-linux515.img
diskutil unmountDisk  /dev/disk3
sudo dd if=manjaro-xfce-21.3.7-minimal-220816-linux515.img.dmg of=/dev/disk3 bs=1m
```