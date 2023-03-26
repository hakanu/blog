---
published: true
layout: post
category: linux
title: SSH password connection rejected after OpenMediaVault install
---
This is so stupid but took my 1 hour to figure out.

I installed Open Media Vault to create some raids and home NAS on a debian machine. However, after the installation it started to reject my ssh connection to the machine.

Things to look for:

```bash
sudo vim /etc/ssh/sshd_config

# Add this line: AllowUsers your_username
# Change this line: PermitRootLogin yes

# Restart the service.
sudo service ssh restart

# Mine is not fixed so I had to put my username into ssh group
sudo usermod -aG ssh your_username
```