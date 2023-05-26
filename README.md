# Description

This is the updated docker-compose repo of all the media, home, and web server apps described in the following guides on our website:

- [Docker Media Server Ubuntu: Compose for 23 Awesome Apps](https://www.smarthomebeginner.com/docker-media-server-2022/)
- [Ultimate Traefik Docker Compose Guide [2022] with LetsEncrypt](https://www.smarthomebeginner.com/traefik-docker-compose-guide-2022/)
- [WordPress on Docker with Nginx, Traefik, LE SSL, Security, and Speed](https://www.smarthomebeginner.com/wordpress-on-docker-traefik/)
- [Ultimate Synology NAS Docker Compose Media Server 2022](https://www.smarthomebeginner.com/synology-nas-docker-media-server-2022/)

# Support My Work

Documenting, writing guides, and keeping this repo update-to-date takes hundreds of hours of work. Please consider supporting my work to show your appreciation. 

# Did this Repo help you?
- Become a patron and show us your strongest support. 

<div style="text-align:center;margin:20px"><a href="https://www.patreon.com/smarthomebeginner" target="_blank" rel="nofollow noopener noreferrer"><img src="https://www.smarthomebeginner.com/images/2022/05/become-a-patreon.jpg" alt="" width="434" height="102" /></a></div>

- Please consider buying us a coffee (or two) as a token of appreciation.

<div style="text-align:center;margin:20px"><a href="https://www.buymeacoffee.com/smarthomebeginr" target="_blank" rel="nofollow noopener noreferrer"><img src="https://www.smarthomebeginner.com/images/2020/04/coffee.png" alt="" width="340" height="77" /></a></div>

# Join our Community

<div style="text-align:center;margin:20px"><a href="https://www.smarthomebeginner.com/discord-github" target="_blank" rel="nofollow noopener noreferrer"><img src="https://www.smarthomebeginner.com/images/2022/05/join-discord-300x75.png" alt="" width="300" height="75" /></a></div>

- Do you need support or just want to chat with like-minded people. Join our discord. 
- The authors will try our best to help but support is not guaranteed. But you will find others who might have went through what you are going through and may be willing to pay it forward and help. 

<div style="padding:20px;border: 3px solid red;">
<h3>IMPORTANT</h3>
If you are going to start from scratch using this repo, be prepared to be patient and start slow. There are so many details to pay attention to. First start with the basic Docker Media Server guide linked above (with Nginx Proxy Manager instead of Traefik). 

When you are ready to upgrade to Traefik or prefer Traefik over Nginx Proxy Manager, I strongly suggest getting Traefik and Traefik dashboard up and running before adding any other app. 

Go step-by-step. If you bite too big of a piece, I guarantee you will choke.

</div>

<strong>Supporting Guides:</strong>

- [How to Install Docker and Docker Compose on Ubuntu 22.04 LTS](https://www.smarthomebeginner.com/install-docker-on-ubuntu-22-04/) [[VIDEO](https://youtu.be/nwFh4JBGD_0)]
- [How to Install Docker and Docker Compose on Ubuntu 20.04 LTS](https://www.smarthomebeginner.com/install-docker-on-ubuntu-20-04/)
- [Cloudflare Settings for Traefik Docker: DDNS, CNAMEs, & Tweaks](https://www.smarthomebeginner.com/cloudflare-settings-for-traefik-docker/)
- [Ultimate Docker to Podman Migration Guide: It's NOT difficult](https://www.smarthomebeginner.com/docker-to-podman-migration-guide/)
- [Nextcloud Docker with Traefik Reverse Proxy for Beginners](https://www.smarthomebeginner.com/traefik-docker-nextcloud/)

<strong>Security Guides:</strong>

- [Google OAuth 2 MFA Protection for Docker](https://www.smarthomebeginner.com/traefik-forward-auth-google-oauth-2022/)
- [Authelia MFA Protection for Docker](https://www.smarthomebeginner.com/docker-authelia-tutorial/)
- [Traefik Docker Security Best Practices](https://www.smarthomebeginner.com/traefik-docker-security-best-practices/)
- [Crowdsec Docker Compose Guide Part 1: Powerful IPS with Firewall Bouncer](https://www.smarthomebeginner.com/crowdsec-docker-compose-1-fw-bouncer/)
- [CrowdSec Docker Part 2: Improved IPS with Cloudflare Bouncer](https://www.smarthomebeginner.com/crowdsec-cloudflare-bouncer/)
- [CrowdSec Docker Part 3: Traefik Bouncer for Additional Security](https://www.smarthomebeginner.com/crowdsec-traefik-bouncer/)
- [CrowdSec Multiserver Docker (Part 4): For Ultimate Protection](https://www.smarthomebeginner.com/crowdsec-multiserver-docker/)

For security, I implemented CrowdSec multi-server setup in 2022. From the stats, it is blocking/mitigating well over 600 intrusion attempts per day on my servers. I will cover this in a separate guide later but you will find the docker-compose CrowdSec, Traefik Bouncer, and Cloudflare Bouncer Bouncers in my repo already.

### Obsolete Posts (for educational purposes):

The following posts have been updated/replaced by the posts linked above:

- [Docker Media Server with Traefik 2 Reverse Proxy](https://www.smarthomebeginner.com/traefik-2-docker-tutorial/)
- [Docker Media Server without Reverse Proxy ](https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/)
- [Docker Media Server with Traefik 1 Reverse Proxy](https://www.smarthomebeginner.com/traefik-reverse-proxy-tutorial-for-docker/)
- [Synology Docker Media Server with Traefik, Docker Compose, and Cloudflare](https://www.smarthomebeginner.com/synology-docker-media-server/)

### Description of Compose Files in this Repo

- docker-compose-t2.yml - this is my main stack with most apps/services (home aserver), including Traefik
- docker-compose-npm.yml - this is the basic media server stack with Nginx Proxy Manager instead of Traefik
- docker-compose-t2-web.yml - web server specific stack for WordPress and non-WordPress sites with Nginx and Traefik
- docker-compose-t2-synology.yml - apps/services that I run on Synology NAS using Docker Compose for Homelab use

<div style="padding:20px;border: 3px solid red;">
Please note that docker-compose files in the <strong>archives</strong> folder is not actively maintained. They may need updates/rework.
</div>

Almost any app/service from the docker-compose files listed above can be copy-pasted to any other compose file in this repo.

## MY SETUP

- Home Server (docker-compose-t2.yml) - Ubuntu 22.04 Proxmox LXC Container on AMD Ryzen 7 4800u ASROCK 4x4 Box 
- Media Server (docker-compose-t2-media-db.yml) - Ubuntu 22.04 Proxmox LXC Container on AMD Ryzen 7 4800u ASROCK 4x4 Box 
- Web Server (docker-compose-t2-web.yml) - Digital Ocean VPS (2 cores and 2 GB RAM)
- Synology (docker-compose-t2-synology.yml) - Synology DS918+ NAS.

I use Syncthing to keep certain key files synched between various systems.

## What apps are included in this stack?

The apps I use are scattered around in several different docker-compose files. Click the links below for specific installation guides.

 Some apps are used in more than one host and some on only one. 

### FRONTENDS

- Traefik - Reverse Proxy
- Nginx Proxy Manager - Reverse Proxy 
- Docker Socket Proxy - Secure Proxy for Docker API
- Traefik Custom Error Pages
- OAuth - Google OAuth 2 Forward Authentication
- Authelia - Private Forward Authentication
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
- MotionEye - Video Surveillance
- ZoneMinder - Video Surveillance
- MiFlora - MiFlora MQTT Daemon (MiFlora Plant Sensors)

### DATABASE

- MariaDB - MySQL Database
- phpMyAdmin - Database management
- [InfluxDB](https://www.smarthomebeginner.com/influxdb-docker-compose-guide/) - Database for sensor data
- Postgres - Database
- [Grafana](https://www.smarthomebeginner.com/grafana-docker-compose-guide/) - Graphical data visualization for InfluxDB data
- Varken - Monitor Plex, Sonarr, Radarr, and Other Data
- Redis - Key value store
- Redis Commander - Redis management

### DOWNLOADERS

- jDownloader - Download management
- TransmissionBT with VPN - Torrent Downloader.
- SABnzbd - Binary newsgrabber, NZB downloader
- Nzbget - Binary newsgrabber, NZB downloader
- qBittorrent with Wireguard VPN from [Surfshark](https://bit.ly/shb-surfshark) - Torrent downloader

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

- AirSonic - Music Server
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

- Firefox - Web Broswer
- Glances - System Information
- APCUPSD - APC UPS Management
- Guacamole - Remote desktop, SSH, on Telnet on any HTML5 Browser
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
- Gluetun - VPN client for docker containers and more
- DeUnhealth - Auto restart containers on VPN restart
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

## Starting and Stopping

I use bash_aliases to simplify starting and stopping containers/stack. Included in the repo is an example of bash_aliases I use (replace USER with your Linux username). Here are some example alias commands:

- <strong>dcup2</strong> - Start Docker Traefik 2 stack
- <strong>dcdown2</strong> - Stop Docker Traefik 2 stack
- <strong>dcrec2</strong> - Start or recreate a specific service
- <strong>dcstop2</strong> - Stop a specific service
- <strong>dcrestart2</strong> - Restart a specific service
- <strong>dclogs2</strong> - See real-time logs for the corresponding stack or service
- <strong>dcpull2</strong> - Pull new images for the corresponding stack or service