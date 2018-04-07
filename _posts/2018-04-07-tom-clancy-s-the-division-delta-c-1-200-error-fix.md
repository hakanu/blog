---
published: true
layout: post
category: python
title: Tom Clancy's The Division- Delta C 1-200 error fix
---
![](https://mobile.donanimhaber.com/store/60/3e/df/603edfafc9b1c1c57c4be37a4131f02d.jpeg)

- Open network and sharing center;
- Click on your network;
- Click on Properties button;
- Choose TCP/IPv4 and on Properties button;
- Enter Google's dns: 8.8.8.8 and 4.4.4.4;
- Run cmd as administrator;
- Enter following commands:
  - `ipconfig /flushdn` and press Enter.
  - `ipconfig /registerdns` and press Enter
  - `ipconfig /release` and press Enter.
  - `ipconfig /renew` and press Enter.
  - `netsh winsock reset` and press Enter.
- Reboot your computer.
- Turn off your firewall
