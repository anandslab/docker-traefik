# Description
This is the updated docker-compose repo of all the media and home server apps described in the following guides on our website:

* Docker Media Server with Traefik 2 Reverse Proxy: [https://www.smarthomebeginner.com/traefik-2-docker-tutorial/](https://www.smarthomebeginner.com/traefik-2-docker-tutorial/)

<STRONG>Old Posts:</STRONG>
The following 3 posts have been combined and updated for Traefik v2 (linked above):
* Docker Media Server without Reverse Proxy (- [https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/](https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/)
* Docker Media Server with Traefik 1 Reverse Proxy - [https://www.smarthomebeginner.com/traefik-reverse-proxy-tutorial-for-docker/](https://www.smarthomebeginner.com/traefik-reverse-proxy-tutorial-for-docker/)
* Docker with Google OAuth 2 - [https://www.smarthomebeginner.com/google-oauth-with-traefik-docker/](https://www.smarthomebeginner.com/google-oauth-with-traefik-docker/)

## A Note on Traefik 1 vs Traefik 2?
<strong>Update (April 19, 2020):</strong> We have switched from Traefik v1 to Traefik v2, which is now our default. Therefore, the setup for Traefik v1 will only receive minor security related updates (if any). If you are new, follow instructions for Traefik v2.

### Traefik 2 (ACTIVE)
* docker-compose-t2.yml
* docker-compose-t2-vpn.yml
* docker-compose-t2-obsolete.yml (Apps that we do not use anymore)
 
### Traefik 1 (NOT ACTIVELY MAINTAINED)
* docker-compose-t1.yml
* docker-compose-t1-vpn.yml
* docker-compose-t1-obsolete.yml (Apps that we do not use anymore)

### Traefik 1 - Docker Swarm Mode (NOT ACTIVELY MAINTAINED)
* docker-compose-t1-swarm.yml

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
* MiFlora - MiFlora MQTT Daemon (MiFlora Plant Sensors) (OBSOLETE)

### DATABASE

* MariaDB - MySQL Database
* phpMyAdmin - Database management
* InfluxDB - Database for sensor data
* Postgres - Database
* Grafana - Graphical data visualization for InfluxDB data
* Varken - Monitor Plex, Sonarr, Radarr, and Other Data (OBSOLETE)

### DOWNLOADERS

* jDownloader - Download management
* TransmissionBT with VPN - Torrent Downloader
* SABnzbd - Binary newsgrabber (NZB downloader)
* qBittorrent with VPN - Torrent downloader

### INDEXERS

* NZBHydra2 - NZB meta search
* Jackett - Torrent proxy

### PVRS

* Lidarr - Music Management
* Radarr - Movie management
* Sonarr - TV Shows management

### MEDIA SERVER

* AirSonic - Music Server
* Plex - Media Server
* Emby - Media Server
* Jellyfin - Media Server
* Ombi - Media Requests
* Tautulli - Previously PlexPy. Plex statistics and monitoring
* Plex-Sync - For Syncing watched status between plex servers 
* PhotoShow - Personal Photo Gallery and viewer
* TellyTv- IPTV proxy for Plex (OBSOLETE)
* xTeve- IPTV proxy for Plex (OBSOLETE)

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
* APCUPSD - APC UPS Management
* Logarr - Log Management (OBSOLETE)
* Monitorr - Webfront to display the status of any webapp or service (OBSOLETE)
* Guacamole - Remote desktop, SSH, on Telnet on any HTML5 Browser 
* Guacamole Daemon - Needed for Guacamole
* Dozzle - Docker logs viewer
* qDirStat - Directory Statistics
* VS Code Server - Code Editor
* StatPing - Status Page & Monitoring Server
* SmokePing - Network Latency Monitoring

### MAINTENANCE

* Ouroboros - Automatic Docker Container Updates
* Docker-GC - Automatic Docker Garbage Collection
* Traefik Certificate Dumper - Extract Traefik SSL Certs
* Cloudflare DDNS - Dynamic IP Updater

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

* <strong>dc1up</strong> or <strong>dc2up</strong> - Create network and start Docker Traefik 1 or 2 stack
* <strong>dc1down</strong> or <strong>dc2down</strong> - Stop Docker Traefik 1 or 2 stack
* <strong>dcup1</strong> or <strong>dcup2</strong> - Start Docker Traefik 1 or 2 stack
* <strong>dcup1v</strong> or <strong>dcup2v</strong> - Start Docker Trafik 1 or 2 VPN stack
* <strong>dcdown1</strong> or <strong>dcdown2</strong> - Stop Docker Traefik 1 or 2 stack
* <strong>dcdown1v</strong> or <strong>dcdown2v</strong> - Stop Docker Traefik 1 or 2 VPN stack
* <strong>dcrec1</strong> or <strong>dcrec2</strong> - Start or recreate a specific service
* <strong>dcstop1</strong> or <strong>dcstop2</strong> - Stop a specific service
* <strong>dcrestart1</strong> or <strong>dcrestart2</strong> - Restart a specific service
* <strong>dclogs1</strong> or <strong>dclogs1v</strong> or <strong>dclogs2</strong> or <strong>dclogs2v</strong> - See real-time logs for the corresponding stack or service
* <strong>dcpull1</strong> or <strong>dcpull1v</strong> or <strong>dcpull2</strong> or <strong>dcpull2v</strong> - Pull new images for the corresponding stack or service

## Did this Repo help you?

Please consider buying us a coffee (or two) as a token of appreciation.

<a href="https://www.buymeacoffee.com/smarthomebeginr" target="_blank" rel="nofollow noopener noreferrer"><img src="https://www.smarthomebeginner.com/images/2020/04/coffee.png" alt="" width="340" height="77" class="aligncenter size-full wp-image-41005" /></a>