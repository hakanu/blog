---
published: true
layout: post
category: docker
title: >-
  Solution of error getting credentials - err: exec:
  "docker-credential-desktop.exe": executable file not found in $PATH,  Docker
  on WSL Ubuntu
---
Hit an error today, solution is very stupid, so I had to blog it here.

## Error

```bash
$ docker compose up
[+] Running 0/0
 ⠋ scriberr Pulling                                                                                                                                                                                                                           0.0s
error getting credentials - err: exec: "docker-credential-desktop.exe": executable file not found in $PATH, out: ``
```

In `~/.docker/config.json` change `credsStore to credStore`

```bash
$ cat ~/.docker/config.json
{
  "credStore": "desktop.exe"
}
```


[Source](https://forums.docker.com/t/docker-credential-desktop-exe-executable-file-not-found-in-path-using-wsl2/100225/5)


