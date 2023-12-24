---
published: true
layout: post
category: firebase
title: >-
  Solving "Error: TRIGGER_PAYLOAD_TOO_LARGE: This request would cause a function
  payload exceeding the maximum size allowed" in firebase realtime db
---
I was using this piece and it stopped working in one night:

```python

db.reference('foo/some_key').delete()
```

I wrote the code above in different variations, nothing helped.
Writing it here so that I won't forget. Eventually the solution was very easy, I had an inactive firebase function listening to firebase realtime database writes and I just deleted that function. This thing got resolved.

The inspo is from this old post:

https://stackoverflow.com/questions/50513374/firebase-realtime-database-currently-gives-trigger-payload-too-large-error

Hope saves someones less hours than me.
