<h2>Description</h2>
This is the updated docker-compose repo of all the media and home server apps described in the following guides on our website:

<p>
<ul>
  <li>Docker Media Server - https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/</li>
<li>Traefik Reverse Proxy - https://www.smarthomebeginner.com/traefik-reverse-proxy-tutorial-for-docker/</li>
<li>Docker with Google OAuth2 - https://www.smarthomebeginner.com/google-oauth-with-traefik-docker/</li>
</ul>
</p>

<h3>But what about Traefik 2.0?</h3>
<p>At this point this stack is built on Traefik 1.0. As we move ours to Traefik 2.0, we will publish a new repository. </p>

<p>Having said that, Traefik 1.7.16 (the final release in v1) still works great for the purposes of a media / home server stack. Traefik 2.0 is significantly different requiring a major rework of your files. Therefore, if you are already on Traefik v1, we do not see a need to upgrade to v2 at this point. </p>

<p>If you are starting out, you may start with Traefik 2.0. However, documentation, community knowledge, and support for Traefik 2.0 is still quite limited at this time.</p>

<h2>What apps are included in this stack?</h2>
We will try to keep this repo up-to-date. Here are the apps currently included in our stack:

<h3>FRONTENDS</h3>
<ul>
<li>Traefik - Reverse Proxy</li>
<li>OAuth - Forward Authentication</li>
<li>Portainer - Container Management</li>
<li>Organizr - Unified Frontend</li>
<li>Heimdall - Unified Frontend Alternative</li>
</ul>

<h3>SMART HOME</h3>
<ul>
<li>HA-Dockermon - Manage Docker containers in Home Assistant </li>
<li>Mosquitto - MQTT Broker</li>
<li>ZoneMinder - Video Surveillance </li>
</ul>

<h3>DATABASE</h3>
<ul>
<li>phpMyAdmin - Database management</li>
<li>InfluxDB - Database for sensor data</li>
<li>Grafana - Graphical data visualization for InfluxDB data</li>
</ul>

<h3>INDEXERS</h3>
<ul>
<li>Jackett - Torrent proxy</li>
<li>NZBHydra2 - NZB meta search</li>
</ul>

<h3>PVRS</h3>
<ul>
<li>Lidarr - Music Management</li>
<li>Radarr - Movie management</li>
<li>Sonarr - TV Shows management</li>
</ul>

<h3>DOWNLOADERS</h3>
<ul>
<li>jDownloader - Download management</li>
<li>SABnzbd - Binary newsgrabber (NZB downloader)</li>
<li>qBittorrent - Torrent downloader</li>
<li>TransmissionBT - Torrent Downloader</li>
</ul>

<h3>MEDIA SERVER</h3>
<ul>
<li>Plex - Media Server</li>
<li>Emby - Media Server</li>
<li>Tautulli - Previously PlexPy. Plex statistics and monitoring</li>
<li>Plex-Sync - For Syncing watched status between plex servers </li>
</ul>

<h3>MEDIA FILE MANAGEMENT</h3>
<ul>
<li>Bazarr - Subtitle Management</li>
<li>Picard - Music Library Tagging and Management</li>
<li>Handbrake - Video Conversion (Transcoding and compression)</li>
<li>MKVToolNix - Video Editing (Remuxing - changing media container while keeping original source quality)</li>
<li>MakeMKV - Video Editing (Ripping from Disks)</li>
<li>FileBot - File renamer</li>
</ul>

<h3>SYSTEM</h3>
<ul>
<li>Firefox - Web Broswer
<li>Glances - System Information</li>
<li>Logarr - Log Management</li>
<li>Monitorr - Webfront to display the status of any webapp or service</li>
<li>APCUPSD - APC UPS Management</li>
<li>qDirStat - Directory Statistics</li>
<li>Guacamole - Remote desktop, SSH, on Telnet on any HTML5 Browser </li>
<li>Guacamole Daemon - Needed for Guacamole</li>
<li>IPVanish - VPN for container traffic</li>
</ul>

<h3>MAINTENANCE</h3>
<ul>
<li>Ouroboros - Automatic Docker Container Updates</li>
<li>Docker-GC - Automatic Docker Garbage Collection</li>
</ul>

<h2>Usage</h2>
All variables (ie. ${XXX}) in docker-compose.yml come from .env file stored in the same place as docker-compose.yml. Restrict permissions to .env file (recommended: 640)

An example .env file is included in the repo. You may rename it from .env.exmaple to .env, edit the variables to your situation before starting the containers. 
