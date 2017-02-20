---
published: false
layout: post
category: bash
title: 'Some nice #bash commands'
---
## Make all files lower case in the folder in linux

```
for f in `find`; do mv -v "$f" "`echo $f | tr '[A-Z]' '[a-z]'`"; done
```

### Rename all files in the directory sequentially

```
a=1
for i in *.mp4; do
  new=$(printf "%04d.mp4" "$a") #04 pad to length of 4
  mv -- "$i" "$new"
  let a=a+1
done
```

## Check if variable null (not set) or not

```
  if [ -z "$var" ]
  then
    echo "\$var is empty"
  fi
```


## Function definition

```
main ()
{
	echo "This is a function"
}
```