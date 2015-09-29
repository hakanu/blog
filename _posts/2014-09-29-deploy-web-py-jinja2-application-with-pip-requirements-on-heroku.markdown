---
layout: post
title: Deploy web.py applications with pip requirements on Heroku
date: '2014-09-29 23:53:30'
---

[![](http://distilleryimage10.ak.instagram.com/2138b070f15b11e1959322000a1e9e0c_7.jpg)](http://instagram.com/uhakan)

Running and deploying python apps on Heroku is pretty easy. I usually use web.py and Jinja2 templates for a typical web server.

* Install [heroku toolbet](https://toolbelt.heroku.com/)

* Login to heroku

`heroku login`

* Set the environment variables

`heroku config:set PORT=8080`

* Heroku clone the app from created path.

`heroku git:clone -a myapp`

* Create **Procfile** to tell heroku how to run the app

`gedit Procfile`

* Put this into the **Procfile**: (Heroku assigns some random port every time it restarts the job so don't hardcode the port here. It is highly like that heroku will fail to bind that port. Let it use its own port.)

`python main.py $PORT`

`gedit requirements.txt`

* Example content of **requirements.txt** (**pip** based installation will be done after pushing the code before deployment by heroku)

        web.py==0.37
        Jinja2==2.6
        Werkzeug==0.8.3
        gunicorn==0.14.2

* Deploy the app by using git:

  `git add .`
  
  `git commit -m "Some commit"`
  
  `git push heroku master`

* Visit [yourapp.herokuapp.com](yourapp.herokuapp.com)
* To see the logs:

`heroku logs`

* One last thing, you can use this [site](https://uptimerobot.com/) to monitor your application's uptime by pinging it periodically. It will prevent your application to become idle on heroku. 