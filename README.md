# Description
This is the updated docker-compose repo of all the media and home server apps described in the following guides on our website:

* Docker Media Server - [https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/](https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/)
* Traefik Reverse Proxy - [https://www.smarthomebeginner.com/traefik-reverse-proxy-tutorial-for-docker/](https://www.smarthomebeginner.com/traefik-reverse-proxy-tutorial-for-docker/)
* Docker with Google OAuth2 - [https://www.smarthomebeginner.com/google-oauth-with-traefik-docker/](https://www.smarthomebeginner.com/google-oauth-with-traefik-docker/)

## A Note on Traefik 1 vs Traefik 2?
<p><strong>Update (December 16, 2019):</strong> First draft of Traefik 2.1 setup pushed to the repository. At this point, it works for most of the apps. Still a lot to be figured out and optimized. Look for a detailed guide on our website in the coming days.</p>

### Traefik 1
* docker-compose-t1.yml
* docker-compose-t1-vpn.yml
* docker-compose-t1-obsolete.yml (Apps that we do not use anymore)

### Traefik 1 - Docker Swarm Mode
* docker-compose-t1-swarm.yml

### Traefik 2
* docker-compose-t2.yml
* docker-compose-t2-vpn.yml

<blockquote>
<p>At this point we still prefer Traefik  1. As we move ours to Traefik 2, we will publish a new repository. </p>

<p>Having said that, Traefik 1.7.16 (the final release in v1.x.x) still works great for the purposes of a media / home server stack. Traefik 2 is significantly different requiring a major rework of your files. Therefore, if you are already on Traefik 1, we do not see a need to upgrade to Traefik 2 at this point. </p>

<p>If you are starting out, you may start with Traefik 2. However, documentation, community knowledge, and support for Traefik 2 is still quite limited at this time.</p>
</blockquote>

## What apps are included in this stack?
We will try to keep this repo up-to-date. For now, here are the apps currently included in our stack:

### FRONTENDS

* Traefik - Reverse Proxy
* OAuth - Forward Authentication
* Portainer - Container Management
* Organizr - Unified Frontend
* Heimdall - Unified Frontend Alternative
* Autoindex - Plain text Index to All Files

### SMART HOME

* HA-Dockermon - Manage Docker containers in Home Assistant 
* Mosquitto - MQTT Broker
* ZoneMinder - Video Surveillance 

### DATABASE

* phpMyAdmin - Database management
* InfluxDB - Database for sensor data
* Postgres - Database
* Grafana - Graphical data visualization for InfluxDB data
* Varken - Monitor Plex, Sonarr, Radarr, and Other Data

### DOWNLOADERS

* jDownloader - Download management
* SABnzbd - Binary newsgrabber (NZB downloader)
* qBittorrent - Torrent downloader
* TransmissionBT - Torrent Downloader

### INDEXERS

* Jackett - Torrent proxy
* NZBHydra2 - NZB meta search

### PVRS

* Lidarr - Music Management
* Radarr - Movie management
* Sonarr - TV Shows management

### MEDIA SERVER

* Plex - Media Server
* Jellyfin - Media Server
* Emby - Media Server (OBSOLETE)
* Tautulli - Previously PlexPy. Plex statistics and monitoring
* Plex-Sync - For Syncing watched status between plex servers 
* Telly Tv- IPTV proxy for Plex

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
* Monitorr - Webfront to display the status of any webapp or service (OBSOLETE)
* APCUPSD - APC UPS Management
* qDirStat - Directory Statistics
* Guacamole - Remote desktop, SSH, on Telnet on any HTML5 Browser 
* Guacamole Daemon - Needed for Guacamole
* StatPing - Status Page & Monitoring Server

### MAINTENANCE

* Ouroboros - Automatic Docker Container Updates
* Docker-GC - Automatic Docker Garbage Collection

## IPVanish VPN
Some of the containers are behind VPN for privacy and security. We have been using [IPVanish](https://www.smarthomebeginner.com/go/ipvanish) for a while now. The following apps are behind IPVanish VPN:
* Jackett
* qBittorrent
* Transmission BT
* jDownloader

Based on the docker-compose blocks for the above apps, you can almost any of the apps behind VPN. 

## MariaDB 
Some of the containers in docker-compose.yml (eg. ZoneMinder, Guacamole, phpMyAdmin, etc.) need MariaDB. At this point, an external MariaDB host is specified, with the assumption that you have MariaDB running elsewhere (eg. on your NAS).

At some point, we will add a MariaDB container and use that as the database host. 

# Usage

## Installation
First, install Docker and Docker Compose, as described in our <a href="https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/">Docker Media Server guide</a>. 

1. Clone the repo.
2. Configure `traefik.toml`
  * Rename `traefik\traefik.toml.example` to `traefik\traefik.toml`
  * Edit it to reflect your situation
  * Edit domain name. 
  * DNS Challenge (for LetsEncrypt verification) is enabled by default for cloudflare. Use the [Traefik Reverse Proxy guide](https://www.smarthomebeginner.com/traefik-reverse-proxy-tutorial-for-docker/) for help with this.
  * For other providers other than cloudflare, [check here](https://docs.traefik.io/v2.0/https/acme/#providers).
3. (Optional) Enable or use HTTP Basic Authentication by renaming `shared\.htpasswd.example` to `shared\.htpasswd` in the folder and adding username and hashed password to it. 
4. Configure environmental variables (`.env` file)
  * Rename the included `.env.example` to `.env`.
  * Edit variables in `.env` file. 
  * All variables (ie. `${XXX}`) in docker-compose.yml come from `.env` file stored in the same place as docker-compose.yml. 
  * Ensure good permissions for the `.env` file (recommended: 640).
5. Edit `docker-compose.yml` to include only the services you want or add additional services to it. Be sure to read the comments for each app and create any required files.
6. Start and stop your docker stack as described in our [Docker Media Server guide](https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/).
7. (Optional) Put non-docker apps behind Traefik proxy by renaming `traefik\rules\app.toml.example` to `traefik\rules\app.toml` and editing its contents.

## Starting and Stopping 
I use bash_aliases to simplify starting and stopping containers/stack. Included in the repo is an example of bash_aliases I use (replace USER with your Linux username). Here are some example alias commands:

* <strong>1up</strong> or <strong>2up</strong> - Create network and start Docker Traefik 1 or 2 stack
* <strong>1down</strong> or <strong>2down</strong> - Stop Docker Traefik 1 or 2 stack
* <strong>dcup1</strong> or <strong>dcup2</strong> - Start Docker Traefik 1 or 2 stack
* <strong>dcup1v</strong> or <strong>dcup2v</strong> - Start Docker Trafik 1 or 2 VPN stack
* <strong>dcdown1</strong> or <strong>dcdown2</strong> - Stop Docker Traefik 1 or 2 stack
* <strong>dcdown1v</strong> or <strong>dcdown2v</strong> - Stop Docker Traefik 1 or 2 VPN stack
* <strong>dcrec1</strong> or <strong>dcrec2</strong> - Start or recreate a specific service
* <strong>dcstop1</strong> or <strong>dcstop2</strong> - Stop a specific service
* <strong>dcrestart1</strong> or <strong>dcrestart2</strong> - Restart a specific service
* <strong>dclogs1</strong> or <strong>dclogs1v</strong> or <strong>dclogs2</strong> or <strong>dclogs2v</strong> - See real-time logs for the corresponding stack or service
* <strong>dcpull1</strong> or <strong>dcpull1v</strong> or <strong>dcpull2</strong> or <strong>dcpull2v</strong> - Pull new images for the corresponding stack or service





