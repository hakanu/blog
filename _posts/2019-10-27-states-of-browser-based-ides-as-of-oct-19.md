---
published: false
layout: post
category: Ide
title: States of Browser Based IDEs as of Oct'19
---
I have been trying to adopt almost all of the browser based IDEs in the wild by importing one of my toy projects and implementing an FR on them. In this post, I tried to summarize my extremely subjective experience. Disclaimer: I use vim, sublime text, vscode, atom, notepad++ most of the time (all have different purposes).

Got some help from this list: <https://github.com/styfle/awesome-online-ide>

Coder - VSCode Server 
----------------------

*   Easy to run for the first time
*   Full extension support
*   Terminal
*   Good configuration for user folders, extension folders etc
*   Host computer’s file system can be mounted and used easily

[https://github.com/cdr/code-server](https://github.com/cdr/code-server)

![](api/images/qxfjXUM6JNN7/code_server_cpu_usage.png)

AWS Cloud 9 IDE
---------------

*   Terminal
*   Eclipse-esque UI
*   Easy to run via AWS marketplace
*   Doesn’t really work on mobile chrome. Need to disable ”Prevent cross site tracking“ from safari settings to be able to use this from ipad.
*   Authorization through amazon account
*   Really hard to connect to the host machine to mess with files. Everything is forced to be Done from the browser UI’s supplied terminal.

[https://aws.amazon.com/cloud9/](https://aws.amazon.com/cloud9/)

Theia @theia_ide
-----------------

*   Pure vscode with less configuration and settings
*   No extensions builtin, needs rebuild
*   Easy to run for the first time
*   Terminal
*   Used  in gitpod.io

[https://repl.it/](https://repl.it/)

[https://glitch.com/](https://glitch.com/)

[https://about.gitlab.com/2018/06/15/introducing-gitlab-s-integrated-development-environment/](https://about.gitlab.com/2018/06/15/introducing-gitlab-s-integrated-development-environment/)



<br>