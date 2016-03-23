---
published: true
layout: post
category: bash
title: "Rename files sequentially in a folder #bash"
---


The output will be something like 0001.jpg, 0002.jpg etc. You can change the number of digits by modifying `%04d` part.

```
a=1
for i in *.jpg; do
  new=$(printf "%04d.jpg" "$a") #04 pad to length of 4
  mv -- "$i" "$new"
  let a=a+1
done
```

Thanks [SO](http://stackoverflow.com/questions/3211595/renaming-files-in-a-folder-to-sequential-numbers)