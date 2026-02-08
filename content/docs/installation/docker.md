---
title: Docker
cascade:
  type: docs
weight: 3
sidebar:
    open: true
next: /docs/installation/production-setup/
---

You can run Dragonfly using Docker Compose.

Save this file as `docker-compose.yml`:

```yaml
services:
  dragonfly:
    image: ghcr.io/riffcc/dragonfly:latest
    restart: unless-stopped
    ports:
      - "3000:3000"
    volumes:
      - dragonfly-data:/var/lib/dragonfly
    environment:
      - RUST_LOG=info

volumes:
  dragonfly-data:
```

Then run:

```bash
docker compose up -d
```

Visit the web interface at `http://localhost:3000`
(or `http://your-hostname:3000` if you're not running it locally).

### Networking for PXE boot

The default port-forwarded configuration works for the web UI and basic management. If you need PXE boot functionality (DHCP and TFTP), you'll need host networking:

```yaml
services:
  dragonfly:
    image: ghcr.io/riffcc/dragonfly:latest
    restart: unless-stopped
    network_mode: host
    volumes:
      - dragonfly-data:/var/lib/dragonfly
    environment:
      - RUST_LOG=info

volumes:
  dragonfly-data:
```

Host networking is required because DHCP uses broadcast packets and TFTP requires direct socket access, which don't work through Docker's port forwarding.

### Customising the port

To run on a different port, change the port mapping:

```yaml
    ports:
      - "8080:3000"  # Access on port 8080 instead
```

### Data persistence

All Dragonfly data (database, templates, boot images) is stored in the `dragonfly-data` volume. This persists across container restarts and upgrades.

To back up your data:

```bash
docker run --rm -v dragonfly-data:/data -v $(pwd):/backup debian:trixie-slim tar czf /backup/dragonfly-backup.tar.gz /data
```
