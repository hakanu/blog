---
layout: post
title: Ghost v0.5 update problem - No support for database client postgres
date: '2014-08-28 23:28:37'
---

Error line from logs:
**ERROR: No support for database client postgres**

If you are using postgres (usually for heroku users), just change your config.js file from:

`production: {
        url: 'http://hakanu.net',
        mail: {},
        database: {
            client: 'postgres',           `
            
to

`production: {
        url: 'http://hakanu.net',
        mail: {},
        database: {
            client: 'pg',`
            

Redeploy your ghost.