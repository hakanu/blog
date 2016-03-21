---
published: true
layout: post
category: nodejs
title: "Solving nodejs error: Cannot find module 'are-we-there-yet'"
---

This happened to me while playing with Web Starter Toolkit (WST)

#### Problem

`web_start_kit_hello  npm install --global gulp && npm install`

`module.js:340
    throw err;
          ^
    Error: Cannot find module 'are-we-there-yet'
    at Function.Module._resolveFilename (module.js:338:15)
    at Function.Module._load (module.js:280:25)
    at Module.require (module.js:364:17)
    at require (module.js:380:17)
    at Object.<anonymous> (/usr/local/lib/node_modules/npm/node_modules/npmlog/log.js:2:16)
    at Module._compile (module.js:456:26)
    at Object.Module._extensions..js (module.js:474:10)
    at Module.load (module.js:356:32)
    at Function.Module._load (module.js:312:12)
    at Module.require (module.js:364:17)`

#### Solution:
Go to the global node_modules directory (`npm root -g` if you don't know)

$ `cd /usr/local/lib/node_modules`

`curl -L https://www.npmjs.com/install.sh | sh`