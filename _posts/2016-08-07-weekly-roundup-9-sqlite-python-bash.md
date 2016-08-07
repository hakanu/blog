---
published: false
layout: post
category: roundup
title: 'Weekly roundup - 9 #sqlite #python #bash'
---
## A New Post

* SQLite
	* dump a table as csv:
		* `sqlite3 -header -csv mydb.db "select * from my_table;" > monthly.csv`
    * See the schema
    	* `cat .schema | sqlite3 mydb.db`
    * Redirect output to sql file from sqlite cli.
    	* `sqlite3 mydb.db`
        * `> .output my.sql`
        * `> select * from my_table;`
        * OR just dump the whole db
        	* `sqlite3 mydb.db`
	        * `> .output my.sql`
        	* `> .dump`
* Bash - check if a command is installed in the machine:

`command_exists ()
{
  type "$1" &> /dev/null ;
}

# Install csvtojson if not exists.
if command_exists csvtojson ; then
  echo "csvtojson exists"
else
  echo "Installing csvtojson"
  sudo npm install -g csvtojson
fi`

* 