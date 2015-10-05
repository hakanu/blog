---

layout: post
category: python
author: Hakan Uysal
title: Solving mongodb auth problem - pymongo.errors.OperationFailure auth failed

date: '2015-10-05 22:40:00'

---


Error thrown:

	pymongo.errors.OperationFailure: command SON([('authenticate', 1), ('user', u'root'), ('nonce', u''), ('key', u'')]) failed: auth failed


Steps to solve:

- If using global pymongo, update it.

	`sudo pip install pymongo --upgrade`

- If using pymongo from lib folder

	`sudo pip install -r requirements.txt -t lib/ --upgrade`

- Redeploy. This will hopefully fix your heroku and Google App Engine deployment with pymongo.
	