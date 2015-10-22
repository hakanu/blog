---

layout: post
category: GAE
author: Hakan Uysal
title: Solving Google App Engine users API problem - raise NotAllowedError

date: '2015-10-21 23:03:00'

---


Error thrown:

	    <class 'google.appengine.api.users.NotAllowedError'>: 
		Traceback (most recent call last):
		  File "/base/python_runtime/python_lib/versions/1/google/appengine/ext/appstats/ui.py", line 324, in <module>
		    main()
		  File "/base/python_runtime/python_lib/versions/1/google/appengine/ext/appstats/ui.py", line 320, in main
		    util.run_bare_wsgi_app(app)
		  File "/base/python_runtime/python_lib/versions/1/google/appengine/ext/webapp/util.py", line 116, in run_bare_wsgi_app
		    result = application(env, _start_response)
		  File "/base/python_runtime/python_lib/versions/1/google/appengine/ext/appstats/ui.py", line 308, in __call__
		    users.create_login_url(os.getenv('PATH_INFO', '')))])
		  File "/base/python_runtime/python_lib/versions/1/google/appengine/api/users.py", line 256, in create_login_url
		    raise NotAllowedError

Code:

`from google.appengine.api import users`
`self.redirect(users.create_login_url(self.request.uri))`

Steps to solve:

- Go to https://appengine.google.com
- Go to your project's settings
- Change basic settings like this:

![](https://devdala.files.wordpress.com/2015/10/screen-shot-2015-10-21-at-11-04-07-pm-compressor.png)

- Redeploy the app. Should be fine.