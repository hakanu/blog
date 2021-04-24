---
published: true
layout: post
category: linux
title: How to fix Steam's small font size issue on Linux
---
If this is happening in your Ubuntu, it's pretty annoying.
I have one 1080p and one 4k monitor. Maybe second monitor is messing with it.

![](https://devdala.files.wordpress.com/2021/04/selection_003_compressed.png)

You need to run it from the terminal with this env variable:

```bash
GDK_SCALE=2 steam
```

![](https://devdala.files.wordpress.com/2021/04/selection_004_compresed.png)