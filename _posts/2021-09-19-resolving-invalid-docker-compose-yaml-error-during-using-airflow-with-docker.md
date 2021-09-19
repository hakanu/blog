---
published: true
layout: post
category: docker
title: Resolving invalid docker-compose.yaml error during using Airflow with Docker
---
I had a relatively fresh install of docker and compose, when I tried to use [Apache Airflow](https://airflow.apache.org/), at the `docker-compose up airflow-init` phase I get this error:

```bash
docker-compose up airflow-init
ERROR: The Compose file './docker-compose.yaml' is invalid because:
Unsupported config option for services.airflow-cli: 'profiles'
Invalid top-level property "x-airflow-common". Valid top-level sections for this Compose file are: version, services, networks, volumes, and extensions starting with "x-".
```

What you should do is not changing airflow's docker-compose.yaml instead checking out your docker-compose version:

```bash
docker-compose --version
```

If it's less than 1.29 which is minimum requirement by airflow, you should update your docker-compose.yaml:

```bash

# Check out where is your docker-compose
whereis docker-compose  # Probably it's at /usr/bin/docker-compose

# Make a copy just in case.
cp /usr/bin/docker-compose /usr/bin/docker-compose_old

# Get the new build (in my case it's 1.29)
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose
```

Now retry airflow init again and it will work:

```bash
docker-compose up airflow-init
```