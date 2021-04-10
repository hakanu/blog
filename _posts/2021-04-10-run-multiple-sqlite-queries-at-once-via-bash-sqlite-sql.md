---
published: true
layout: post
category: python
title: 'Run multiple sqlite queries at once via #bash #sqlite #sql'
---
Multiple sqlite queries come together to form up scripts. Although UI apps like [sqlite browser](https://sqlitebrowser.org/) (which is my favorite btw) does great job to run scripts together easily, from bash it's a little tricky. Because you need some automation around your queries to clean up the database before certain ops. 

```bash
# For some bash niceness demonstration within sql queries. 
# Don't get sql injected though (create safe strings).
d=$(date '+%Y-%m-%d')

# Let's form up a script with 3 instructions.
query=".mode column
	UPDATE some_table SET title = 'new title' WHERE day > '${d}';
    SELECT * FROM some_other_table WHERE day > '${d}';

# For debugging purposes.
echo "Running this query: ${query}"

# Sqlite reads from stdin so we should give what it needs.
# Make sure you wrap $query with quotation marks otherwise your 
# query won't be piped to sqlite properly due to line breaks.
echo "$query" | sqlite3 some.db

echo "Running the query is finished"
}
```