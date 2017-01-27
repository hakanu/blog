---
published: false
layout: post
category: oauth
title: Complete Guide of Battle.net OAuth API and Login Button
---
I play Overwatch like crazy and I use sites like [overbuff](http://overbuff.com) and [masteroverwatch](http://masteroverwatch.com).

I like their battle.net login buttons and wanted to create a simple site to beat matchmaking system. I didn't realize that this will be a huge struggle.

Here are the official docs:
<https://dev.battle.net/docs/read/oauth>

Get this Chrome Extension to try get post requests, amazing extension including authentication features:
<https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop?hl=en>

# Sign up first

* Go to the <https://dev.battle.net> and create a mashery account.
* Create your first app
  * You can put localhost as **callback url**, you **MUST** put it as `https://localhost`
  * https is really important let's keep this in mind.

# Get authorization code

Oauth is usually 2-steps. First you authorize the user and then use this authorization to obtain an access token in order to make requests to battle.net on behalf of user without using user's battle.net account username and password. 

Here is the first step, put a link in your html directing to a url like this:


# Get access token with authorization code

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
