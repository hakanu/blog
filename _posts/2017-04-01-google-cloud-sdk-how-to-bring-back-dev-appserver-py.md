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

* The reason is that it's installed through apt-get, instead we should uninstall that version through apt and then reinstall in the old way.

`sudo apt-get update`
`sudo apt autoremove google-cloud-sdk`

* Install in an old way, this will ask you if you want to delete the old folders. Say yes to that.
`curl -sSL https://sdk.cloud.google.com | bash -`

* Now we have the proper gcloud, we can give it a try to install the python SDK:
`gcloud components install app-engine-python`

* Boom, worked; try this in your GAE app:
`dev_appserver.py main.app.yaml`



