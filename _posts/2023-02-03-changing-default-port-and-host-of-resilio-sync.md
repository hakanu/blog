---
published: true
layout: post
category: python
title: 'Changing default port and host of Resilio Sync '
---
![](https://devdala.files.wordpress.com/2023/02/screenshot_20230203_082422.png)

Why does it have to be so hard. Good docs but there is no good documentation about the default configuration directory. For linux it's `/etc/resilio-sync/config.json`

If you want remote server to be accessed remotely you gotta bind 0.0.0.0 and default resilio port is 8888.

Open it up:

```
vim /etc/resilio-sync/config.json
```

Add this snippet:

```json
{
"use_gui": false,
  "webui" :
  {
    "listen" : "0.0.0.0:9999"
  }
}
```

If you haven't installed, it's like this for linux (or raspberry pi):

```bash
echo "deb http://linux-packages.resilio.com/resilio-sync/deb resilio-sync non-free" | sudo tee /etc/apt/sources.list.d/resilio-sync.list

curl -L https://linux-packages.resilio.com/resilio-sync/key.asc | sudo apt-key add

sudo dpkg --add-architecture armel && sudo apt-get update && sudo apt-get install resilio-sync:armel

sudo apt-get update

sudo apt-get install resilio-sync
```