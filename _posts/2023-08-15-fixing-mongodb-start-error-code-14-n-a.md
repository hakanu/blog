---
published: true
layout: post
category: mongodb
title: Fixing mongodb start error code 14/n/a
---
Stupid errors today.

My local mongodb which has been running for multiple weeks decided not to start.

First I need to remove MONGODB_CONFIG_OVERRIDE_NOFORK env variable.

```bash
sudo vim /usr/lib/systemd/system/mongod.service
# Convert this line:
# Environment="MONGODB_CONFIG_OVERRIDE_NOFORK=1"
# To This line:
# Environment="MONGODB_CONFIG_OVERRIDE_NOFORK=0"
```

Then it still refuse to up itself, but this time no errors:

```bash
sudo systemctl start mongod

x:~$ sudo systemctl status mongod

× mongod.service - MongoDB Database Server
     Loaded: loaded (/lib/systemd/system/mongod.service; enabled; vendor preset: enabled)
     Active: failed (Result: exit-code) since Mon 2023-08-14 20:33:54 CEST; 1s ago
       Docs: https://docs.mongodb.org/manual
    Process: 1501 ExecStart=/usr/bin/mongod --config /etc/mongod.conf (code=exited, status=14)
   Main PID: 1501 (code=exited, status=14)

Aug 14 20:33:54 x systemd[1]: Started MongoDB Database Server.
Aug 14 20:33:54 x systemd[1]: mongod.service: Main process exited, code=exited, status=14/n/a
Aug 14 20:33:54 x systemd[1]: mongod.service: Failed with result 'exit-code'.
```

Apparently it's a [permission issue](https://askubuntu.com/questions/823288/mongodb-loads-but-breaks-returning-status-14):

```bash
sudo chown -R mongodb:mongodb /var/lib/mongodb
sudo chown mongodb:mongodb /tmp/mongodb-27017.sock
sudo service mongod restart
```
