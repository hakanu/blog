---
published: true
layout: post
category: python
title: >-
  Solving 'google-api-python-client' distribution was not found error in the
  hackiest way
---

For a project I need to use google-api-python-client package, although I installed it through pip at the runtime I receive this error:

```bash
pkg_resources.DistributionNotFound: The 'google-api-python-client' distribution was not found and is required by the application
```

What I learned so far is that google-api-python-client is a resource rather than a library so it's much of json files apparently. And it actually is when you open up the folder

There has been weird solutions like copying the whole google-api-python-client folder to next to the code calling this. This didn't work for me. I went old school 

eg. code location calling this (ps I have my libraries installed under lib via `pip install requirements.txt -t lib/`): `lib/googleapiclient/model.py`

And in the model.py this is the offending line:

```python
_LIBRARY_VERSION = pkg_resources.get_distribution("google-api-python-client").version
_PY_VERSION = platform.python_version()
```

This is the folder for offending resources: `lib/google_api_python_client-2.22.0.dist-info` (2.22.0 is subject to change, that's my version).

I have modified above model.py to this to make the code work in the most hackiest way:

```python
_LIBRARY_VERSION = '2.22.0'
_PY_VERSION = platform.python_version()
```

Day is saved. So long.
