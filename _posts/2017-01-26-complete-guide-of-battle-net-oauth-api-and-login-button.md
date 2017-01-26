---
published: false
layout: post
category: oauth
title: Complete Guide of Battle.net OAuth API and Login Button
---
https://dev.battle.net/docs/read/oauth
https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop?hl=en

# Get authorization code

"Missing grant type" battle.net

You can only use once "authorization_code"

Request access token is a POST request - BE CAREFUL

## With python 
In python, use json unencoded payload for POST request

import requests
data = {
      'code': auth_code,
      'client_id': client_id,
      'client_secret': client_secret,
      'redirect_uri': redirect_uri,
      'grant_type': 'authorization_code'
  }
  response = requests.post(
      _BATTLE_NET_TOKEN_URL,
      #data=json.dumps(data),  # not this!
      #json=data,  # not this!
      data=data,  # this is it!
      auth=HTTPBasicAuth(client_id, client_secret),
      verify=False)

## With postman
- Use basic authentication which is btoa(username + ':' + password)
- This kinda auth is pretty simple.
- username is client_id and password is client_secret

# After you get the token
- Use it with GET requests
curl https://eu.api.battle.net/account/user?access_token=<redacted>

{
  "id": 29953309,
  "battletag": "haku#41232"
}
