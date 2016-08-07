---
published: false
layout: post
category: python
title: Useful BeautifulSoup Tips
---
Yes it works like a charm even on the unvalidated html. That's my biggest problem python libraries like lxml etc, they don't really work well with the unvalidated html/xml trees. However BeautifulSoup does everything it can.

Here are some handy commands I use every day:

* Install and import 
`sudo easy_install beautifulsoup4`

`
from bs4 import BeautifulSoup

soup = BeautifulSoup(html_doc, 'html.parser')

# Find one element in the html by tag name.
soup.find('a')

# Find all elements in the html by tag name.
soup.find_all('a')

# Find one element in the html by having a class name (multiple classes will be found as well).
soup.find('a', {'class': 'some-css-class'})

# Find one element in the html by having a class name (multiple classes will be found as well).
for s in soup.find_all('a', {'class': 'some-css-class'}):
	print s
    
# Get element's text within the tags.
soup.find('a', {'class': 'some-css-class'}).get_text()

# Get element's specific attribute value.
soup.find('a', {'class': 'some-css-class'}).get('href')

# Find image's src attribute for example.
soup.find('img', {'class': 'img-responsive'}).get('src')

# 
`