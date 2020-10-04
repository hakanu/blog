---
published: true
layout: post
category: python
title: Using IP restricted Mongodb Atlas from Heroku or Google App Engine (GAE)
---
## Using Mongodb Atlas (or any other IP restricted mongodb) from Heroku or Google App Engine (GAE)

I was getting this error while deploying my mongodb atlas hosted db backed python flask app on google app engine and heroku: `pymongo.errors.ServerSelectionTimeoutError: connection closed,connection closed,connection closed heroku` and my app was not waking up, failing with 500 error. Logs were showing that mongodb connection is timing out meanwhile in my local dev it was all working normal.

This problem applies to any mongodb instance which is IP restricted, not only mongodb atlas. If you are using managed stack like GAE or heroku this is inevitable because there are IP restrictions for your mongodb instance probably due to increased security. I will show you a cheap hacky solution.

The problem lies under the IP whitelisting of mongodb atlas.

* One solution: add `0.0.0.0/0` to iptable of mongodb atlas so that it's open to whole world which is quite unsafe.
* Instead you can get all heroku ips with this command and add to mongodb atlas from admin screen.
```
echo "Looking up Heroku"
HEROKU_REGION=eu
sudo apt -qqy install curl jq 2>/dev/null 1>/dev/null
heroku regions --json 2>/dev/null | jq ".[] | select(.name==\"$HEROKU_REGION\") | .provider.region" | (REGION=$(cat) 
curl -s https://ip-ranges.amazonaws.com/ip-ranges.json |  jq ".prefixes[] | select(.region==$REGION) | .ip_prefix") > heroku_ips.txt
```

*	Get GAE IPs from here:
	* First get the list of netblock from this command, beware this is not static and up to change:
	```
	nslookup -q=TXT _cloud-netblocks.googleusercontent.com 8.8.8.8
	```
	* Now nslookup each one to find out underlying IPs:
	```
	echo "Looking up GAE"
	nslookup -q=TXT _cloud-netblocks1.googleusercontent.com 8.8.8.8 >> $GAE_FILE
	nslookup -q=TXT _cloud-netblocks2.googleusercontent.com 8.8.8.8 >> $GAE_FILE
	nslookup -q=TXT _cloud-netblocks3.googleusercontent.com 8.8.8.8 >> $GAE_FILE
	nslookup -q=TXT _cloud-netblocks4.googleusercontent.com 8.8.8.8 >> $GAE_FILE
	nslookup -q=TXT _cloud-netblocks5.googleusercontent.com 8.8.8.8 >> $GAE_FILE
	```

* Add them to your mongodb atlas whitelist. I can hear you are saying that there are many IPs, should I do it one by one? Hell no, I got you. Here is a javascript console code which you can paste and it will start adding ips to your whitelist one by one. Not the most efficient but does the job. Takes a couple of minutes to finish all.
	* PS: Not to mislead anyone, I didn't put the exact ips below, you should fill them up from above commands.
	
```javascript
/* Run ip_list_lookup.sh to get the freshest list of IPs. */
var herokuIps =  [_ADD_IP_LIST_FROM_ABOVE_COMMANDS];
var gaeIps = [_ADD_IP_LIST_FROM_ABOVE_COMMANDS];

function addIps(ips) {
	var i = 2;
	var myInt = setInterval(function() {
		// Trigger IP add popup.
		document.getElementsByClassName("fa-plus")[0].click();
		setTimeout(() => {
			console.log('waiting for popup')
		}, 2000);

		console.log('Setting input text to', ips[i])
		document.getElementsByName("networkPermissionEntry")[0].value = ips[i];
		document.getElementsByName("confirm")[0].click();

		if (i == ips.length) {
			clearTimeout(myInt);
		}
		i++;
	}, 5000);
}

addIps(herokuIps);
addIps(gaeIps);
```
