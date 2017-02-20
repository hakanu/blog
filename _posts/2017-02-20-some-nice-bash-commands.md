---
published: true
layout: post
category: python
title: 'Some nice #bash commands'
---
## Make all files lower case in the folder in linux

```
for f in `find`; do mv -v "$f" "`echo $f | tr '[A-Z]' '[a-z]'`"; done
```

### 
