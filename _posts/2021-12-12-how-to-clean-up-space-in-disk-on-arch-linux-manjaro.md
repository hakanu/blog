---
published: true
layout: post
category: linux
title: How to clean up space in disk on Arch Linux (manjaro)
---
![](https://devdala.files.wordpress.com/2021/12/screenshot_2021-12-12_23-13-10.png)

1. Use something like [Disk Usage Analyzer](https://wiki.gnome.org/action/show/Apps/DiskUsageAnalyzer)
1. `df -h` is your friend.
1. clean up `/var/log/` journald files.
```bash
journalctl --vacuum-size=128M
```
1. Clean up pacman cache (analogous to `sudo apt autoclean` in ubuntu and debian)
```bash
sudo pacman -Scc
```
