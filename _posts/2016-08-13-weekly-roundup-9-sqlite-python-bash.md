---
published: false
layout: post
category: roundup
title: 'Weekly roundup - 9 #sqlite #python #bash'
---

* SQLite
	* dump a table as csv:
		* `sqlite3 -header -csv mydb.db "select * from my_table;" > monthly.csv`
    * See the schema
    	* `cat .schema | sqlite3 mydb.db`
    * Redirect output to txt file from sqlite cli.
    	* `$ sqlite3 mydb.db`
        * `.output my.txt`
        * `select * from my_table;`
        * OR just dump the whole db
        	* `$ sqlite3 mydb.db`
	        * `.output my.txt`
        	* `.dump`
* Bash - check if a command is installed in the machine:

```bash
command_exists ()
{
  type "$1" &> /dev/null ;
}

# Install csvtojson if not exists.
if command_exists csvtojson ; then
  echo "csvtojson exists"
else
  echo "Installing csvtojson"
  sudo npm install -g csvtojson
fi
```

* Python multi threading: Pass parameters to the thread


```python
import threading

def F():
	threading.Thread(target=Foo, args=(my_param,)).start()

def Foo(my_param):
	print 'This is a long running process'
```

* Jekyll multiline code blocks for github pages (kramdown): Use this:

\`\`\`language_name

some_code_here()

\`\`\`

* 
