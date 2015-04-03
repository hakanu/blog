---
layout: post
title: How to install programs in Linux
date: '2009-10-01 20:03:17'
---

Although it is not useful information for professional Linux users, this can help fresh Linux users.

There are several ways to install a program. Some of them are really messy. However, some of them are easier than Windows. Of course it depens on the program you want to install

First way is using Synaptic Package Manager. You can reach it by following this path: System -&gt; Administration -&gt; Synaptic Package Manager. Write the name of program you want to install into the search bar. Choose from the list install it. The Synaptic Package Manager will download the program's files from operating system's storage and the program will be installed automatically.

Other way is using terminal. To open terminal, you can use this path: Applications -&gt; Accessories -&gt; Terminal. After opening it, write the setup code and press enter button. Setup code is like this:
<pre>sudo apt-get install xxx</pre>
<em>sudo: </em>gives you root(administrator) rights

<em>apt-get:</em> debian package manager

<em>install: </em>setup code

<em>xxx: </em>the name of the program you want to install

For example, to install Opera Web Browser:
<pre>sudo apt-get install opera</pre>
Tiny note: While Synaptic Package Manager is working, you can not install another program by using terminal. At the same time, there must be one installer. It's eligible in Windows too. There is always one Windows installer at the same time.

The other way is using tar.gz packages. However, there is not a definite way to do the installation. Because every program has different technique for setup. It's generally written in the tar.gz package. You can read and follow the instructions and make installation.