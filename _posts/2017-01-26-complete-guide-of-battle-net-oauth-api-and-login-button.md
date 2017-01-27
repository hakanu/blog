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
* Note your client key and secret and redirect_uri which must be an HTTPS url.

# Get authorization code

Oauth is usually 2-steps. First you authorize the user and then use this authorization to obtain an access token in order to make requests to battle.net on behalf of user without using user's battle.net account username and password. 

Here is the first step, put a link in your html directing to a url like this:

`https://eu.battle.net/oauth/authorize?access_type=online&client_id=<redacted>&redirect_uri=https%3A%2F%2Flocalhost&response_type=code&state=`

As you can see we request a so-called _code_, you should of course put your client key obtained from the dev.battle.net applications panel.

# Get access token with authorization code

This is the second part. Usually this part doesn't need many params but interestingly battle.net documentation is poor and its backend is so picky, it took me days to try each combination. I'm doing a brain dump here with possible error you'd see.

* This request must be POST request. Don't try GET
* This request must use "Basic authentication" which is applying btoa to username and password by concatting them with ':' => js equivalent: btoa(username + ':' + password)
  * The resulting string must be put in the headers.
* This request must be made from a server, cross domain requests are not allowed from ajax xhr (eg via jquery). So  I put a small python example. i'm not sure how to do a cors request without writing another server. LMK if you know a method to just do XHR to battle.net servers without using an intermediate server.
* "Missing grant type" battle.net: Don't use json payload in your POST request. You will see in details below.
* You can only use once "authorization_code"

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

- Use it with GET requests (this is community api)
curl https://eu.api.battle.net/account/user?access_token=<redacted>

{
  "id": 29953309,
  "battletag": "haku#41232"
}

Here is my site: <https://owmatch.me> (Not ready of course but you can test the login)

PS: There is no official overwatch api yet. We should scrape it on our own. I will publish a repo on this soon.