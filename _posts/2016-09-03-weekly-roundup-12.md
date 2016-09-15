---
published: false
layout: post
category: roundup
title: Weekly roundup - 12
---

* Strip out image EXIF information:
`convert input.jpg -strip output.jpg`

* 3x3 square image grid example with uneven sized images. I finally found the simplest solution with only CSS:
http://jsfiddle.net/webtiki/MpXYr/2/
* Interesting read: [encoding/csv: Reading is slow - slower than python and java](https://github.com/golang/go/issues/16791)
* If you store column as DATETIME in SQLite, you don't need to convert the returning object's that column into datetime. It's automatically done by the sqlite framework.
* TSDB: Time series database.
	
    * [OpenTSDB](http://opentsdb.net)
    * [InfluxDB](https://www.influxdata.com)
    * [Grafana UI](http://grafana.org/)
    * [VoltDB](https://www.voltdb.com/)
    * [Snowflake](https://www.snowflake.net/)
