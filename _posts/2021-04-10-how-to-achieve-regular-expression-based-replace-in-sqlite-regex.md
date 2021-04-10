---
published: true
layout: post
category: sqlite
title: 'How to achieve regular expression based replace in #sqlite #regex'
---
It may be surprising but there is not much information about how to bulk update sqlite database columns based on regexp replace. Many examples recommmend compiling sqlite from the source with `icu_replace.c` (becoming icu_replace.so). However, I couldn't make it work.

Hopelessly roaming around github I've found this awesome library: https://github.com/nalgeon/sqlean
It has many good modules but the most useful one for me was `re` module: https://github.com/nalgeon/sqlean/blob/main/docs/re.md

Here is an example bulk update by using regexp replace in sqlite commandline:

* Download latest release for your platform for your interested module: https://github.com/nalgeon/sqlean/releases
* Let's assume you are on linux, it's highly likely that you will need sqlite3-re.so file so put it somewhere you can reference later, let's say `/home/hakanu-net/sqlite3-re.so`

```sql

$ sqlite3 some.db

>> SELECT load_extension('/home/hakanu-net/sqlite3-re.so'); 

-- Example from sqlean docs:
>> SELECT REGEXP_REPLACE('this year is 2021', '[0-9]+', '2050');
the year is 2050

-- My main usage to clean up entries:
>> UPDATE entries SET title = REGEXP_REPLACE(title, 'foo', 'new_foo'); 
```

sqlean modules make sqlite very powerful. I'm going to check out json1 module next.
