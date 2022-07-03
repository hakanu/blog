---
published: true
layout: post
category: linux
title: >-
  Resolve apt update problem on raspberry pi: "This must be accepted explicitly
  before updates for this repository..."
---
This is what i get from my old raspi 4b:

```bash
sudo apt-get update
Get:1 http://archive.raspberrypi.org/debian buster InRelease [32.6 kB]
Get:2 http://raspbian.raspberrypi.org/raspbian buster InRelease [15.0 kB]
Hit:3 https://deb.nodesource.com/node_15.x buster InRelease
Hit:4 https://dl.yarnpkg.com/debian stable InRelease
Get:5 https://pkgs.tailscale.com/stable/raspbian buster InRelease
Reading package lists... Done
E: Repository 'http://raspbian.raspberrypi.org/raspbian buster InRelease' changed its 'Suite' value from 'stable' to 'oldstable'
N: This must be accepted explicitly before updates for this repository can be applied. See apt-secure(8) manpage for details.
E: Repository 'http://archive.raspberrypi.org/debian buster InRelease' changed its 'Suite' value from 'testing' to 'oldstable'
N: This must be accepted explicitly before updates for this repository can be applied. See apt-secure(8) manpage for details.
```

## Solution

Run this random sudo command you found online.

```bash
sudo apt-get update --allow-releaseinfo-change
```

And now `sudo apt-get upgrade` should do its magic.