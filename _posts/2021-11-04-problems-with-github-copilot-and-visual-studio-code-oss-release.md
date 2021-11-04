---
published: true
layout: post
category: python
title: 'Problems with Github Copilot and Visual Studio Code OSS release '
---

I can only install VSCode through Manjaro's add/remove programs utility tool and it only has the open source version of the vscode which is called **Code OSS** and even it's tray icon is different. Anyways, I already have access to the copilot but haven't installed in manjaro.
Now whenever I try to run `ext install GitHub.copilot` in Ctrl + P console of Code OSS, it returns this error "No extensions found".

Thankfully solution was easy, just hit "Install from VSIX" from top right corner and download vsix from here and show it to vscode.
https://marketplace.visualstudio.com/items?itemName=GitHub.copilot

But then it asks to update the vscode to 1.57+ although I'm using 1.61. Lol. What you should do in case, since code OSS is a non-standard release, you need to enable some features (I found answer [here](https://github.com/github/feedback/discussions/6629#discussioncomment-1524627))

* Ctrl P
* Run `Preferences: Configure Runtime Arguments` command
* in the JSON file add following entry: `"enable-proposed-api":["github.copilot"]`
* restart VSCode.

