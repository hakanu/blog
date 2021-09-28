---
published: true
layout: post
category: linux
title: >-
  Solving DBeaver starting problem requiring later version of JVM on Arch Linux
  #manjaro
---
Even though you install DBeaver from Manjaro's own Add/Remove Programs app, you may still not be able to start it properly due to JVM version clash. Luckily, solution is easy, just be better. Lol. Not, just install the latest version of opendjk.

```bash
sudo pacman -S jdk-openjdk  # For me it installed jdk-openjdk-16.0.2.u7-1

# Still it won't work unless we set default java to this v16.
sudo archlinux-java set java-16-openjdk
```

Now you can use Dbeaver without any problem.