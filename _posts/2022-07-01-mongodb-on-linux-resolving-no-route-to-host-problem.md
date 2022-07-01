---
published: true
layout: post
category: mongodb
title: 'Mongodb on linux: Resolving No route to host problem'
---
Prenote: I don't recommend opening your db to the world without any IP restrictions

```
W NETWORK  [thread1] Failed to connect to in(checking socket for error after poll), reason: No route to host
E QUERY    [thread1] Error: couldn't connect to server connection attempt failed :
connect@src/mongo/shell/mongo.js:275:13
@(connect):1:6
exception: connect failed
```

If you really really want to open: Just start accepting traffic from mongodb default port 27017 through `iptables` if you are on ubuntu/debian

```bash
sudo iptables -I INPUT 6 -m state --state NEW -p tcp --dport 27017 -j ACCEPT
```
