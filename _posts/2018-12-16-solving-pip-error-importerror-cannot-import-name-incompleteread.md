---
published: true
layout: post
category: python
title: 'Fix pip error: ImportError cannot import name IncompleteRead '
---
Here is how to resolve weird python pip error. Happened to me while uninstalling a package.

`sudo pip uninstall wheezy`

Output:

```
Traceback (most recent call last):
File "/usr/bin/pip", line 9, in <module>
load_entry_point('pip==1.5.6', 'console_scripts', 'pip')()
File "/usr/lib/python2.7/dist-packages/pkg_resources.py", line 356, in load_entry_point
return get_distribution(dist).load_entry_point(group, name)
File "/usr/lib/python2.7/dist-packages/pkg_resources.py", line 2476, in load_entry_point
return ep.load()
File "/usr/lib/python2.7/dist-packages/pkg_resources.py", line 2190, in load
['__name__'])
File "/usr/lib/python2.7/dist-packages/pip/__init__.py", line 74, in <module>
from pip.vcs import git, mercurial, subversion, bazaar  # noqa
File "/usr/lib/python2.7/dist-packages/pip/vcs/mercurial.py", line 9, in <module>
from pip.download import path_to_url
File "/usr/lib/python2.7/dist-packages/pip/download.py", line 25, in <module>
from requests.compat import IncompleteRead
ImportError: cannot import name IncompleteRead
```

* This is fixed in the pip version. Just update yours by first removing old version

`sudo apt-get remove python-pip`

* Get the latest version

`sudo easy_install pip`

There you go.
