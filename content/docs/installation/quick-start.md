---
title: Quick Start
cascade:
  type: docs
weight: 1
sidebar:
    open: true
---
You can install Dragonfly on any macOS or Linux system.

For Linux installations, we suggest using Debian or Ubuntu or running the Docker image, although you may have luck with other distributions.

### Docker
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

For more details on running Dragonfly with Docker, see the [Docker guide](/docs/docker).

### Binary Installation
Download the latest binary from the [releases page](https://github.com/dragonflycomputer/dragonfly/releases).

You'll want the version for your computer.

{{< tabs items="Linux,macOS,Windows" defaultIndex="0" >}}
  <!-- Linux -->
  {{< tab >}}
  Download Dragonfly from the [releases page](https://github.com/riffcc/dragonfly/releases).
  ```
  wget -O dragonfly https://github.com/dragonflycomputer/dragonfly/releases/download/v0.1.0-alpha1/dragonfly-linux-amd64
  ```
  
  Copy the binary to /usr/local/bin/dragonfly and make it executable:
  ```
  sudo cp dragonfly /usr/local/bin/dragonfly
  sudo chmod +x /usr/local/bin/dragonfly
  ```
  
  Install Dragonfly:
  ```
  sudo dragonfly install
  ```
  
  You can now visit the web interface on port 3000 `http://<machine-ip-address>:3000`

  {{< /tab >}}
  <!-- macOS -->
  {{< tab >}}
  Download Dragonfly from the [releases page](https://github.com/riffcc/dragonfly/releases).
  ```
  wget -O dragonfly https://github.com/dragonflycomputer/dragonfly/releases/download/v0.1.0-alpha1/dragonfly-darwin-amd64
  ```
  
  Copy the binary to /usr/local/bin/dragonfly and make it executable:
  ```
  sudo cp dragonfly /usr/local/bin/dragonfly
  sudo chmod +x /usr/local/bin/dragonfly
  ```
  
  Install Dragonfly:
  ```
  sudo dragonfly install
  ```
  
  You can now visit the web interface on port 3000 `http://<machine-ip-address>:3000`

  {{< /tab >}}
  
  <!--Windows -->
  {{< tab >}}
  Installation on Windows is not currently supported, and support is not planned at this time.
  
  However, you may be able to get Dragonfly running via WSL2 (Windows Subsystem for Linux).
  
  If this is a strong need, please contact us at support@dragonflycomputer.com!
  {{< /tab >}}

{{< /tabs >}}
