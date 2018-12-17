---
published: true
layout: post
category: mongodb
title: Safe and Secure MongoDB Installation and Setup for 2018
---
# MongoDB install and setup guide for 2018

# Install
https://docs.mongodb.com/tutorials/install-mongodb-on-ubuntu/

# Configure
https://www.digitalocean.com/community/tutorials/how-to-install-and-secure-mongodb-on-ubuntu-16-04

# Configure for remote access
https://docs.mongodb.com/manual/reference/configuration-options/ 

# Close ports

```js
sudo apt-get install  mongodb-org mongodb-org-server mongodb-org-shell mongodb-org-mongos mongodb-org-tools

sudo ufw allow ssh
sudo ufw allow http
sudo ufw allow proto tcp from any to any port 80,443

sudo ufw deny from any to any port 27017
sudo ufw allow from 37.228.249.62/32 to any port 27017
sudo ufw status
```

# Error while using pymongo 3.6 with mongodb 3.6

https://docs.atlas.mongodb.com/driver-connection/#python-driver-example
pymongo.errors.ServerSelectionTimeoutError: No replica set members found yet

# Error while connecting remotely

```
mongo  --host 85.217.170.40 -u myuser -p mypass --authenticationDatabase 'test'
MongoDB shell version v3.6.3
connecting to: mongodb://85.217.170.40:27017/
2018-03-26T21:37:16.205+0100 E QUERY    [thread1] Error: network error while attempting to run command 'isMaster' on host '85.217.170.40:27017'  :
connect@src/mongo/shell/mongo.js:251:13
@(connect):1:6
exception: connect failed
```

https://docs.mongodb.com/tutorials/install-mongodb-on-ubuntu/

# Create new user

```
use admin
db.createUser(
  {
    user: "AdminSammy",
    pwd: "AdminSammy'sSecurePassword",
    roles: [ { role: "userAdminAnyDatabase", db: "admin" } ]
  }
)
```

# Disable SSL

```
net:
  port: 27017
  bindIp: 127.0.0.1,85.217.170.40
  ssl:
    #  allowConnectionsWithoutCertificates: true
    mode: disabled
```

```
sudo systemctl restart mongod
```

```
mongo --host 6.6.6.6 -u testuser -p testpass --authenticationDatabase 'test'
```
