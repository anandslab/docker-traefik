# Description

This is the updated docker-compose repo of all the media, home, and web server apps described in the following guides on our website:

- [Docker Media Server with Traefik 2 Reverse Proxy](https://www.smarthomebeginner.com/traefik-2-docker-tutorial/)
- [WordPress on Docker with Nginx, Traefik, LE SSL, Security, and Speed](https://www.smarthomebeginner.com/wordpress-on-docker-traefik/)
- [Synology Docker Media Server with Traefik, Docker Compose, and Cloudflare](https://www.smarthomebeginner.com/synology-docker-media-server/)

<div style="padding:20px;border: 3px solid red;">
<h3>IMPORTANT</h3>
If you are going to start from scratch using this repo, be prepared to be patient and start slow. There are so many details to pay attention to. I strongly suggest getting Traefik and Traefik dashboard up and running before adding any other app. Here is the order I would recommend:

<ol>
<li>Traefik with HTTP Authentication. This requires:</li>
<ul>
<li>.env file</li>
<li>secrets</li>
<li>network definition</li>
<li>middlewares and chains</li>
</ul>
<li>Socket Proxy</li>
<li>Check to ensure Traefik still works</li>
<li>OAuth or Authelia (optional)</li>
<li>Check to ensure OAuth works</li>
<li>Put Traefik dashboard behind OAuth or Authelia and disable HTTP Authentication</li>
<li>Ensure Traefik dashboard works behind OAuth/Authelia</li>
<li>Proceed to add portainer and other apps/services</li>
</ol>

Go step-by-step. If you bite too big of a piece, I guarantee you will choke.

</div>

<strong>Supporting Articles:</strong>

- [Cloudflare Settings for Traefik Docker: DDNS, CNAMEs, & Tweaks](https://www.smarthomebeginner.com/cloudflare-settings-for-traefik-docker/)
- [Google OAuth 2 MFA Protection for Docker](https://www.smarthomebeginner.com/google-oauth-with-traefik-docker/)
- [Authelia MFA Protection for Docker](https://www.smarthomebeginner.com/docker-authelia-tutorial/)
- [Traefik Docker Security Best Practices](https://www.smarthomebeginner.com/traefik-docker-security-best-practices/)
- [Nextcloud Docker with Traefik Reverse Proxy for Beginners](https://www.smarthomebeginner.com/traefik-docker-nextcloud/)

### Obsolete Posts (for educational purposes):

The following posts have been combined and updated for Traefik v2 (linked above):

- [Docker Media Server without Reverse Proxy ](https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/)
- [Docker Media Server with Traefik 1 Reverse Proxy](https://www.smarthomebeginner.com/traefik-reverse-proxy-tutorial-for-docker/)

## Docker, Docker Compose, and Traefik Versions (updated January 23, 2022)

- Docker: 20.10.12
- Docker Compose: 2.1.1
- Traefik: 2.6

<strong>Known Issue:</strong> Cloudflare Companion does not seem to work with Docker Compose v2.2 and above. I could not figure out why. If someone figures it out please share. So at this point v2.1.1 is the highest version I can go for Docker Compose.

<strong>Update (September 13, 2021):</strong> I moved from TOML to YAML for Traefik 2 dynamic configurations. I have included example configuration files for both. However, since I do not use TOML anymore, there may be minor syntax errors or typos.

### Description of Compose Files in this Repo

- docker-compose-t2.yml - this stack has the most apps/services
- docker-compose-t2-web.yml - web server specific stack for WordPress and non-WordPress sites with Nginx
- docker-compose-t2-synology.yml - apps/services that I run on Synology NAS using Docker Compose for Homelab use
- docker-compose-t2-obsolete.yml - apps/services that I once tried/used but don't use anymore (future compatibility not guaranteed)

Almost any app/service from the Traefik v2 docker-compose files listed above can be copy-pasted to any other compose file in this repo.

### Compose Files Archive (NOT ACTIVELY MAINTAINED)

- archives/docker-compose-t1.yml
- archives/docker-compose-t1-vpn.yml
- archives/docker-compose-t1-obsolete.yml
- archives/docker-compose-t1-swarm.yml

## MY SETUP

- MAIN - Ubuntu 20.04 Virtual Machine on Intel Xeon 5420 Proxmox Host
- WEB - Ubuntu 20.04 LXC Container on Intel Xeon 5420 Proxmox Host
- SYNOLOGY - Synology DS918+ NAS

I use Syncthing to keep certain key files synched between various systems.

## What apps are included in this stack?

The apps I use are scattered around in several different docker-compose files. Some apps are used in more than one host and some on only one.

### FRONTENDS

- Traefik - Reverse Proxy
- Docker Socket Proxy - Secure Proxy for Docker API
- Traefik Custom Error Pages (OBSOLETE)
- OAuth - Google OAuth 2 Forward Authentication
- Authelia - Private Forward Authentication
- Portainer - Container Management
- Organizr - Unified Frontend
- Heimdall - Unified Frontend Alternative
- Autoindex - Plain text Index to All Files

### SMART HOME

- Home Assistant Core - Home Automation
- HA-Dockermon - Manage Docker containers in Home Assistant (OBSOLETE)
- Mosquitto - MQTT Broker
- MotionEye - Video Surveillance
- ZoneMinder - Video Surveillance (OBSOLETE)
- MiFlora - MiFlora MQTT Daemon (MiFlora Plant Sensors) (OBSOLETE)

### DATABASE

- MariaDB - MySQL Database
- phpMyAdmin - Database management
- InfluxDB - Database for sensor data
- Postgres - Database (OBSOLETE)
- Grafana - Graphical data visualization for InfluxDB data
- Varken - Monitor Plex, Sonarr, Radarr, and Other Data (OBSOLETE)
- Redis - Key value store
- Redis Commander - Redis management

### DOWNLOADERS

- jDownloader - Download management
- TransmissionBT with VPN - Torrent Downloader with [IPVanish](https://www.smarthomebeginner.com/go/ipvanish) VPN.
- SABnzbd - Binary newsgrabber, NZB downloader (OBSOLETE)
- Nzbget - Binary newsgrabber, NZB downloader
- qBittorrent with VPN - Torrent downloader (OBSOLETE)

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

- AirSonic - Music Server (OBSOLETE)
- NaviDrome - Music Server
- FunkWhale - Music Server
- Calibre - Ebook/Audiobook Server (OBSOLETE)
- Calibre-Web - Ebook/Audiobook Reader (OBSOLETE)
- Plex - Media Server
- Emby - Media Server (OBSOLETE)
- Jellyfin - Media Server
- Ombi - Media Requests (OBSOLETE)
- Tautulli - Previously PlexPy. Plex statistics and monitoring
- Plex-Sync - For Syncing watched status between plex servers
- PhotoShow - Personal Photo Gallery and viewer (OBSOLETE)
- TellyTv- IPTV proxy for Plex (OBSOLETE)
- xTeve- IPTV proxy for Plex (OBSOLETE)

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
- Dozzle - Docker logs viewer
- qDirStat - Directory Statistics
- StatPing - Status Page & Monitoring Server
- SmokePing - Network Latency Monitoring (OBSOLETE)
- VS Code Server - Code Editor
- Logarr - Log Management (OBSOLETE)
- Monitorr - Webfront to display the status of any webapp or service (OBSOLETE)
- Cloud Commander - Web File Manager (OBSOLETE)
- Cloud9 - Cloud IDE (OBSOLETE)
- SMTP To Telegram - Sends all incoming Email messages to Telegram (OBSOLETE)
- UniFi Controller - Controller for Ubiquiti UniFi Network Gear
- Rclone - Mount Cloud/Google Drive
- MergerFS - Merge local and remote file systems (OBSOLETE)

### WEB

- Nginx - Web Server
- php7 - PHP-FPM

### MAINTENANCE

- Watchtower - Automatic Docker Container Updates
- Docker-GC - Automatic Docker Garbage Collection
- Traefik Certificate Dumper - Extract Traefik SSL Certs
- Cloudflare DDNS - Dynamic IP Updater
- Cloudflare Companion - Automatic CNAME creation for services

# Usage

--------- ANYTHING THAT HAS "example" IN THE NAME WILL HAVE TO BE RENAMED APPROPRIATELY ---------

## Installation

First, install Docker and Docker Compose, as described in our <a href="https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/">Docker Media Server guide</a>.

1. Clone the repo.
2. Configure Traefik Docker-Compose snippet and CLI arguments.

- Edit domain name.
- DNS Challenge (for LetsEncrypt verification) is enabled by default for cloudflare. Use the [Traefik Reverse Proxy guide](https://www.smarthomebeginner.com/traefik-reverse-proxy-tutorial-for-docker/) for help with this.
- For other providers other than cloudflare, [check here](https://docs.traefik.io/v2.0/https/acme/#providers).

3. (Optional) Enable or use HTTP Basic Authentication by renaming the `secrets_example` folder to `secrets` adding username and hashed password to the `htpasswd` file.
4. Configure environmental variables (`.env` file)

- Rename the included `.env.example` to `.env`.
- Edit variables in `.env` file.
- All variables (ie. `${XXX}`) in docker-compose.yml come from `.env` file stored in the same place as docker-compose.yml.
- Ensure good permissions for the `.env` file (recommended: 640).

5. Edit `docker-compose-t2.yml` to include only the services you want or add additional services to it. Be sure to read the comments for each app and create any required files. You can copy snippets between any of the various docker-compose files in the repo.
6. Start and stop your docker stack as described in our [Docker Media Server guide](https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/).
7. (Optional) Put non-docker apps behind Traefik proxy by creating traefik rules based on the examples provided.

## Starting and Stopping

I use bash_aliases to simplify starting and stopping containers/stack. Included in the repo is an example of bash_aliases I use (replace USER with your Linux username). Here are some example alias commands:

- <strong>dcup2</strong> - Start Docker Traefik 2 stack
- <strong>dcdown2</strong> - Stop Docker Traefik 2 stack
- <strong>dcrec2</strong> - Start or recreate a specific service
- <strong>dcstop2</strong> - Stop a specific service
- <strong>dcrestart2</strong> - Restart a specific service
- <strong>dclogs2</strong> - See real-time logs for the corresponding stack or service
- <strong>dcpull2</strong> - Pull new images for the corresponding stack or service

## Did this Repo help you?

Please consider buying us a coffee (or two) as a token of appreciation.

<a href="https://www.buymeacoffee.com/smarthomebeginr" target="_blank" rel="nofollow noopener noreferrer"><img src="https://www.smarthomebeginner.com/images/2020/04/coffee.png" alt="" width="340" height="77" class="aligncenter size-full wp-image-41005" /></a>
