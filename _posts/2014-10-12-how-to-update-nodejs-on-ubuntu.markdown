---
layout: post
title: How to update nodejs on Ubuntu (Debian)
date: '2014-10-12 15:28:45'
---

[![](http://distilleryimage5.ak.instagram.com/8a8a21b06d6811e2bcd822000a9f129c_7.jpg)](http://instagram.com/uhakan)

Thanks [StackOverflow](http://stackoverflow.com)!

#### First method: Through NPM
* `sudo npm cache clean -f`
* `sudo npm install -g n`
* `sudo n stable`
* `node -v`

#### Second method: Through NVM
* `curl https://raw.github.com/creationix/nvm/master/install.sh | sh`
* `source ~/.profile`
* `nvm install 0.10.26`
* `nvm use v0.10.26`
* `which node`
* `node -v`
* install node globally (ie, into /usr/local)

`n=$(which node);n=${n%/bin/node}; chmod -R 755 $n/bin/*; sudo cp -r $n/{bin,lib,share} /usr/local`