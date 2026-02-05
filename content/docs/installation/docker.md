---
title: Docker
cascade:
  type: docs
weight: 3
sidebar:
    open: true
next: /docs/installation/production-setup/
---

You can run Dragonfly using Docker Compose:

Save this file as `docker-compose.yml`:
```
services:
  dragonfly:
    image: riffcc/dragonfly:v0.1.0-alpha1
    volumes:
      - config:/var/lib/dragonfly
    ports:
      - "3000:3000" # Main web interface
      - "67:67" # DHCP stapling service
      - "69:69" # TFTP service
```

Edit it to your needs, then run
```
docker-compose up -d
```

Visit the web interface at http://localhost:3000
(or `http://your-hostname:3000` if you're not running it locally)
