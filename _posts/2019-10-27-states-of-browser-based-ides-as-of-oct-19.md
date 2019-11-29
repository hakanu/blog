---
published: false
layout: post
category: Ide
title: State of Browser Based IDEs as of Nov'19
---
I have been trying to adopt almost all of the browser based IDEs in the wild by importing one of my toy projects and implementing a trivial feature on them. In this post, I tried to summarize my extremely subjective experience. 

Disclaimer: I use vim, sublime text, vscode, atom, notepad++, nano most of the time (all have different purposes).

Got some help from this list: <https://github.com/styfle/awesome-online-ide>

# IDEs

## Coder - VSCode Server 
----------------------

[https://github.com/cdr/code-server](https://github.com/cdr/code-server)

### Pros

*   Easy to run for the first time
*   Full extension support
*   Terminal
*   Good configuration for user folders, extension folders etc
*   Host computer’s file system can be mounted and used easily

### Cons
* High CPU usage on host machine

![](api/images/qxfjXUM6JNN7/code_server_cpu_usage.png)

## AWS Cloud 9 IDE
---------------

### Pros

*   Terminal
*   Eclipse-esque UI
*   Easy to run via AWS marketplace
*   Doesn’t really work on mobile chrome. Need to disable ”Prevent cross site tracking“ from safari settings to be able to use this from ipad.
*   Authorization through amazon account

### Cons

* Really hard to connect to the host machine to mess with files. 
* Everything is forced to be done from the browser UI’s supplied terminal.

[https://aws.amazon.com/cloud9/](https://aws.amazon.com/cloud9/)

## Theia @theia_ide
-----------------

### Pros

*   Pure vscode with less configuration and settings
*   No extensions builtin, needs rebuild
*   Easy to run for the first time
*   Terminal
*   Used  in gitpod.io

[https://repl.it/](https://repl.it/)

[https://glitch.com/](https://glitch.com/)

[https://about.gitlab.com/2018/06/15/introducing-gitlab-s-integrated-development-environment/](https://about.gitlab.com/2018/06/15/introducing-gitlab-s-integrated-development-environment/)

## Eclipse che
----------
### Pros

* An eclipse project. 

## VSCode hosted
--------
https://visualstudio.microsoft.com/services/visual-studio-online/

### Pros

* Official so you get all the builds and security patches immediately.

### Cons

* Binded Azure. Can not run in your machine in another provider yet. Maybe in the future?

# Summary

My favorite is coder server which is the vscode in your browser with full terminal access to the host machine without the need of additional SSH tooling. You can also transfer the same VSCode shortcut usage knowledge. In addition full support of the vscode plugins is the winner. You can add vim mode and in your browser you have the full vim keyboard navigation with vscode nicesities.
