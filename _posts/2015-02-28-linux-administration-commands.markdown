---
layout: post
title: Small bash commands for linux administration
date: '2015-02-28 01:26:43'
---

[![](https://distilleryimage3-a.akamaihd.net/fac1ecea8f6111e2b3e122000a1f9a4f_7.jpg)](https://instagram.com/uhakan/)

Mostly useful for Ubuntu or debian based operating system.

### Top 10 largest directories

`du -a /var | sort -n -r | head -n 10`

### Find largest files on Linux

`find / -size +10M -ls`

`find / -size +700M -ls`

### Top 10 processes by memory 

`ps aux --sort -rss | head`


### Bash check timing time measure

`time ls /bin`

`time mongo --eval "db.users.find({})"`

### batch file extension renamer in bash

`for file in *.png; do
    mv "$file" "`basename $file .png`.jpg"
done`

#### Create bootable disk (usb) from image

`sudo dd bs=4M if=/home/$USERNAME/path/to/2014-09-09-wheezy-raspbian.img of=/dev/sdd`

### Update & upgrade packages

`sudo apt-get update`

`sudo apt-get upgrade`

### Clean up packages for saving up disk space

`sudo apt-get clean`

### Scan the local network for connected devices with IPs.

`sudo apt-get install nmap`

`sudo nmap -sP 192.168.0.0/24`


### Python setup tools

`sudo apt-get install python-setuptools`

`sudo easy_install web.py`

### SSH into a remote computer
`ssh name@hostname`

### Pipe both standart output and error into a file
Useful for logs

`./some_binary >> logs.txt 2>&1`

My usual run structure for unique log files:

`./some_binary >> logs_`date +%Y%m%d_%H%M%S`.txt 2>&1 &`