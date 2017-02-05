---
published: true
layout: post
category: python
title: 'Install latest #nodejs on raspberry pi (#raspbian)'
---
First add the source:

`curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash -`

Install just like normal - don't install node which is different.

`sudo apt install nodejs`

Now you can use it just like normal nodejs, this should output something like 7.blah

`node -v`

NPM comes for free as well.

`npm -v`