---
published: true
layout: post
category: python
title: "Python regular expression '-' specialness"
---



### note to self

Use \- instead of - in python regular expressions

$ python
import re
re.search(r'([\-\w]*)', 'www.hakanu-net')
