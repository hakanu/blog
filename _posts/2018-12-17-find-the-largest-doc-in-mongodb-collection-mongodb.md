---
published: true
layout: post
category: mongodb
title: 'Find the largest doc in Mongodb collection #mongodb'
---
Nothing fancy just iterating over the bson objects and evaluating if we see a larger one.

Here is the js snippet:

```javascript
var max = 0;
var id = null;
db.users.find().forEach(function(obj) {
    var curr = Object.bsonsize(obj); 
    if(max < curr) {
        max = curr;
        id = obj;
    } 
})
print(max);
print(id._id);
```