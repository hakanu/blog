---
published: false
layout: post
category: python
title: "phpadminlite - a Web UI for SQLite"
---

# Install dependencies
sudo apt-get install apache2
sudo apt-get install php5
sudo apt-get install php5-sqlite

# Change port 80 to smt else
sudo nano /etc/apache2/ports.conf
# Restart server.
sudo /etc/init.d/apache2 restart

# Copy files from downloaded folder to 
cp phpadminlite.php to /var/www/html/.

# Visit page.
Go to http://192.168.0.19:7070/phpliteadmin.php

# Password is in config file, definitely modify it.