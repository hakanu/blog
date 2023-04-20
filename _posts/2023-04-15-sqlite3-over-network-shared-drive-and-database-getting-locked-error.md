---
published: true
layout: post
category: python
title: Sqlite3 over network shared drive and database getting locked error
---
Sqlite3 apparently doesn't like my new NAS setup. Reads are fine but writes were not working and regardless of the timeout I give it was failing with database is locked error.

Error I get: 

```
python3.9/site-packages/peewee.py", line 3221, in execute_sql                                        cursor.execute(sql, params or () 
sqlite3.OperationalError: database is locked     
```

I had to play with pragmas a bit. At the end what worked is 

```sql
sqlite3 mydatabase.db

# Write ahead logging: 
# https://www.sqlite.org/pragma.html#pragma_journal_mode
PRAGMA journal_mode=WAL;

# Made this to normal from full.
# https://www.sqlite.org/pragma.html#pragma_synchronous
PRAGMA synchronous=normal;
```

You can obviously use DB Browser sqlite UI:

![](https://devdala.files.wordpress.com/2023/04/screenshot-2023-04-15-010508.png)

If this doesn't work either, unmount the network drive and mount it like this with `nobrl` option which prevents byte range locking but this comes with disadvantage of likelihood of database corruptions

```bash
sudo mount -t cifs //192.168.1.100/MY_SHARE_NAME /mnt/MY_MOUNT_FOLDER -o username=my_user,password=my_pass,uid=$(id -u),gid=$(id -g),nobrl
```