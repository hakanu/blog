---
published: true
layout: post
category: mongodb
title: "Solving mongodb's user creation problem"
---




I have been test driving mongodb with some serious projects. I have always had difficulty in creating users in any database. Mongodb was no surprise.
Here is the working command for me.

- Error 
2016-02-16T01:28:27.570+0000 Error: couldn't add user: User "test1@admin" already exists at src/mongo/shell/db.js:1004

![](https://devdala.files.wordpress.com/2016/03/media-20160216.png)

- First add the user: 
`mongo localhost:12346`

`> use admin`

`> db.createUser({
       user: "test1",
       pwd: "test",
       roles:[
          { role: "readWrite", db: "isimibul-dev" }]})`

- Now connect by using the user: 

`mongo localhost:12346/mydb-dev -u test1 -p test`

One side note: If you are having difficulties with connecting to the DB, you can change auth mechanism to MONGODB-CR, this is the old system used back in the days of v2.4; now SHA is used for auth, if you are using an updated version like v3, just use SHA as auth mechanism.
