---
layout: post
title: Use third party python packages in Google App Engine
date: '2014-08-06 23:48:51'
---

![](https://devdala.files.wordpress.com/2014/08/img_20140510_211106_11.jpg)

*My hacky solution of usage of 3rd party packages in python. If you have a better method, leave a comment!*

Let's start with flask example [package by google](https://github.com/GoogleCloudPlatform/appengine-python-flask-skeleton).

* `git clone https://github.com/GoogleCloudPlatform/appengine-python-flask-skeleton.git`
* `cd appengine-python-flask-skeleton`
* `pip install -r requirements.txt -t lib`
* `dev_appserver.py .`
* Visit [localhost:8080](http://localhost:8080/)

There is this **lib** folder with all of the dependencies in it like flask, jinja2, markupsafe etc. And in the code they are used like this:
from flask import Flask

So, to import your stuff:

* Download the package from pypi. For this example, I'm going to go through [markdown package](https://pypi.python.org/pypi/Markdown#downloads).
* Extract it somewhere, copy the folder and paste into lib/ folder.
* Preserve the name of the package like **Markdown-2.4.1** in my case.
* Go inside the folder and cut the *markdown* folder and paste under lib/ folder.
* In the code, you can use it like:
import markdown
markdown.markdown(content)

Also [check this](http://flask.pocoo.org/snippets/19/) if you are interested in **how to use markdown in flask**.

Default third party packages available on Google App Engine are listed [here](https://developers.google.com/appengine/docs/python/tools/libraries27).