---
published: true
layout: post
category: linux
title: Playing AAA Games on Steam with Proton on Linux
---
![](https://devdala.files.wordpress.com/2021/05/selection_013.png)

I have recently switched to Ubuntu 21.04 from Windows 10. Obviously I need to play games. I knew that Steam has been doing some work on this. It's time to put it on use. I installed Steam.

With Steam there has been some problems, here are some of those solutions:

* [How to fix Steam's small font size issue on Linux](https://hakanu.net/linux/2021/04/24/how-to-fix-steam-s-small-font-size-issue-on-linux/)
* [Fix scaling issue of Counter Strike in Ubuntu (Steam)](https://hakanu.net/linux/2021/04/25/fix-scaling-issue-of-counter-strike-in-ubuntu-steam/)

After fixing these, I was able to play Counter STrike Global Offensive with 300 FPS @ 144 Hz. So all good in the hood. Then I wanted to play some smaller indie games. I have tried the ones which are already available in Steam (Linux supported).

* Tried Hades didn't work.
* Tried Bastion, worked nice!
* Tried Pyre and Transistor, didn't work.
* Tried Dark Souls 3, didn't work.
* Tried Curse of the Dead Gods, didn't work. Well this was the last one which exhausted my patience. So I started to look for the underlying issue. Because other people were able to play. So I should be able to play too! It's a fresh ubuntu installation, Nvidia drivers are installed.

Anyways, let's get to work.

First of all make sure you have Nvidia Drivers are installed. Mine is installed automatically interestingly. So good job ubuntu + nvidia. It was very controversial in the past.

Run `nvidia-settings` from your terminal to make sure drivers are installed. For AMD folks, I didn't check it but I'm sure there is equivalent.

![](https://devdala.files.wordpress.com/2021/05/selection_018.png)

Run steam from the terminal (at least in my case, I have to due to the scaling reasons): `GDK_SCALE=2 steam`

Go to Steam -> Settings -> Downloads -> Steam Library Folders and select a default folder to install the games into. In the ideal world, Windows games are directly working in Linux too. However, this was my problem apparently. I keep installing the games into my Windows steam folder which is NTFS format on my m2 drive. However, steam linux doesn't like it so above games were not working. I uninstalled the games and reinstalled into ext4 folder by changing default folder to a native ubuntu folder from here:

![](https://devdala.files.wordpress.com/2021/05/selection_016.png)

I was getting this error in the terminal in case someone is searching for this online

```bash
Traceback (most recent call last):
  File "/Steam/steamapps/common/Proton 3.16/proton", line 168, in <module>
    tar.extractall(path=basedir + "/dist")
  File "/usr/lib/python3.9/tarfile.py", line 2036, in extractall
    self.extract(tarinfo, path, set_attrs=not tarinfo.isdir(),
  File "/usr/lib/python3.9/tarfile.py", line 2077, in extract
    self._extract_member(tarinfo, os.path.join(path, tarinfo.name),
  File "/usr/lib/python3.9/tarfile.py", line 2158, in _extract_member
    self.makelink(tarinfo, targetpath)
  File "/usr/lib/python3.9/tarfile.py", line 2253, in makelink
    self._extract_member(self._find_link_target(tarinfo),
  File "/usr/lib/python3.9/tarfile.py", line 2152, in _extract_member
    self.makedir(tarinfo, targetpath)
  File "/usr/lib/python3.9/tarfile.py", line 2181, in makedir
    os.mkdir(targetpath, 0o700)
OSError: [Errno 22] Invalid argument: steamapps/common/Proton 6.3/dist/./share/default_pfx/dosdevices/c
```

PS: maybe we only need to have proton installed in ext4. Games can still live in NTFS. Somebody should give this a go.

Let me quickly check if I can play `Curse of the Dead Gods`. Nope, can not even install:
![](https://devdala.files.wordpress.com/2021/05/selection_013.png)

Install proton (Steam -> Library -> Search -> proton) if it's not installed. I installed the most recent two version (incl Experimental) but doesn't matter much as far as I see. Steam linux comes with 3.16 by default I guess.

![](https://devdala.files.wordpress.com/2021/05/selection_015.png)

Enable Steam Play in advanced mode through Steam -> Settings -> Steam Play -> Tick `Enable Steam Play for all other titles`. This is kinda shim layer as far as I understand, it tries to run the game although it's not supported. So AAA games can be run through proton. This settings change requires restarting Steam.

![](https://devdala.files.wordpress.com/2021/05/selection_014.png)

Voila, the game is installable.

![](https://devdala.files.wordpress.com/2021/05/selection_017.png)

It's locked to 60FPS with really nice looking graphics:

![](https://devdala.files.wordpress.com/2021/05/whatsapp-image-2021-05-01-at-01.32.22.jpeg)

I'm off to try Dark Souls III now. Byes!

Update: It worked like a charm, 60FPS Max settings with RTX 2070, zero hiccup. You have to use the Proton installed in ext4 not in NTFS and force to use the one installed in ext4 Game -> Right Click -> Manage -> Compatibility

![](https://devdala.files.wordpress.com/2021/05/screenshot-from-2021-05-01-03-19-25.png)

![](https://devdala.files.wordpress.com/2021/05/20210501025249_1.jpg)

![](https://devdala.files.wordpress.com/2021/05/20210501025549_1.jpg)

![](https://devdala.files.wordpress.com/2021/05/20210501025725_1.jpg)

![](https://devdala.files.wordpress.com/2021/05/20210501030853_1.jpg)

Check if the game you want to play is working fine: https://www.protondb.com/
