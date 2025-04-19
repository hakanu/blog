---
published: true
layout: post
category: hdd
title: >-
  How to understand the discrepancies in the hard drive lifetime (smart farm
  logs)
---

Preface: The discrepancy doesn't mean that your hdd is bad. It's an input for decision making. I use this to spot "new new" drives vs "refurbished but sold as new" drives especially on amazon.

![chatgpt generated image beware](https://devdala.wordpress.com/wp-content/uploads/2025/04/e9ceb854-e786-4f5a-beff-2bd713d58bcf.png)

I was extending my NAS disks and I had already got 2x 12TB Seagates from amazon.de. Since they have been behaving nicely for the last 6 months, I wanted to get 2 more. Then I saw a random review which mentions the farm logs showing different values than smart monitoring tools (s.m.a.r.t.) aka `smartctl`. I have never heard FARM logs before, apparently it stands for Field Accessible Reliability Metrics and useful additional metric for Seagate drives which is harder to reset than smart `Power_On_Hours` metric.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Guess i got scammed by this German Seagate hdd scammers who reset the s.m.a.r.t. information of the hdds and sell it as unused.<br><br>best way to check apparently is the discrepancy of &quot;power on hours&quot;:<br><br>smart power on hours : 4083 (166 days)<br>seagate farm logs PoH: 28831 (1200 days) <a href="https://t.co/ofY36fNDRy">pic.twitter.com/ofY36fNDRy</a></p>&mdash; Hakan Uysal (@hakanu_) <a href="https://twitter.com/hakanu_/status/1911763836732145809?ref_src=twsrc%5Etfw">April 14, 2025</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

I researched on reddit and saw that there is a big market there: https://www.tomshardware.com/pc-components/hdds/german-seagate-customers-say-their-new-hard-drives-were-actually-used-resold-hdds-reportedly-used-for-tens-of-thousands-of-hours

However, noone is explaining the exact command to run. Here they are

```bash
sudo apt update
sudo apt install smartmontools 

# Usual smart logs for power on hours.
sudo smartctl -a  /dev/sdb | grep "Power_On"

# Only applicable for Seagate drives
# FARM Logs
sudo smartctl -l farm /dev/sdb | grep "Power on"
```

If you drive is "new new", you should get almost zero hours for both of these commands. However, in my case `smartctl -a` was giving almost zero but `smartctl -l farm` 28k hours which is totaling to ~1166 days. Obviously this doesn't mean that the drive is bad or anything. Drive is manifactured probably around that time. However some refurbishing event happened and got it fixed and resold to me with clean S.M.A.R.T. 