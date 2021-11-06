---
published: true
layout: post
category: python
title: Find group telegram chat ID for your telegram bot (easy way)
---
A lot of tutorials say, you should open this url up and send a message to bot and it will show up:
https://api.telegram.org/bot%TELEGRAM_TOKEN%/getUpdates

However, it's not that easy, if you re-use a bot which is already listening getUpdates (eg. from your machine, you created a bot and it's listening), this command will give you this empty json response:

```json
{
  "ok": true,
  "result": [
  ]
}
```

Not so useful is it?. Instead, two methods:

1. you can stop getUpdates listening on your machine temporarily and go to above url and grab the chat id. BTW, chat IDs in telegram can be negative.
1. Alternatively you can open up web.telegram.org. In the past, it was showing the chat id in the url but that's no more with more advanced javascript. Instead we will sneak in the html. Open up the js console with inspect element and then select the group chat element you want to send message. Find data-peer-id, voila that's your chat id. Dunno why noone talks about this easy way.

![](https://devdala.files.wordpress.com/2021/11/screenshot_2021-11-06_21-27-41.png)

If you want to send messages with python you can do this:

```bash
pip3 install python-telegram-bot
```

Python code:

```python
import telegram
my_token = '%TELEGRAM_TOKEN%'


def send_tg_message(msg, chat_id, token=my_token):
  bot = telegram.Bot(token=token)
  bot.sendMessage(chat_id=chat_id, text=msg)

send_tg_message('hakanu.net', SOME_INTEGER_I_FOUND_WITH_THIS_AWESOME_BLOG_POST)
```