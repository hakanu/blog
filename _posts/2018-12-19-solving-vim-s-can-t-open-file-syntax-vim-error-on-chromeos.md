---
published: true
layout: post
category: vim
title: Solving Vim's "Can't open file syntax.vim" error on ChromeOS
---
Happened on my chromebook while installing newer version of vim (aka vim8).

All highlights are gone and all of the files were showing up as plain text.

`vim --v`
7.2

`crew install vim`
Add to ~/.bashrc

`alias vim=/usr/local/bin/vim`
`vim --v`
8.1

old vim ==> /usr/bin/vim
new vim ==> /usr/local/bin/vim

Add to ~/.bashrc:

`export VIMRUNTIME=/usr/local/share/vim/vim81/`

