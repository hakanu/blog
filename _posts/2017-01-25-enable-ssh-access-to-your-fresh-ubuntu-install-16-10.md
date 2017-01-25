---
published: true
layout: post
category: ubuntu
title: Enable SSH access to your fresh Ubuntu install (16.10)
---
Leaving this here since I should not spend another hour to figure this out in my next fresh ubuntu install.

Install ssh server first:

`sudo apt-get install openssh-server `

And open the port:

`sudo ufw allow 22`

Find your IP address

`ifconfig`
