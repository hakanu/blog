---
published: false
layout: post
category: python
title: Google Cloud SDK - how to bring back dev_appserver.py
---
This weekend's annoying problem is this. New gcloud SDK is great, it is installed through Ubuntu Software Center (apt-get) etc. However, when you install it like that, even though you can deploy the Google App Engine apps; you would not be able to run the [local server](https://github.com/gae-init/gae-init/issues/394) to see your changes locally for the python GAE app. Example:

* Run the development server:
`dev_appserver.py main.app.yaml`
Output: dev_appserver.py command not found

* List the components:
`gcloud components list`
│ Uninstalled │ gcloud app Python Extensions │ app-engine-python │   6.1 MiB │

* Install the python SDK to use dev_appserver.py
`gcloud components install app-engine-python`
Output: You cannot perform this action because this Cloud SDK installation is 
managed by an external package manager. 
