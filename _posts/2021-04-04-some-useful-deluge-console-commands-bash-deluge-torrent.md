---
published: true
layout: post
category: bash
title: 'Some useful deluge-console commands #bash #deluge #torrent'
---

I keep forgetting deluge commands so let me put it here for myself. Many of them are self explanatory but I'm dumb and keep forgetting.

1. Create `screen`
1. Start deluge service: `deluged`
1. Start deluge console `deluge-console`
1. Add a new torrent: `add magnet-link`
1. List the torrents being downloaded: `info`
1. Remove a torrent (eg finished torrent without removing the data): `rm torrent-id`  (You can find the id from previous command.)
1. Pause a torrent `pause torrent-id`
1. Continue paused torrent `resume torrent-id`
1. Exit: `exit`

[All commands with more params](https://whatbox.ca/wiki/Deluge_Console_Documentation)

Alternatively if you are a GUI person, you can use `deluge-web` command in a `screen` to observe using web UI even with authentication:

Default port for deluge-web is `8112`, so just navigate to http://my_deluge_server_ip:8112

[More info](https://dev.deluge-torrent.org/wiki/UserGuide/ThinClient)

What's deluge and how to download: https://deluge-torrent.org/