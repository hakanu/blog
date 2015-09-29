---

layout: post
category: sql
author: Hakan Uysal
title: Solving Sqlite's python Unicode string problem with non UTF8 data
date: '2015-08-25 23:31:13'

---


Error it throws:

	sqlite3.ProgrammingError: You must not use 8-bit bytestrings unless you use a text_factory that can interpret 8-bit bytestrings (like text_factory = str). It is highly recommended that you instead just switch your application to Unicode strings.

Solution was easy; add this line for assigning text_factory. It converts strings into unicode objects.

`conn = GetSqliteConnection(db_path)
conn.text_factory = lambda x: unicode(x, 'utf-8', 'ignore')`

Thanks to [SO](http://stackoverflow.com/questions/2392732/sqlite-python-unicode-and-non-utf-data) again. (PS that post is extremely useful for python encoding/decoding.)