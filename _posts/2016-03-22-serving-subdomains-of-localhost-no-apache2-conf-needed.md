---
published: false
layout: post
category: python
title: "Serving subdomains of localhost, no apache2 conf needed"
---

For my latest project, I implemented subdomain handling 

* Modify content of hosts file

$ `sudo nano /etc/hosts`

* Example configuration

```127.0.0.1	localhost
127.0.0.1       hakan.localhost```

* Install web.py just for the sake of trial.

$ `sudo easy_install web.py`

* Create a file

$ `touch main.py`

* Paste this content:

```import web
        
urls = (
    '/(.*)', 'hello'
)
app = web.application(urls, globals())

class hello:        
    def GET(self, name):
        if not name: 
            name = 'World'
        return 'Hello, ' + name + '!'

if __name__ == "__main__":
    app.run()```

* Run the file.

$ `python main.py`

Open browser and go: 
<hakan.localhost:8080/>