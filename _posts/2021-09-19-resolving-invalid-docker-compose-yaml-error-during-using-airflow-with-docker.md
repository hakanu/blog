---
published: false
layout: post
category: docker
title: Resolving invalid docker-compose.yaml error during using Airflow with Docker
---
I had a relatively fresh install of docker 

```bash
docker-compose up airflow-init
ERROR: The Compose file './docker-compose.yaml' is invalid because:
Unsupported config option for services.airflow-cli: 'profiles'
Invalid top-level property "x-airflow-common". Valid top-level sections for this Compose file are: version, services, networks, volumes, and extensions starting with "x-".
```