---
published: false
---

## Solving mongodb's user creation problem

2016-02-16T01:28:27.570+0000 Error: couldn't add user: User "test1@admin" already exists at src/mongo/shell/db.js:1004

mongo localhost:12346
> use admin
> db.createUser(
...     {
...       user: "test1",
...       pwd: "test",
...       roles: [
...          { role: "readWrite", db: "isimibul-dev" }
...       ]
...     }
... )
mongo localhost:12346/paylasio-dev -u test1 -p test

