---
published: true
layout: post
category: selfhost
title: >-
  How to know if your laptop is bypassing the battery and using AC power
  directly
---
I do lots of self hosting and some of my machines are old laptops with lids closed.

However, it's not always possible to remove the battery from the laptop and use it with only AC power due to new slimmer laptops have embedded batteries.

If you have a battery discharging and charging 365/7/24 then you may start getting swollen battery and fire hazard arises. if you are a self hoster at home, noone wants that.

Here are some bash commands to know if your battery is being used or direct AC power is used.

```bash
sudo cat /sys/class/power_supply/AC0/online
# cat: /sys/class/power_supply/AC0/online: No such file or directory

sudo cat /sys/class/power_supply/BAT0/status
# cat: /sys/class/power_supply/BAT0/status: No such file or directory

ls /sys/class/power_supply/
# ADP1  BAT1

cat /sys/class/power_supply/ADP1/online
# 1

cat /sys/class/power_supply/BAT1/status
# Not charging
```