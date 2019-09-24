---
published: false
layout: post
category: ipad
title: ''
---
I have developed this habit to use smaller and less powerful devices to develop stuff for 2 years. The reason for this is that the larger screen becomes the more distracted I become. And also more powerful machines usually handle lots of open chrome tabs which are also distraction for me.

So I have been using my refurbished entry level chromebook for almost all of my hobby projects. Recently I kept seeing this branding for iPad to replace a normal laptop. So I decided to give it a go. Here is a small journey of mine. Up to you to pick up whatever tool you liked on the way. Everybody has different style and priorities while coding so everything here is subjective. This post is written through iPad OS 13 Open Beta 2 In Jul’19.

Local only
----------

Well my chromebook was amazing, I have zeal installed, I can totally go offline and develop something in an 8 hour flight. For iPad I wanted to emulate the same one. So I basically need a capable terminal.

#### iSH Shell

This is pretty cool project I have been following quite some while. There is a single developer who managed to put full alpine linux into iOS through test flight app and system call translation.

https://www.reddit.com/r/ish

https://ish.app

*   Pros
    *   It’s fast and durable terminal
    *   Noteworthy apps can be run on ish: python, git, gcc, ssh, ruby, jekyll, vim
        *   You can create a local python server and from safari app you can just go to localhost:8080 boom.
    *   Dark mode :P
*   Cons
    *   Not everything is working
    *   no tmux yet and not so close
    *   screen is available but you can not attach again after detach.
    *   Absence of tmux prevents splits so vim + running the code is not possible.

Recommended method: 

*   Split screen
*   Get another text editor - I’ve got GoCo Edit Which can mount ish files.
*   Edit the code from app, run it from ish.

### SSH to another machine (the most used approach) 

Whenver you google “coding in ipad” Or ”development with iPad”, you keep ending up long posts with first line saying install an ssh app. Yeah well that’s cheating. This is my joker card. I have termius and also ish has ssh; I can not connect to my main workstation or raspberry pisor some EC2 instance to do the development and I can get full linux terminal with tmux and vim.

Of course this is not local at all; you can go LAN only which is still something.

Recommended method:

*   Use ish to ssh in workstation
*   Edit text from ish‘s vim
*   Split screen And go to LAN IP of workstation (192.168.0.X:8080) to check out the server.
*   Trigger vim from ish to modify files in the workstation

### Coder: Cool Docker and VSCode Method

This is the one I really would like to make as defacto. Again this is not fully offline either, even not offline at all. However, this is the coolest method I have.

Since VSCode is written with electronjs, it‘s based on js/css/html which means it’s deployable to web rather than desktop apps. So there is an actively maintained repo which can be used to run VSCode in the browser Via docker from the workstation.

https://github.com/cdr/code-server

\`docker run -it -p 127.0.0.1:8443:8443 -v "${PWD}:/home/coder/project" codercom/code-server --allow-http --no-auth\`

Pros

*   Full VSCode capabilities, themes and extensions
*   VSCode terminal
*   Being able to mount workstation folders an
*   As powerful as browser
*   Safari can make it full screen by adding it to home screen from share menu to get rid of safari menus and tabs clutter.

Cons

*   Needs network
*   Uses websockets I guess, my connection keeps getting dropped.
*   Git extension of vscode makes things really slow given that it’s working remote mounted folder.
*   Not so resilient to the alt+tab window/app switches. Takes a couple of seconds to react after app switch. The most deal breaker one is this.
*   iOS word recommendation bar clutters the view, I occasionally can not see the the last couple of lines at the end in the line.
*   vim mode is extremely buggy in this mode.

### Eclipse Theia: Less Cool but still cool docker method

yes Eclipse is still in the game and adapting. This is written in Typescript. 

Theia IDE is similar one to VSCode. Actually it’s the VSCode with lots of its weights thrown away. Extensions are needed to be built during the binary creation.

https://github.com/theia-ide/theia

\`docker run -it -p 3000:3000 -v "$(pwd):/home/project:cached" theiaide/theia:next\`

*   pros
    *   Faster than cdr/coder vscode
    *   Same vscode terminal
    *   Same vscode themes
    *   Can be full screened by using add to home screen in Safari.
*   cons
    *   Hard to set up extension.
    *   vim mode extension needs some hacks to set up, didn’t try.
    *   Settings are less human friendly.
    *   iOS next word recommendation bar is cluttering this too.

### Monaco editor

This is VSCode’s backing editor. You can run this in browser and connect from local but this won’t be enough because it’s a pure editor.

### AWS Cloud 9 Editor

*   pros
    *   Backed by AWS, pretty fast
    *   Easy to set up
    *   Terminal
*   Cons
    *   Doesn’t work in chrome or safari or opera.
        *   Can only work in safari by disabling “block third party cookies” Option to let 3rd party cookies. Otherwise editor doesn’t show up at all.
    *   No self hosting option, binded to AWS
    *   Medieval look - good old eclipse theme
    *   Impossible to ssh-in to machine running C9 editor. Apparently it’s different when you set C9 up from prepackaged images. In AWS