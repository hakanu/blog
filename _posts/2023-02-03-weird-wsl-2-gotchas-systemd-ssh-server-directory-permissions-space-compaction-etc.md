---
published: true
layout: post
category: wsl
title: >-
  Weird WSL 2 gotchas - systemd, ssh server, directory permissions, space
  compaction etc
---
As much as I love WSL it comes with weird quirks you need to work around. eg. you can not git clone a repo in another directory than C: (I guess) unless you do what I tell you below lol. If there are easier ways, happy to hear.

## Move WSL between drives to open up space

```bat
wsl --list -v
wsl --list -v
wsl -t Ubuntu
wsl --export Ubuntu "D:\wsl_export\ubuntu-ex.tar"
wsl --unregister Ubuntu
wsl --import Ubuntu "D:\WSL\import" "D:\WSL\ubuntu-ex.tar"
```

## Shut down WSL instance

This is useful when you update /etc/wsl.conf

```bat
wsl --shutdown
```

## Find WSL folder:

`\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Lxss`

## Space up

WSL is weird because the more you use space within WSL, eg. apt install things and then remove things. It doesn't return the space back to the host Windows 11 filesystem back. Instead you gotta do the compaction yourself.

Save this to compact-disk.txt

```bat
select vdisk file="C:\Users\$whoami\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu_79rhkp1fndgsc\LocalState\ext4.vhdx"
attach vdisk readonly
compact vdisk
detach vdisk
```
Run this
diskpart /s <SAVED_SCRIPT_FOLDER_PATH>\compact-disk.txt


## Increase the ram allocated for WSL

WSL by default is bound to 8 or half of the host's RAM as far as I understand. I go yolo here because I'm trying to run stable diffusion models.

Add .wslconfig under C:\User\$whoami

```bat
[wsl2]
memory=120GB # Limits VM memory in WSL 2 to 128 GB
```


## Enable SSH Server

This is different from Windows 11's default SSH support. This is a workaround again.
Windows itself has a nice ssh access support but when you access to windows from ssh you can not simply `bash` into WSL. Because it's not working yet if you installed WSL through Microsoft Store which is the officially recommended way to get the proper updates. Well, hmm. So your best bet is either uninstalling WSL and installing through non MS Store or ssh-ing into the WSL itself directly. I chose the second one here however, in order for this to work you gotta keep the WSL on when you boot windows. Annoying while on holidays.

```bash
sudo apt install openssh-server
sudo /usr/sbin/service ssh start
ifconfig
hostname
whoami
ssh hakanu@172.18.211.124
```

## Enable systemd

```bash
sudo vim /etc/wsl.conf
```

Add these lines
```
[boot]
systemd=true
```

## Resolve git issues: Operation not permitted

When you git clone, it gives this stupid error, smt like this:

```
.git/config.lock failed: Operation not permitted
fatal: could not set 'core.filemode' to 'false'
```

```bash
sudo vim /etc/wsl.conf
```

```
[automount]
options = "metadata"
```

From cmd.exe, reboot WSL: `wsl --shutdown`

Voila.