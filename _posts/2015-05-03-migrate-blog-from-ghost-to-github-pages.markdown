---
layout: post
title: Migrated my blog from Ghost to Github pages
date: '2015-04-27 16:31:13'
---

Thanks to [heroku beta pricing](https://news.ycombinator.com/item?id=9295874).

* `mkdir blog`
* `cd blog`
* `git init`

* `sudo gem install jekyll`
* `sudo gem install github-pages`
* `sudo gem install bundler`

### For development, live refresh etc

* `sudo gem install pygments.rb`
* `sudo gem install listen`

### Create the project

* `jekyll new .`
* `jekyll build --watch`  # Auto reload.
* Go to http://localhost:4000

### Import posts from self hosted Ghost blog

* Go to http://yourblog.com/ghost/debug
* Export json file with all of your posts.
* `sudo gem install jekyll_ghost_importer`
* `jekyll_ghost_importer GhostBackup.json`  # This will create _posts folder and _draft folder.

### Play with the settings

* `vim _config.yml`
* `permalink: pretty`
* `paginate: 10`
* `paginate_path: "/page/page:num/"`

### Add pagination

I have ~400 posts so need to paginate in order to show in the main page.
Used this recepi:

http://jekyllrb.com/docs/pagination/

PS: To create a new post you can use github's UI and preview mode which is cool but not as cool as Ghost of course.