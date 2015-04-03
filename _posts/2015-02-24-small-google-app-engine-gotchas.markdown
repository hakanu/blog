---
layout: post
title: Small Google App Engine gotchas
date: '2015-02-24 19:32:40'
---

[![](https://igcdn-photos-f-a.akamaihd.net/hphotos-ak-xfa1/t51.2885-15/10803010_762038930516301_599088481_n.jpg)](https://instagram.com/uhakan/)

Working with GAE is sometimes tough in the beginning.

* GQL queries must not have " in it. Instead ' single quotation must be used.
* GQL does not have LIKE
* You can not put the fields which are not indexed into the WHERE statement.
Adding the field into index.yaml is not enough, you need to explicitly say it in the Model definition:
class Event(ndb.Model):
  title = ndb.TextProperty()
  date = ndb.DateTimeProperty(auto_now_add=True)
  event_date = ndb.TextProperty(indexed=True)
* Plus it still may not work, the index needs to be built. In local just rewrite the data. Otherwise it's not gonna work.
* While mapping the urls don't put get parameters in the url structure. Only put the parameters by / - get params might be unlimited and their order can change. It's fine to map them in variations.
* To save bandwidth use infinite expiration date for css by defining in app.yaml
* create an endpoint for pinging the app to prevent idle sleeps of machine in order to save up bandwidth.  down notifier is good service for this. free.
http://www.downnotifier.com/ is a free service for pinging your site and it also sends mail if your site is down and calculates the downtime and uptime, pretty cool.

### web.py on Google App Engine

* Be careful about the requirement.txt, order is important. Don't import bson package before pymongo for example. Because pymongo uses bson. Otherwise there are import errors.

`pip install -r requirements.txt -t lib/`

* In the first non-native library import, before it, do this:

`sys.path.insert(0, 'lib')`

* Put `__init__.py` into templates folder so it can be seen as a module.

* In the app.yaml add this to the handlers in order to serve static files.
handlers:

`- url: /static
  static_dir: static`