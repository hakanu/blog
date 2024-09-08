---
published: true
layout: post
category: bash
title: Mount exfat with read write access
---
My external hdd i'm trying to mount to debian NAS server through usb is giving me permission denied access for write; it can only read which is not enough for my use case.

`-o rw` doesn't work alone. Gemini keeps giving me only -o rw option for some reason.

```bash
sudo mount /dev/sdg1 /mnt/hdd_exfat/  -o  rw,uid=1000,gid=1000
```

If this still doesn't work try this

```bash
# unmount first
sudo umount /dev/sdg1

# Change the ownership of the mounting point.
sudo chmown $USER:$USER /mnt/hdd_exfat

# Remount
sudo mount /dev/sdg1 /mnt/hdd_exfat/  -o  rw,uid=1000,gid=1000
```
