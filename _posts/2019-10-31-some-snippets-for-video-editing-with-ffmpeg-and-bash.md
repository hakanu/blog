---
layout: post
title: Some code snippets for video editing with FFMPEG and bash
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
Mostly notes to self for future.

I have an unwatched twitch stream where I record moments with my fellow gamers. The other day I was checking out [the clips](https://www.twitch.tv/dailyow/manager/clips) that I have taken when we were playing Call of Duty Black Ops 4. I decided to make them a video and upload it to my personal YouTube channel which doesn't have any video that reached 2-digit view count. Of course I should write some script for this. Otherwise I need to learn Adobe Premiere or Da Vinci Resolve or iMovie or whatever. Who has time to learn something new?

Anyways, so first of all, I needed to download the clips to my local. I can either do that with my inspect element skills and figure out mp4 link from twitch or I can rise on the shoulders of the giants: [youtube-dl](https://ytdl-org.github.io/youtube-dl/index.html)

Luckily ytdl can download videos from wide range of sites. And also twitch gives me the title that I put while clipping so yet another manual process is eliminated.

```bash
virtual -p python3 env
source env/bin/activate
pip install youtube_dl

youtube-dl https://clips.twitch.tv/SaltyTameSpaghettiKevinTurtle
```

Now I have a bunch of mp4 files with title and ID in their names including spaces which are not liked by bash: `"{title} -  {id}.mp4"`
Let's get rid of those IDs:

```bash
  for f in *.mp4 
  do
    echo "Renaming: $f"
    mv -v "$f" "${f//-[0-9].mp4/.mp4}"
  done
```

I also want to add some caption to the clips otherwise it'd be too ez. There are multiple ways to achieve this. My naive approach is drawing text on the video for 0th to 2nd second. So it was going to show up and then disappear. Nope. In order to use such a technique, you need your ffmpeg to be compiled with `libfreetype`. I'm never good at compiling stuff from the source. So used some alternative method which is embedding subtitles to the video with ffmpeg. Sounds easy, I need to pass the subtitle file to be embedded which has srt extension. Let's create them in bash:

```bash
  for f in *.mp4 
  do
    echo "Creating srt file for : $f"
    echo -e "1\n00:00:00,000 --> 00:00:03,000\n${f//.mp4/}" >> "${f}.srt"
    ffmpeg -i "${f}.srt" "${f}.ass"
  done
```

I have also converted srt to .ass file because ffmpeg natively supports ass as far as I understand but it's more complicated than this. I just love srt and it's so human readable meanwhile .ass is not.

Let's embed them with ffmpeg, I tried all these methods none worked:

```bash
  for f in *.mp4 
  do
    echo "Adding srt file into mp4: $f"
    ffmpeg -i "$f" -i "${f}.srt" \
      -c:v copy \
      -c:a copy \
      -c:s mov_text  \
      -flags global_header \
      "${f}_subtitled".mp4

    ffmpeg -i "$f" -i "$f".srt \
      -c:v libx264 -preset ultrafast \
      -ar 44100 -ac 2 -ab 128k -strict -2 \
      -c:s mov_text -map 0 -map 1 \
      "${f}_subtitled.mp4"

    ffmpeg -i "$f" -i "$f".srt \
      -c:v copy \
      -c:a copy \
      -c:s mov_text -map 0 -map 1 \
      "${f}_subtitled.mp4"

    ffmpeg -i "$f" \
      -vf ass="${f}.ass" "${f}_subtitled_ass".mp4
  done
```

None of the above worked so I falled back to my beloved python where I have my [moviepy](https://zulko.github.io/moviepy/) which is a video manipulation library backed by ffmpeg and imagemagick aka two beasts.

```bash
pip install moviepy
```

Found this mostly online, modified it a little bit:

```python
from moviepy import editor
import sys


def annotate(clip, txt, txt_color='white', fontsize=50, font='Xolonium-Bold'):
    """ Writes a text at the bottom of the clip. """
    txtclip = editor.TextClip(txt, fontsize=fontsize, font=font, color=txt_color)
    cvc = editor.CompositeVideoClip([clip, txtclip.set_pos(('center', 'bottom'))])
    return cvc.set_duration(clip.duration)

movie_name = sys.argv[1]
video = editor.VideoFileClip(movie_name)
print('video dur: ', video.duration)
subs = [
    ((0, 2), sys.argv[2]),
    ((2, video.duration), ' '),
]

annotated_clips = [
	annotate(video.subclip(from_t, to_t), txt) for (from_t, to_t), txt in subs]

final_clip = editor.concatenate_videoclips(annotated_clips)
final_clip.write_videofile(movie_name + '_subtitled_moviepy.mp4')
```

Ran it like this:

```bash
python add_subtitle.py "$f" "${f//.mp4/}" 
```

Didn't work of course. What works in the first run? It complained about imagemagick not being installed:

```bash
sudo apt install imagemagick
convert --v  # Make sure it's installed
```

Alright, re-ran, now it moved forward but this time it has a weird error.

`convert-im6.q16: not authorized `myfile.pdf' @ error/constitute.c/WriteImage/1037.`

Found my reply [here](https://askubuntu.com/questions/1081895/trouble-with-batch-conversion-of-png-to-pdf-using-convert/1081907). Apparently it's imagemagick has a policy protection for server side use. So let's go to the edge and circumvent this:

```bash
sudo vim /etc/ImageMagick-6/policy.xml
```

Replace the line:

`<policy domain="path" rights="none" pattern="@" />`

`<policy domain="path" rights="read|write" pattern="@" />`

OK now it worked. In essence what this moviepy script does is it divides first 2 seconds and gets each frame in these 2 seconds, draws text on top of it. And for the rest of the video (Duration - 2) seconds, it puts a space as subtitle (empty string was not working); and at the end it appends these two together so it results with a one video with 2 second subtitle which is what I have wanted.

And finally the combination section. Of course nothing is easy. Since we have more than 2 videos (2 video merging is easy in FFMPEG but multiple is a little bit different), we need to form a file with all of the video paths. I don't mind doing this, but my for loop doesn't iterate alphabetically which bothers me a lot so I need to read some long bash explanations in SO. At the end I ended up with this style which is a while-kinda loop iterates over the mp4 files in alphabetical order and then prints each mp4's path into list.txt file which is later used by ffmpeg to be merged for these multiple videos.

```bash
  find . -type f -name "*_subtitled_moviepy.mp4" -print0 | while IFS= read -r -d '' f
  do
    echo "creating list txt mp4: $f"
    echo -e "file '${f}'" >> list.txt
  done
  ffmpeg -f concat -safe 0 -i list.txt -c copy output_combined_subtitled.mp4
```

PS: I've had to pass -safe 0 because ffmpeg was complaining about the file names being unsafe. I guess it's because file names with spaces are unsafe for ffmpeg?

Here is the final result (there are some freezes in the beginning though :/):

<iframe width="560" height="315" src="https://www.youtube.com/embed/PhxfTObusGM?start=7" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
