---
published: true
layout: post
category: python
title: 'Useful BeautifulSoup Tips #bs #python #scraper'
---
![](https://www.crummy.com/software/BeautifulSoup/10.1.jpg)

> Poor man's scraper...

Yes it works like a charm even on the unvalidated html. That's my biggest problem with python libraries like lxml etc, they don't really work well with the unvalidated html/xml trees. However BeautifulSoup does everything it can.

Here are some handy commands I use every day:

* Install: `sudo easy_install beautifulsoup4`

```python
from bs4 import BeautifulSoup

soup = BeautifulSoup(html_doc, 'html.parser')

# Prettify your html. Works amazingly well.
print soup.prettify()

# Find one element in the html by tag name.
soup.find('a')

# Find all elements in the html by tag name.
soup.find_all('a')

# Find one element in the html by having a class name (multiple classes will be found as well):
soup.find('a', {'class': 'some-css-class'})

# Find one element in the html by having a class name (multiple classes will be found as well):
for s in soup.find_all('a', {'class': 'some-css-class'}):
	print s
    
# Get element's text within the tags:
soup.find('a', {'class': 'some-css-class'}).get_text()

# Get element's specific attribute value:
soup.find('a', {'class': 'some-css-class'}).get('href')

# Find image's src attribute for example:
soup.find('img', {'class': 'img-responsive'}).get('src')

# Find element if it has that attribute:
soup.find('img', style=True)  # Brings up an img element with style attribute.

# Check if element has some attribute:
soup.find('img').has_attr('style')  # eg. returns True

# Use CSS selectors:
soup.select("p.strikeout.body")
soup.select("li nth-of-type(3)")
```

* [Homepage](https://www.crummy.com/software/BeautifulSoup/)
* [Documentation](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)
* [PyPi](https://pypi.python.org/pypi/beautifulsoup4)
