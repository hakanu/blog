---
published: true
layout: post
category: linux
title: Some useful bash commands to find large files and directories
---
I hate the small disks, it blocks apt update/upgrade commands usually.

```bash
# Top 20 largest folders (directories, i was windows guy)
du -a | sort -n -r | head -n 5

# Top 20 largest files in home folder (directory)
du -a /home | sort -n -r | head -n 5

# My favorite:
du /* -hsx | sort -rh | head -20

# take a look at /tmp
ls -lah /tmp

# Kernel directories are another suspect.
# Check your kernel version
uname -r

# This folder is probably a culprit.
du /usr/* -hsx | sort -rh | head -20
ls /usr/src -lah

# Clean up journalctl logs
journalctl --vacuum-time=2d  # Retains last two days

# Clean up apt cache.
sudo apt autoclean
sudo apt autoremove
sudo apt clean
```

If your problem is excessively space occupying old kernel versions: Consider getting rid of the ones which are older than your kernel appropriately.

du -> sort command may fail if there is 0 space.

Check this post out to open up some space on Manjaro
[How to clean up space in disk on Arch Linux (manjaro)
](https://hakanu.net/linux/2021/12/12/how-to-clean-up-space-in-disk-on-arch-linux-manjaro/)

Check this post out to open up some space on Raspbian linux running raspberry pi:
[Free up space in debian server while apt-get commands are failing
](https://hakanu.net/debian/2019/11/28/free-up-space-in-debian-server-while-apt-get-commands-are-failing/)
