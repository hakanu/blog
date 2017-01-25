---
published: true
layout: post
category: iot
title: Simplest Raspberry Pi 3 setup as a home server - Jan'17
---
I've just done it and I don't want to forget this struggle.

![](https://lh3.googleusercontent.com/OkpftC-4ZQxAoF90yn3s6U86yaUvYSAPoO5_bTIrYDezc_JhWsRSjrquFBtzowH5UYVTMsEolxGhpNSiyBRPZHE9ecOn-wWvYVc4DO0K1xW9BfRoGc_Am91wqv4YdVvagHZZJvgnIXp-cEV242iTzV3PmQESBqLwcIefFIgaMqWueUfXXqJdiUEoveYzmaBNmoJZo6wmmCdO1hlULwll1AAYCclDdTI3vOXU_I6IcUW6WOtEMPa_N7sW_z_NUm1u8-VZqkP5n4e6w6WF6u_mM1_X1mGEAV3nVPu_di-QLhYIgR9NOAd89VZkxhzHmcVldAi4FveL5Ufmgtd6eXprQDnNeZ0Z1m3lwD_Cmf4quWSI8vgDnQ6VNyKrE8ABFTXHyevC3QkDphHS_Ihp_PVP6PvYZrrFSILselmZjV1G6tFudVl_rStGBLBsXoqxpXyGUTlTHMKq7Tnkzn4w7so2A2pihgqw4Jks5s39Nbgv6DUJmfXu_56MqWoMmd9UVX40kcstZT8hNaIYUZ5nCoKIdvzEAMrm5_QXJWilrQqkzRE8SYVLr_zfjuNEuQbhxOQx8cr6iSrPcwCkyh91PrHjkv4gNILxsU-3QueM7PklKZ_QrKkqz6ZD6A=w725-h966-no)

- [Buy a super fast 32 gb sd card](https://www.amazon.co.uk/s/ref=nb_sb_noss?url=search-alias%3Daps&field-keywords=micro+sd+card+32+gb) - keep your adapter because most of the new computers only have sd card slots not micro sd slots.
- Format sd card as FAT - MSDOS with 
  - Disk utility -> Erase on Mac
  - Right click -> Format on Windows
  - Disks on Ubuntu
- [Download NOOBS](https://www.raspberrypi.org/downloads/noobs/) - easy UI to select which OS should be installed into your pi. Don't bother flashing yourself with raspbian etc.
- Extract NOOBS zip and copy all of the files (if it's extracted into a folder just copy its content, root of the sd card must have a couple of files, not one directory)
- Put your recently formatted and NOOBs copied sd card into the pi and then wait a little bit
- Plug your raspberry pi into micro usb
- Plug your monitor via an HDMI cable
- Plug your mouse and keyboard (mechanical keyboards take some time though to be recognized, just wait a little bit more)
- NOOBS UI will show up, for raspberry pi 3 you can connect to wifi. You can either install the GUI supported Jessie version of raspbian or you can go for other and check your other options. They will be downloaded if you choose
- I don't want a UI since I only want a server. So I went with the Jessie lite which is 1 GB smaller than Jessie itself and it doesn't have X server. I believe it makes everything faster. I have chromecast so I don't need yet another media center.
- Let's enable the SSH first. Because after Nov'16 raspbian doesn't come with ssh enabled by default. you need to manually enable, so: `sudo raspi-config`
- Side note: there is no ufw in raspbian unlike default desktop ubuntu. So don't try to enable your port 22 with `sudo ufw allow 22`, it won't work :)
- Advanced settings -> SSH -> Enable SSH server
- default username: **pi** default password: **raspberry**
- Change the default password: `sudo passwd pi`
- enter new password
- To find out the IP of your raspberry pi: `ifcongif` - I assume you connected with cable. For wifi it's a little bit different.
- Connect from other computer to your raspberry pi so you don't need to connect any mouse or keyboard: `ssh 192.168.0.x` (Replace x according to the output of the ifconfig ran on raspberry pi). Or you can use this handy command to find out what devices are connected to your network with which IP: `sudo nmap -sP -n 192.168.0.0/24`

- Check your free ram: `free -m`
835 mb of RAM niceuuhh!
