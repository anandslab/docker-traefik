# INSTRUCTIONS
# All variables ${XXX} come from .env file stored in the same place as docker-compose.yml. Restrict permissions to .env file (recommended: 640)

########################### NETWORKS
########################### SERVICES
############################# FRONTENDS
# Traefik - Reverse Proxy
# OAuth - Forward Authentication
# Portainer - Container Management
# Organizr - Unified Frontend
# Heimdall - Unified Frontend Alternative
############################# SMART HOME
# HA-Dockermon - Manage Docker containers in Home Assistant 
# Mosquitto - MQTT Broker
# ZoneMinder - Video Surveillance 
############################# DATABASE
# phpMyAdmin - Database management
# InfluxDB - Database for sensor data
# Grafana - Graphical data visualization for InfluxDB data
############################# INDEXERS
# Jackett - Torrent proxy
# NZBHydra2 - NZB meta search
############################# PVRS
# Lidarr - Music Management
# Radarr - Movie management
# Sonarr - TV Shows management
############################# DOWNLOADERS
# jDownloader - Download management
# SABnzbd - Binary newsgrabber (NZB downloader)
# qBittorrent - Torrent downloader
# TransmissionBT - Torrent Downloader
############################# MEDIA SERVER
# Plex - Media Server
# Emby - Media Server
# Tautulli - Previously PlexPy. Plex statistics and monitoring
# Plex-Sync - For Syncing watched status between plex servers 
############################# MEDIA FILE MANAGEMENT
# Bazarr - Subtitle Management
# Picard - Music Library Tagging and Management
# Handbrake - Video Conversion (Transcoding and compression)
# MKVToolNix - Video Editing (Remuxing - changing media container while keeping original source quality)
# MakeMKV - Video Editing (Ripping from Disks)
# FileBot - File renamer
############################# SYSTEM
# Firefox - Web Broswer
# Glances - System Information
# Logarr - Log Management
# Monitorr - Webfront to display the status of any webapp or service
# APCUPSD - APC UPS Management
# qDirStat - Directory Statistics
# Guacamole - Remote desktop, SSH, on Telnet on any HTML5 Browser 
# Guacamole Daemon - Needed for Guacamole
# IPVanish - VPN for container traffic
############################# MAINTENANCE
# Ouroboros - Automatic Docker Container Updates
# Docker-GC - Automatic Docker Garbage Collection 