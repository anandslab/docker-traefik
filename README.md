# Description

This is the updated docker-compose repo of all the media and home server apps described in the following guides on our website:

- [Docker Media Server with Traefik 2 Reverse Proxy](https://www.smarthomebeginner.com/traefik-2-docker-tutorial/)
- [WordPress on Docker with Nginx, Traefik, LE SSL, Security, and Speed](https://www.smarthomebeginner.com/wordpress-on-docker-traefik/)
- [Synology Docker Media Server with Traefik, Docker Compose, and Cloudflare](https://www.smarthomebeginner.com/synology-docker-media-server/)

<strong>Supporting Articles:</strong>

- [Cloudflare Settings for Traefik Docker: DDNS, CNAMEs, & Tweaks](https://www.smarthomebeginner.com/cloudflare-settings-for-traefik-docker/)
- [Google OAuth 2 MFA Protection for Docker](https://www.smarthomebeginner.com/google-oauth-with-traefik-docker/)
- [Authelia MFA Protection for Docker](https://www.smarthomebeginner.com/docker-authelia-tutorial/)
- [Traefik Docker Security Best Practices](https://www.smarthomebeginner.com/traefik-docker-security-best-practices/)

### Obsolete Posts:

The following posts have been combined and updated for Traefik v2 (linked above):

- [Docker Media Server without Reverse Proxy ](https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/)
- [Docker Media Server with Traefik 1 Reverse Proxy](https://www.smarthomebeginner.com/traefik-reverse-proxy-tutorial-for-docker/)

## A Note on Traefik 1 vs Traefik 2?

<strong>Update (April 19, 2020):</strong> I have switched from Traefik v1 to Traefik v2, which is now my default. Therefore, the setup for Traefik v1 will only receive minor updates (if any). If you are new, follow instructions for Traefik v2.

### Traefik 2 (CURRENT - GENERIC LINUX)

- docker-compose-t2.yml
- docker-compose-t2-vpn.yml
- docker-compose-t2-obsolete.yml (Apps that I do not use anymore)
- docker-compose-t2-web.yml (Docker stack on Virtual Private Server that Runs Wordpress and Other Websites)

### Traefik 2 (CURRENT - SYNOLOGY)

- docker-compose-t2-synology.yml (Apps that I run on Synology NAS using Docker Compose)
- Almost any app from the Traefik v2 docker-compose files listed above can be copy-pasted to the Synology Docker-Compose. I run a few on Synology and the rest on my Intel NUC Linux home server.

### Traefik 1 (NOT ACTIVELY MAINTAINED)

- docker-compose-t1.yml
- docker-compose-t1-vpn.yml
- docker-compose-t1-obsolete.yml (Apps that I do not use anymore)

### Traefik 1 - Docker Swarm Mode (NOT ACTIVELY MAINTAINED)

- docker-compose-t1-swarm.yml

## What apps are included in this stack?

We will try to keep this repo up-to-date. For now, here are the apps currently included in our stack:

### FRONTENDS

In paranthesis, the system on which it runs.

- NUC - Intel NUC Home Server with Pop OS
- SYNOLOGY - Synology DS918+ NAS
- WEB - Digital Ocean Virtual Private Server with Ubuntu 20.04
- OBSOLETE - Not used anymore

See the corresponding Docker Compose file for the compose snippet.

- Traefik - Reverse Proxy (NUC and WEB)
- Docker Socket Proxy - Secure Proxy for Docker API (NUC, SYNOLOGY, and WEB)
- Traefik Custom Error Pages (OBSOLETE)
- OAuth - Google OAuth 2 Forward Authentication (NUC and WEB)
- Authelia - Private Forward Authentication (NUC and WEB)
- Portainer - Container Management (SYNOLOGY and WEB)
- Organizr - Unified Frontend (NUC)
- Heimdall - Unified Frontend Alternative (NUC)
- Autoindex - Plain text Index to All Files (NUC)

### SMART HOME

- Home Assistant Core - Home Automation (NUC)
- HA-Dockermon - Manage Docker containers in Home Assistant (OBSOLETE)
- Mosquitto - MQTT Broker (SYNOLOGY)
- MotionEye - Video Surveillance (NUC)
- ZoneMinder - Video Surveillance (OBSOLETE)
- MiFlora - MiFlora MQTT Daemon (MiFlora Plant Sensors) (OBSOLETE)

### DATABASE

- MariaDB - MySQL Database (SYNOLOGY and WEB)
- phpMyAdmin - Database management (NUC and WEB)
- InfluxDB - Database for sensor data (SYNOLOGY)
- Postgres - Database (OBSOLETE)
- Grafana - Graphical data visualization for InfluxDB data (NUC)
- Varken - Monitor Plex, Sonarr, Radarr, and Other Data (OBSOLETE)
- Redis - Key value store (SYNOLOGY and WEB)
- Redis Commander - Redis management (OBSOLETE)

### DOWNLOADERS

- jDownloader - Download management (NUC)
- TransmissionBT with VPN - Torrent Downloader with [IPVanish](https://www.smarthomebeginner.com/go/ipvanish) VPN. (NUC)
- SABnzbd - Binary newsgrabber, NZB downloader (NUC)
- qBittorrent with VPN - Torrent downloader (OBSOLETE)

### INDEXERS

- NZBHydra2 - NZB meta search (NUC)
- Jackett - Torrent proxy (NUC)

### PVRS

- Lidarr - Music Management (NUC)
- Radarr - Movie management (NUC)
- Sonarr - TV Shows management (NUC)
- LazyLibrarian - Books Management (NUC)

### MEDIA SERVER

- AirSonic - Music Server (NUC)
- Calibre - Ebook/Audiobook Server (NUC)
- Calibre-Web - Ebook/Audiobook Reader (NUC)
- Plex - Media Server (NUC and SYNOLOGY)
- Emby - Media Server (NUC)
- Jellyfin - Media Server (NUC)
- Ombi - Media Requests (NUC)
- Tautulli - Previously PlexPy. Plex statistics and monitoring (NUC)
- Plex-Sync - For Syncing watched status between plex servers (NUC)
- PhotoShow - Personal Photo Gallery and viewer (NUC)
- TellyTv- IPTV proxy for Plex (OBSOLETE)
- xTeve- IPTV proxy for Plex (OBSOLETE)

### MEDIA FILE MANAGEMENT

- Bazarr - Subtitle Management (NUC)
- Picard - Music Library Tagging and Management (NUC)
- Handbrake - Video Conversion, Transcoding, and Compression (NUC)
- MKVToolNix - Video Editing, Remuxing (changing media container while keeping original source quality) (NUC)
- MakeMKV - Video Editing (Ripping from Disks) (NUC)
- FileBot - File renamer (NUC)

### UTILITIES

- Firefox - Web Broswer (NUC)
- Duplicati - Backup App (NUC)
- Glances - System Information (NUC, SYNOLOGY, and WEB)
- APCUPSD - APC UPS Management (NUC)
- Guacamole - Remote desktop, SSH, on Telnet on any HTML5 Browser (NUC)
- Guacamole Daemon - Needed for Guacamole (NUC)
- Dozzle - Docker logs viewer (NUC and WEB)
- qDirStat - Directory Statistics (NUC)
- StatPing - Status Page & Monitoring Server (NUC)
- SmokePing - Network Latency Monitoring (OBSOLETE)
- VS Code Server - Code Editor (NUC and WEB)
- Logarr - Log Management (OBSOLETE)
- Monitorr - Webfront to display the status of any webapp or service (OBSOLETE)
- Cloud Commander - Web File Manager (OBSOLETE)
- Cloud9 - Cloud IDE (OBSOLETE)
- SMTP To Telegram - Sends all incoming Email messages to Telegram (NUC)
- UniFi Controller - Controller for Ubiquiti UniFi Network Gear (WEB)

### WEB

- Nginx - Web Server (WEB)
- php7 - PHP-FPM (WEB)

### MAINTENANCE

- Watchtower - Automatic Docker Container Updates (NUC, SYNOLOGY, and WEB)
- Docker-GC - Automatic Docker Garbage Collection (NUC, SYNOLOGY, and WEB)
- Traefik Certificate Dumper - Extract Traefik SSL Certs (NUC and WEB)
- Cloudflare DDNS - Dynamic IP Updater (SYNOLOGY)
- Cloudflare Companion - Automatic CNAME creation for services (NUC)

# Usage

## Installation

First, install Docker and Docker Compose, as described in our <a href="https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/">Docker Media Server guide</a>.

1. Clone the repo.
2. Configure Traefik Docker-Compose snippet and CLI arguments.

- Edit domain name.
- DNS Challenge (for LetsEncrypt verification) is enabled by default for cloudflare. Use the [Traefik Reverse Proxy guide](https://www.smarthomebeginner.com/traefik-reverse-proxy-tutorial-for-docker/) for help with this.
- For other providers other than cloudflare, [check here](https://docs.traefik.io/v2.0/https/acme/#providers).

3. (Optional) Enable or use HTTP Basic Authentication by renaming `shared\.htpasswd.example` to `shared\.htpasswd` in the folder and adding username and hashed password to it.
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

- <strong>dc1up</strong> or <strong>dc2up</strong> - Create network and start Docker Traefik 1 or 2 stack
- <strong>dc1down</strong> or <strong>dc2down</strong> - Stop Docker Traefik 1 or 2 stack
- <strong>dcup1</strong> or <strong>dcup2</strong> - Start Docker Traefik 1 or 2 stack
- <strong>dcup1v</strong> or <strong>dcup2v</strong> - Start Docker Trafik 1 or 2 VPN stack
- <strong>dcdown1</strong> or <strong>dcdown2</strong> - Stop Docker Traefik 1 or 2 stack
- <strong>dcdown1v</strong> or <strong>dcdown2v</strong> - Stop Docker Traefik 1 or 2 VPN stack
- <strong>dcrec1</strong> or <strong>dcrec2</strong> - Start or recreate a specific service
- <strong>dcstop1</strong> or <strong>dcstop2</strong> - Stop a specific service
- <strong>dcrestart1</strong> or <strong>dcrestart2</strong> - Restart a specific service
- <strong>dclogs1</strong> or <strong>dclogs1v</strong> or <strong>dclogs2</strong> or <strong>dclogs2v</strong> - See real-time logs for the corresponding stack or service
- <strong>dcpull1</strong> or <strong>dcpull1v</strong> or <strong>dcpull2</strong> or <strong>dcpull2v</strong> - Pull new images for the corresponding stack or service

## Did this Repo help you?

Please consider buying us a coffee (or two) as a token of appreciation.

<a href="https://www.buymeacoffee.com/smarthomebeginr" target="_blank" rel="nofollow noopener noreferrer"><img src="https://www.smarthomebeginner.com/images/2020/04/coffee.png" alt="" width="340" height="77" class="aligncenter size-full wp-image-41005" /></a>
