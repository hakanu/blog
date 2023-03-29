---
published: true
layout: post
category: python
title: Fresh Debian install and username not in sudoers file
---
Note for my future self to solve this quickly. Because there are really long tutorials on this.

I have got a fresh debian 11 installation yet, I can not do sudo apt install anything because of this error. You can not modify things like usermod because it needs sudo privileges.

Here is the quick solution:

```bash
su root 
vim /etc/sudoers

# Into the file add your username:
your_username ALL=(ALL)  ALL

# Save and exit, boom
```
