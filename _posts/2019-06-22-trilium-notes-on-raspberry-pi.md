---
published: true
layout: post
category: python
title: Trilium Notes on raspberry pi
---
[Trilium notes](https://github.com/zadam/trilium) is a knowledge base app I have been testing these days. Some notable features which beats other alternatives:

* Infinitely nested hierarchical notes
* Self hosting the server
* Builtin relation maps
* Web UI and desktop from the same source
* Sync just works
* Quick global and local search
* Scriptable UI and note functionality which I haven't used much tho.
* Builtin source code highlighting.
* Easy note export/import - no locking in
* Easy backup via sqlite copy
* Explicit logging
* SQL command line to query notes.

I will have a separate post of my journey. There are a million medium posts and 10s of note taking apps none of which can be acclaimed the best and feature complete. Because it's such a personal experience to use some features more than others.

For anyone who wants to test drive trilium on raspberry pi, here are my steps. Raspbian doesn't have full docker yet in the repos so [recommended method](https://github.com/zadam/trilium/wiki/Server-installation) to install is not really applicable until repos are updated.

The downloaded package has a nodejs binary and npm packages already installed but they don't work on raspi since it's ARM rather than normal x64 architecture. So you'd see an error like this when you run with `./trilium.sh`

> cannot execute binary file: Exec format error

Here is 

```shell
# Download the latest release from releases page.
wget https://github.com/zadam/trilium/releases/download/v0.33.2-beta/trilium-linux-x64-server-0.33.2-beta.tar.xz

# Uncompress the tar.xz file with tar.
tar -xf trilium-linux-x64-server-0.33.2-beta.tar.xz cd trilium-linux-x64-server-0.33.2-beta

# Get rid of prepackaged node modules, probably sqlite3 will complain
# due to the need of being built from the source.
mv node_modules node_modules_

# Reinstall node modules for raspberry pi by using raspi's npm in order to get the arm version's of the npm packages. # This will take long npm install 

# Create a screen or prepend nohup to node command to run it in the
# background
screen
# Don't use ./trilium.sh because it expects x64 linux as far as i understand since raspi is arm that node won't work with exec error. Instead use system wise nodejs.
node src/www
```