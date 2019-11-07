# Description
This is the updated docker-compose repo of all the media and home server apps described in the following guides on our website:

* Docker Media Server - [https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/](https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/)
* Traefik Reverse Proxy - [https://www.smarthomebeginner.com/traefik-reverse-proxy-tutorial-for-docker/](https://www.smarthomebeginner.com/traefik-reverse-proxy-tutorial-for-docker/).
* Docker with Google OAuth2 - [https://www.smarthomebeginner.com/google-oauth-with-traefik-docker/)(https://www.smarthomebeginner.com/google-oauth-with-traefik-docker/).

</p>

## But what about Traefik 2.0?
<p>At this point this stack is built on Traefik 1.0. As we move ours to Traefik 2.0, we will publish a new repository. </p>

<p>Having said that, Traefik 1.7.16 (the final release in v1) still works great for the purposes of a media / home server stack. Traefik 2.0 is significantly different requiring a major rework of your files. Therefore, if you are already on Traefik v1, we do not see a need to upgrade to v2 at this point. </p>

<p>If you are starting out, you may start with Traefik 2.0. However, documentation, community knowledge, and support for Traefik 2.0 is still quite limited at this time.</p>

## What apps are included in this stack?
We will try to keep this repo up-to-date. For now, here are the apps currently included in our stack:

### FRONTENDS

* Traefik - Reverse Proxy
* OAuth - Forward Authentication
* Portainer - Container Management
* Organizr - Unified Frontend
* Heimdall - Unified Frontend Alternative

### SMART HOME

* HA-Dockermon - Manage Docker containers in Home Assistant 
* Mosquitto - MQTT Broker
* ZoneMinder - Video Surveillance 

### DATABASE

* phpMyAdmin - Database management
* InfluxDB - Database for sensor data
* Grafana - Graphical data visualization for InfluxDB data

### INDEXERS

* Jackett - Torrent proxy
* NZBHydra2 - NZB meta search

### PVRS

* Lidarr - Music Management
* Radarr - Movie management
* Sonarr - TV Shows management

### DOWNLOADERS

* jDownloader - Download management
* SABnzbd - Binary newsgrabber (NZB downloader)
* qBittorrent - Torrent downloader
* TransmissionBT - Torrent Downloader

### MEDIA SERVER

* Plex - Media Server
* Emby - Media Server
* Tautulli - Previously PlexPy. Plex statistics and monitoring
* Plex-Sync - For Syncing watched status between plex servers 

### MEDIA FILE MANAGEMENT

* Bazarr - Subtitle Management
* Picard - Music Library Tagging and Management
* Handbrake - Video Conversion (Transcoding and compression)
* MKVToolNix - Video Editing (Remuxing - changing media container while keeping original source quality)
* MakeMKV - Video Editing (Ripping from Disks)
* FileBot - File renamer

### SYSTEM

* Firefox - Web Broswer
* Glances - System Information
* Logarr - Log Management
* Monitorr - Webfront to display the status of any webapp or service
* APCUPSD - APC UPS Management
* qDirStat - Directory Statistics
* Guacamole - Remote desktop, SSH, on Telnet on any HTML5 Browser 
* Guacamole Daemon - Needed for Guacamole
* IPVanish - VPN for container traffic

### MAINTENANCE

* Ouroboros - Automatic Docker Container Updates
* Docker-GC - Automatic Docker Garbage Collection

# Usage

First, install Docker and Docker Compose, as described in our <a href="https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/">Docker Media Server guide</a>. 

1. Clone the repo.
2. Rename the included `.env.example` to `.env`.
3. Edit variables in `.env` file. All variables (ie. ${XXX}) in docker-compose.yml come from `.env` file stored in the same place as docker-compose.yml. 
4. Ensure good permissions for the `.env` file (recommended: 640).
5. Start and stop your docker stack as described in our [Docker Media Server guide](https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/).
