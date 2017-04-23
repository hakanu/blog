---
published: false
layout: post
category: windows
title: Windows 10'da Ubuntu Bash modunu etkinleştirmek
---

![](http://devdala.files.wordpress.com/2017/04/cron_mail.png?w=704)

I have 3 raspberry pis and they have some crons on it. Although this is nice, I have hard time to keep track of which pi does what and if its cron has successfully completed. Thankfully there is an easy solution for that: Send an email after every cron run with logs. However, ubuntu or jessie (pi version of linux) is not capable of sending emails out of box. At least as far as I understand that is the situation so we need a mail provider to send emails. I already have an account from mailgun so why not using it? Did some research and combined some short commands to achieve this.
i assume here that you have opened a mailgun.org account and you use crontab as cron job tool on some debian backed environment.

- Install crontab if you do not have:

`sudo apt-get install crontab`

- Check the cron jobs:

`crontab -l`

- Add/Remove/Edit the cron jobs:

`crontab -e`

- Install postfix for mail sending relay

`sudo apt-get -y install postfix`

- Choose from the prompts
- Satellite system
- username: desired_username
- smtp.mailgun.org

- Install mailutils to send email easily from terminal for trials.

`sudo apt-get -y install mailutils`

- Modify this file 

`sudo nano /etc/postfix/sasl_passwd`

- Append this with mailgun credentials found in the mailgun.org account dashboard (I assume you have already created an account there, free account is more than enough.):

`smtp.mailgun.org postmaster@<mailgun_host>:<mailgun_credentials>`

- Run these to make sure that we restarted

`sudo chmod 600 /etc/postfix/sasl_passwd`

`sudo postmap /etc/postfix/sasl_passwd`
`sudo nano /etc/postfix/main.cf`

- Append this to the opened file:

smtp_sasl_auth_enable = yes
smtp_sasl_password_maps = hash:/etc/postfix/sasl_passwd
smtp_sasl_security_options = noanonymous
smtp_sasl_tls_security_options = noanonymous
smtp_sasl_mechanism_filter = AUTH LOGIN

- Restart postfix:

`sudo systemctl restart postfix`

- Test it:

`mail -s "Test mail" some_test@gmail.com <<< "A test message using Mailgun"`


- Check your inbox if it is all good, then we are ready to make crontab send emails.
- Run this:

`crontab -e`

- Append this at the top of the file before cron jobs:

`MAILTO=some_test_account@gmail.com`

- Congrats now wait for your dummy cron to send an email.
