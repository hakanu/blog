---
published: false
layout: post
category: python
title: Some Airflow edge cases and potential solutions
---

1. Whenever I visit http://192.168.86.2:8087/home?tags=my_tag I get a never ending "Last Run" column load.

```bash
AttributeError: 'NoneType' object has no attribute 'isoformat' airflow
```

Change views.py at `%YOUR_PIP_INSTALL_PATH%/lib/python3.9/site-packages/airflow/www/views.py` from `start_date': r.start_date.isoformat()` to `'start_date': r.start_date.isoformat() if r.start_date else datetime.now(),` so that we insert a value into last run. Not the best but at least now tasks are being scheduled.

![](https://devdala.files.wordpress.com/2021/09/screenshot-from-2021-09-19-21-44-32.png)

1. Tasks stuck at "queued" state: Make sure you enable the DAG. At least that's how I found out by trial and error. I may be wrong there are tons of different Q&As out there. Nobody talks about these simple and foundational stuff.
