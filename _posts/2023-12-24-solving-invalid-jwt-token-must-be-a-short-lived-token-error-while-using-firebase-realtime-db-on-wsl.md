---
published: true
layout: post
category: wsl
title: >-
  Solving "Invalid JWT: Token must be a short-lived token" error while using
  firebase realtime db on WSL
---
I keep hitting this in my Windows laptop with WSL (Windows Subsystem for Linux).  
This is the full error:

```bash
google.auth.exceptions.RefreshError: ('invalid_grant: Invalid JWT: Token must be a short-lived token (60 minutes) and in a reasonable timeframe. Check your iat and exp values in the JWT claim.', {'error': 'invalid_grant', 'error_description': 'Invalid JWT: Token must be a short-lived token (60 minutes) and in a reasonable timeframe. Check your iat and exp values in the JWT claim.'})
```

Check out the date: `date` => Probably will output something weird.

Sync it again (needs sudo):

```bash
sudo hwclock -s
```

Check out date date again: `date` => This time it should show correct timezone. if not, there are more commands to run I stole from internet.
