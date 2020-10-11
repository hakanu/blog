---
published: true
layout: post
category: production
title: SMTP Timeout Problems from VPS
---

# SMTP Timeout Problems from VPS

If you are trying to send emails from your VPS through a third party SMTP server, it's highly likely that you will see some timeout errors on default VPS. Here are some tips to overcomem the problem.

In my case I use `mg.` subdomain to use mailgun. It works perfectly on my local machine but it doesn't work in my VPS.

First let's run some diagnostics to pinpoint the problem.
This is my error: `Connect failed :IO::Socket::INET: connect: timeout is showing up in Perl`
Check if you are able to reach to SMTP server from your VPS machine:

```bash
telnet smtp.eu.mailgun.org 25
telnet smtp.eu.mailgun.org 465
telnet smtp.eu.mailgun.org 587
```

- If these are also timing out, check out your VPS machine if VPS provider shut down some ports to prevent the spam:

```bash
nmap YOUR_VPS_IP -p 25
nmap YOUR_VPS_IP -p 465
nmap YOUR_VPS_IP -p 587
```

If you see that the ports are open, advance to the next stage. If they are closed, talk to support of your provider to open them up for you.

- Set up a reverse DNS (aka rDNS) 
	- Add an `A` record to `mg` of your domain and point it out to `YOUR_VPS_IP` **without** proxy in cloudflare.
	- In your admin panel of VPS (ec2 or any other provider), set up the hostname to be mg.yourdomain.com.
- Disable using ipv6 ([source](https://serverfault.com/questions/512744/timeout-error-in-all-my-apps-for-every-call-to-smtp-servers))
	- Check if it's already disabled: `cat /proc/sys/net/ipv6/conf/all/disable_ipv6`
		- 0 means not disabled, 1 means disabled.
	- `vim /etc/sysctl.conf`
	- Add this to the end of the file:

```
# disable ipv6
net.ipv6.conf.all.disable_ipv6 = 1
net.ipv6.conf.default.disable_ipv6 = 1
net.ipv6.conf.lo.disable_ipv6 = 1
```
Reload sysctl configuration `sysctl --system` and retry `cat /proc/sys/net/ipv6/conf/all/disable_ipv6` to confirm you see `1`.

And now retry smtp pinging: `telnet smtp.eu.mailgun.org 25`
If all of these don't work, I don't know what works :) Talk to your provider by creating a support ticket. Maybe they just block you.