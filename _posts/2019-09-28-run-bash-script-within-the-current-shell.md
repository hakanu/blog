---
published: true
layout: post
category: bash
title: Run bash script within the current shell
---
Normally if you do ./foo.sh your script is run in a subshell so whatever happens in that one is not affected by the caller shell.

I wanted to write a script to affect the caller, eg shortcut cd-ing for example.

`touch foo.sh`
`echo "cd /tmp/foo/bar/baz/$1" > foo.sh`

`./foo.sh "yolo"  # No effect at all`
`. foo.sh "yolo"  # Your current dir changes to /tmp/foo/bar/baz/yolo`

You can also put this into ~/.bashrc as an alias so you can easily call without remembering the full path
```bash
alias void='. /a/b/c/foo.sh'
```

```shell
source ~/.bashrc 
void  # Thank me later.
```