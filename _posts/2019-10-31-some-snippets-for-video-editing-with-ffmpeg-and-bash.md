---
layout: post
title: Some snippets for video editing with FFMPEG and bash
type: bash
categories:
  - bash
tags:
  - bash
  - video
  - ffmpeg
image: /assests/img/77111070-8ffd-4f4c-84a6-fe44a6edcfc5.jpeg
description: video editing like a boss
date: 2019-10-31T20:05:42.051Z
---
I have an unwatched twitch stream where I record moments among my gaming friends. The other day I was checking out the clips that I have taken when we were playing Call of Duty Black Ops 4. I decided to make them a video and upload it to my personal YouTube channel which doesn't have any video that reached 2-digit view count. Anyways, so first of all, I needed to download the clips to my local. I can either do that with my inspect element skills and figure out mp4 link from twitch or I can rise on the shoulders of the giants: [youtube-dl](https://ytdl-org.github.io/youtube-dl/index.html)

```
rename() {
  for f in *.mp4 
  do
    echo "Renaming: $f"
    mv -v "$f" "${f//-[0-9].mp4/.mp4}"
  done

  for f in *.mp 
  do
    echo "Renaming: $f"
    mv -v "$f" "${f//-.mp/.mp4}"
  done

}

create_subtitle_files() {
  for f in *.mp4 
  do
    echo "Creating srt file for : $f"
    echo -e "1\n00:00:00,000 --> 00:00:03,000\n${f//.mp4/}" >> "${f}.srt"
    ffmpeg -i "${f}.srt" "${f}.ass"
  done
}

add_subtitle_to_video() {
  echo "Adding subtitles"
  for f in *.mp4 
  do
    echo "Adding srt file into mp4: $f"
#    ffmpeg -i "$f" -i "${f}.srt" \
#      -c:v copy \
#      -c:a copy \
#      -c:s mov_text  \
#      -flags global_header \
#      "${f}_subtitled".mp4

#    ffmpeg -i "$f" -i "$f".srt \
#      -c:v libx264 -preset ultrafast \
#      -ar 44100 -ac 2 -ab 128k -strict -2 \
#      -c:s mov_text -map 0 -map 1 \
#      "${f}_subtitled.mp4"

#    ffmpeg -i "$f" -i "$f".srt \
#      -c:v copy \
#      -c:a copy \
#      -c:s mov_text -map 0 -map 1 \
#      "${f}_subtitled.mp4"

#    ffmpeg -i "$f" \
#      -vf ass="${f}.ass" "${f}_subtitled_ass".mp4
    sudo python add_subtitle.py "$f" "${f//.mp4/}" 
  done
}

combine_videos() {
  echo "Combine videos"

  #for f in `ls *_subtitled_moviepy.mp4 | sort -V` 
  find . -type f -name "*_subtitled_moviepy.mp4" -print0 | while IFS= read -r -d '' f; do
  #do
    echo "creating list txt mp4: $f"
    echo -e "file '${f}'" >> list.txt
  done
  ffmpeg -f concat -safe 0 -i list.txt -c copy output_combined_subtitled.mp4
}

main ()
{
  if [ "$1" = "create_subtitle" ]; then
    create_subtitle_files
  elif [ "$1" = "add_subtitle" ]; then
		add_subtitle_to_video
  elif [ "$1" = "combine_videos" ]; then
		combine_videos
  else
    help
  fi
}

main "$1" "$2" "$3"
```
