---
layout: post
title: Export logs from Google App Engine
date: '2015-04-27 20:26:13'
---

Use this command to fetch the application logs from Google App Engine:

`appcfg.py request_logs   --num_days=210 --include_all Documents/DEV/workspace-py/psi_meetings_web_gae/  mylogs.txt --oauth2`

* Alternatively you can write a handler by using logs API.

https://cloud.google.com/logging/docs/install/logs_export

* And second alternative you can analyze logs by piping them into BigQuery.

https://console.developers.google.com/project/_/logs