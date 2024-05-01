# Description

This is the updated docker-compose repo of all the media, home, and web server apps described on SmartHomeBeginner.com. 

## Docker Server Series:

### Ubuntu/Debian:

<ol>
<li><a href="https://www.smarthomebeginner.com/ultimate-docker-server-1-os-preparation/">Ultimate Docker Server: Getting Started with OS Preparation</a> <span style="color:#6b5b95">[<a href="https://youtu.be/-ZSQdJ62r-Q" target="_blank" rel="noopener">VIDEO</a>]</span> <span style="color:#50C878">[2024]</span></li>
<li><a href="https://www.smarthomebeginner.com/docker-media-server-2024/">Docker Media Server Ubuntu/Debian with 60+ Awesome Apps</a> <span style="color:#50C878">[2024]</span></li>
<li>ZeroTier VPN Ubuntu, Docker, Synology, Windows: Secure on-the-go access <span style="color:#ffa400">[coming soon]</span></li>
<li>Nginx Proxy Manager Docker Compose Guide: Simplest Reverse Proxy <span style="color:#ffa400">[coming soon]</span></li>
<li>Traefik Reverse Proxy
<ul>
<li>Traefik v3: <a href="https://www.smarthomebeginner.com/traefik-v3-docker-compose-guide-2024/">Ultimate Traefik v3 Docker Compose Guide [2024]: LE, SSL, Reverse Proxy</a> <span style="color:#50C878">[2024]</span></li>
<li>Traefik v2: <a href="https://www.smarthomebeginner.com/traefik-docker-compose-guide-2024/">Ultimate Traefik Docker Compose Guide: LE, SSL, Reverse Proxy</a> <span style="color:#50C878">[2024]</span></li>
</ul>
</li>
<li><a href="https://www.smarthomebeginner.com/authelia-docker-compose-guide-2024/">Authelia Docker Compose Guide: Secure 2-Factor Authentication</a> <span style="color:#50C878">[2024]</span></li>
<li><a href="https://www.smarthomebeginner.com/google-oauth-traefik-forward-auth-2024/">Google OAuth Docker Compose Guide: Multi-Factor Authentication</a> <span style="color:#50C878">[2024]</span></li>
<li><a href="https://www.smarthomebeginner.com/traefik-docker-security-best-practices/">Docker Security Practices for Homelab: Secrets, Firewall, and more</a></li>
<li><a href="https://www.smarthomebeginner.com/cloudflare-settings-for-traefik-docker/">Cloudflare Settings for Docker Traefik Stacks</a></li>
<li>Implementing a Backup System for Docker Traefik Stack <span style="color:#ffa400">[coming soon]</span></li>
</ol>

### Synology:
- [Ultimate Synology NAS Docker Compose Media Server 2022](https://www.smarthomebeginner.com/synology-nas-docker-media-server-2022/)

### Web Server:
- [WordPress on Docker with Nginx, Traefik, LE SSL, Security, and Speed](https://www.smarthomebeginner.com/wordpress-on-docker-traefik/)

### Automate the Process:

- [Auto-Traefik: Dead Simple Traefik Reverse Proxy Automator for Docker](https://www.smarthomebeginner.com/auto-traefik/) [[VIDEO](https://www.youtube.com/watch?v=ePBLJTyRgdQ&list=PL1Hno7tIbSWViTyCXl9xNdXXU-1bVxIFD)]

# Support My Work

Documenting, writing guides, and keeping this repo update-to-date takes hundreds of hours of work. Please consider supporting my work to show your appreciation. 

## Did this Repo help you?

<div style="text-align:center;margin:20px"><a href="https://www.smarthomebeginner.com/membership-account/memberships-products-services/" target="_blank" rel="nofollow noopener noreferrer"><img src="https://www.smarthomebeginner.com/images/2024/01/become-a-member.png" alt="" width="258" height="76" /></a></div>

## Join our Community

<div style="text-align:center;margin:20px"><a href="https://www.smarthomebeginner.com/discord-github" target="_blank" rel="nofollow noopener noreferrer"><img src="https://www.smarthomebeginner.com/images/2022/05/join-discord-300x75.png" alt="" width="300" height="75" /></a></div>

- Do you need support or just want to chat with like-minded people. Join our discord. 
- The authors will try our best to help but support is not guaranteed. But you will find others who might have went through what you are going through and may be willing to pay it forward and help. 

# Supporting Guides

## Security:

- [Traefik Docker Security Best Practices](https://www.smarthomebeginner.com/traefik-docker-security-best-practices/)
- [Crowdsec Docker Compose Guide Part 1: Powerful IPS with Firewall Bouncer](https://www.smarthomebeginner.com/crowdsec-docker-compose-1-fw-bouncer/)
- [CrowdSec Docker Part 2: Improved IPS with Cloudflare Bouncer](https://www.smarthomebeginner.com/crowdsec-cloudflare-bouncer/)
- [CrowdSec Docker Part 3: Traefik Bouncer for Additional Security](https://www.smarthomebeginner.com/crowdsec-traefik-bouncer/)
- [CrowdSec Multiserver Docker (Part 4): For Ultimate Protection](https://www.smarthomebeginner.com/crowdsec-multiserver-docker/)

For security, I implemented CrowdSec multi-server setup in 2022. From the stats, it is blocking/mitigating well over 600 intrusion attempts per day on my servers. I will cover this in a separate guide later but you will find the docker-compose CrowdSec, Traefik Bouncer, and Cloudflare Bouncer Bouncers in my repo already.

## Others:

- [How to Install Docker and Docker Compose on Ubuntu 22.04 LTS](https://www.smarthomebeginner.com/install-docker-on-ubuntu-22-04/) [[VIDEO](https://youtu.be/nwFh4JBGD_0)]
- [Cloudflare Settings for Traefik Docker: DDNS, CNAMEs, & Tweaks](https://www.smarthomebeginner.com/cloudflare-settings-for-traefik-docker/)
- [Ultimate Docker to Podman Migration Guide: It's NOT difficult](https://www.smarthomebeginner.com/docker-to-podman-migration-guide/)
- [Nextcloud Docker with Traefik Reverse Proxy for Beginners](https://www.smarthomebeginner.com/traefik-docker-nextcloud/)

# Understanding This Repository

## My Setup

I have 5 docker hosts. I sync all my Docker stacks using Syncthing and push the files to GitHub so I can share with the community. 

- **_docker-compose-hs.yml:_** Docker Compose for <u>Home Server</u> on Ubuntu Server Proxmox LXC Container.
- **_docker-compose-mds.yml:_** Docker Compose for <u>Media/Database Server</u> on Ubuntu Server Proxmox LXC Container.
- **_docker-compose-dns.yml:_** Docker Compose for <u>AdBlock/ DNS Server</u> on Raspberry Pi 4B.
- **_docker-compose-ws.yml:_** Docker Compose for <u>Web Server</u> on Digital Ocean VPS, which powers this website.
- **_docker-compose-ds918.yml:_** Docker Compose for <u>Synology DS918+</u> NAS.

Syncing also allows me to have a backup of one system's configuration file in all the other hosts. For this reason, where applicable, I segregate or name files/folders with their hostname (for example: **_hs_** for Home Server).

Almost any app/service from the docker-compose files listed above can be copy-pasted to any other compose file in this repo.

## Archives
Files and folders inside _archives_ are not actively maintained. But they may still provide a good starting point. 

## What apps are included in this stack?

The apps I use are scattered around in several different docker-compose files. Click the links below for specific installation guides.

Some apps are used in more than one host and some on only one. 

**This is not an exhaustive list**

### FRONTENDS

- Traefik - Reverse Proxy
- Nginx Proxy Manager - Reverse Proxy 
- Docker Socket Proxy - Secure Proxy for Docker API
- [OAuth](https://www.smarthomebeginner.com/traefik-forward-auth-google-oauth-2022/) - Google OAuth 2 Forward Authentication
- [Authelia](https://www.smarthomebeginner.com/docker-authelia-tutorial/) - Private Forward Authentication
- [Portainer](https://www.smarthomebeginner.com/portainer-docker-compose-guide/) - Container Management
- Organizr - Dashboard for Apps
- Heimdall - Dashboard for Apps
- Homepage - Dashboard for Apps
- Dashy - Dashboard for Apps
- Autoindex - Plain text Index to All Files

### SMART HOME

- Home Assistant Core - Home Automation
- HA-Dockermon - Manage Docker containers in Home Assistant
- Mosquitto - MQTT Broker
- [MotionEye](https://www.smarthomebeginner.com/motioneye-docker-guide/) - Video Surveillance
- [Frigate](https://www.smarthomebeginner.com/frigate-docker-guide/) - Video Surveillance
- [ZoneMinder](https://www.smarthomebeginner.com/zoneminder-docker-guide/) - Video Surveillance
- MiFlora - MiFlora MQTT Daemon (MiFlora Plant Sensors)

### DATABASE

- MariaDB - MySQL Database
- phpMyAdmin - Database management
- [InfluxDB](https://www.smarthomebeginner.com/influxdb-docker-compose-guide/) - Database for sensor data
- Postgres - Database
- [Grafana](https://www.smarthomebeginner.com/grafana-docker-compose-guide/) - Graphical data visualization for InfluxDB data
- Varken - Monitor Plex, Sonarr, Radarr, and Other Data
- [Redis](https://www.smarthomebeginner.com/redis-docker-compose-example/) - Key value store
- Redis Commander - Redis management

### DOWNLOADERS

- jDownloader - Download management
- TransmissionBT with VPN - Torrent Downloader.
- SABnzbd - Binary newsgrabber, NZB downloader
- Nzbget - Binary newsgrabber, NZB downloader
- [qBittorrent](https://www.smarthomebeginner.com/gluetun-docker-guide/) with Wireguard VPN from [Surfshark](https://bit.ly/shb-surfshark) - Torrent downloader

### INDEXERS

- NZBHydra2 - NZB meta search 
- Jackett - Torrent proxy
- Prowlarr - Torrent proxy

### PVRS

- Lidarr - Music Management
- Radarr - Movie management
- Sonarr - TV Shows management
- LazyLibrarian - Books Management
- Readarr - Books Management

### MEDIA SERVER

- AirSonic Advanced - Music Server
- NaviDrome - Music Server
- FunkWhale - Music Server
- Calibre - Ebook/Audiobook Server
- Calibre-Web - Ebook/Audiobook Reader
- [Plex](https://www.smarthomebeginner.com/plex-docker-compose/) - Media Server
- Emby - Media Server
- [Jellyfin](https://www.smarthomebeginner.com/jellyfin-docker-compose/) - Media Server
- Ombi - Media Requests
- Tautulli - Previously PlexPy. Plex statistics and monitoring
- Plex-Sync - For Syncing watched status between plex servers
- PhotoShow - Personal Photo Gallery and viewer
- TellyTv- IPTV proxy for Plex
- xTeve- IPTV proxy for Plex

### MEDIA FILE MANAGEMENT

- Bazarr - Subtitle Management
- Picard - Music Library Tagging and Management
- Handbrake - Video Conversion, Transcoding, and Compression
- MKVToolNix - Video Editing, Remuxing (changing media container while keeping original source quality)
- MakeMKV - Video Editing (Ripping from Disks)
- FileBot - File renamer
- Tiny Media Manager - Media Files Management

### UTILITIES

- Firefox - Web Broswerstack
- Glances - System Information
- APCUPSD - APC UPS Management
- [Guacamole](https://www.smarthomebeginner.com/install-guacamole-on-docker/) - Remote desktop, SSH, on Telnet on any HTML5 Browser
- Guacamole Daemon - Needed for Guacamole
- [Dozzle](https://www.smarthomebeginner.com/dozzle-docker-compose-guide/) - Docker logs viewer
- qDirStat - Directory Statistics
- StatPing - Status Page & Monitoring Server
- SmokePing - Network Latency Monitoring
- VS Code Server - Code Editor
- Logarr - Log Management
- Monitorr - Webfront to display the status of any webapp or service
- Cloud Commander - Web File Manager
- Cloud9 - Cloud IDE
- SMTP To Telegram - Sends all incoming Email messages to Telegram
- UniFi Controller - Controller for Ubiquiti UniFi Network Gear
- Rclone - Mount Cloud/Google Drive
- MergerFS - Merge local and remote file systems
- [Gluetun](https://www.smarthomebeginner.com/gluetun-docker-guide/) - VPN client for docker containers and more
- [DeUnhealth](https://www.smarthomebeginner.com/gluetun-docker-guide/) - Auto restart containers on VPN restart
- [AdGuard Home](https://www.smarthomebeginner.com/adguard-home-docker-compose-guide/) - DNS Sinkhole / Ad-blocker

### WEB

- Nginx - Web Server
- php7 - PHP-FPM

### MAINTENANCE

- Watchtower - Automatic Docker Container Updates
- Docker-GC - Automatic Docker Garbage Collection
- Traefik Certificate Dumper - Extract Traefik SSL Certs
- Cloudflare DDNS - Dynamic IP Updater
- Cloudflare Companion - Automatic CNAME creation for services
- WhoAmI - For testing.

## Bash Aliases 

I use bash_aliases to simplify starting and stopping containers/stack. Included in the repo is an example of bash_aliases I use (replace USER with your Linux username). 

Download it to a known location (e.g. /home/user/docker/shared/config/). Then add the following code block to `.bashrc` file in the user's home folder.

```
if [ -f "$HOME/docker/shared/config/bash_aliases" ]; then
    . $HOME/docker/shared/config/bash_aliases
fi
```
Here are some example alias commands:

- `dcup` - Start Docker Traefik 2 stack
- `dcdown` - Stop Docker Traefik 2 stack
- `dcrec` - Start or recreate a specific service or the full stack
- `dcstop` - Stop a specific service or the full stack
- `dcrestart` - Restart a specific service or the full stack
- `dclogs` - See real-time logs for the corresponding stack or service
- `dcpull` - Pull new images for the corresponding stack or service