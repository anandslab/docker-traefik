###################### THIS CHANGELOG IS NO LONGER MAINTAINED. SEE DETAILED COMMIT LOGS. ##########################

# Changelog

- Only showing high-level changes. Smaller changes are too many to list. See commits.

## Planned (notes for future):
- Scrutiny, Rdiffweb, plex image cleaner, Dockge
- apprise, Apprise api, remmina, Webtop, openvscode-server, 
- Add projectsend, embystat, nextcloud, nut-upsd, HealthChecks, FileRun, fail2ban, ofelia, scrutiny to NUC, Wireguard, traktarr, listrr, Subliminal, netdata, Exportarr, Unpackarr
- Check Cloudbox/cloudbox - plex autoscan, cloudplow, plexdupefinder, plextraktsync
- implement secrets and remove variables from .env
- add prometheus, glances to influxdb, speedtest to influxdb
- Web GUI for rclone
- Switch to Hotio.dev's cloudflareddns,
- Check traefik buffering - to avoid http error 431 - header request size too large
- Implement thelounge, privatebin

## January 23, 2022

- To many changes to list. See detailed commit log.

## October 10, 2021

- Discontinuing this overall changelog due to commits now having a detailed log.
- Updated to Traefik 2.5.x

## January 6, 2021

- Moved server to Proxmox on a dedicated cloud/seedbox.
- Extensive tidying up of the setup.
- Moved all container data to the new "appdata" folder.
- Added Google Drive using rclone and mergerfs.
- Removed Emby. Added Readarr and Tiny Media Manager

## October 15, 2020

- Added Duplicati
- Fixed Cloudflare Companion - secrets not working in 6.3.0

## October 03, 2020

- Upgraded to Traefik 2.3.1.
- Obsoleted Traefik Error Pages
- Fixed TLS Options

## August 20, 2020

- Replaced Ouroboros with Watchtower
- Changed Docker-Socket-Proxy from tecnativa to fluencelabs image - More granularity on permissions

## August 17, 2020

- Moved some of the apps to Synology docker stack (dockerc-compose-t2-synology.yml) - Portainer, MariaDB, InfluxDB, Mosquitto MQTT Broker, Cloudflare DDNS, Redis. Add my NUC stack as a separate endpoint NAS Portainer.
- Implemented Tecnativa Socket Proxy - Traefik, Portainer, Glances, Dozzle, Ouroboros, Docker-GC, Cloudflare Companion
- Moved from Home Assistant Supervised to Home Assistant Core
- Fixed multihost CNAME creation in Cloudflare Companion
- Fully rolled out Docker secrets - Traefik, Authelia, Plex, Guacamole, OAuth, MariaDB, etc.. There are still some images that do not support secrets.
- Renamed docker-compose-synology-t2.yml to docker-compose-t2-synology.yml
- Obsoleted SmokePing
- Obsoleted HA-DockerMon
- Obsoleted UniFi Controller
- Obsoleted Postgres
- Updated Authelia configuration.yml.example
- Obsoleted ZoneMinder. Moved to MotionEye
- Added Traefik Custom Error Pages
- Added SMTP to Telegram

## July 22, 2020

- Implemented socket proxy - Traefik, Portainer, Dozzle, Glances, cf-Companion, Docker-GC, WatchTower. Exception: ha-dockermon.

## July 16, 2020

- Removed USER from docker group to enforce use of sudo for docker commands (improve security)
- Updated bash_aliases
- Partially implemented Docker secrets
- passHostHeader is true by default. Removed from rules.
- Moved from toml to yml. Included examples for both in repo.
- Added \$SECRETSDIR env variable
- Expanded bash_aliases

## July 14, 2020

- Added Synology Docker Compose for Traefik 2
- Introduced new environmental variable \$DOCKERDIR for simplicity

## June 25, 2020

- Updated Authelia volumes to reflect the current structure
- Cleaned up LazyLibrarian, Calibre, and Caliber-web
- Bug fixes and typos
- Added /dev/dri volumes to support hardware transcoding in Plex, Emby, and Jellyfin

## June 12, 2020

- Added Home Assistant Core
- Added Redis and Redis Commander
- Enabled Authelia to use Redis
- Added LazyLibrarian, Calibre, and Caliber-web

## May 31, 2020

- Removed tls=true from service since tls.certresolver=dns-cloudflare auto enables TLS
- Enabled Cloudflare proxy
- Added Cloudflare Companion to auto create CNAMEs for services
- Replaces Cloudflare DDNS with Oznu's image

## May 19, 2020

- Removed Jackett from VPN
- Removed qBittorrent
- Added Home Assistant Core to Obsolete as a backup (due to recent developments with Home Assistant)

## May 18, 2020

- Switched default auth from OAuth to Authelia
- Added default certresolver and TLS options and removed these from all services
- Added VSCode, Motion Eye
- Obsoleted Cloud Commander, CloudlIDE, Linuxserver VSCode
- Set exposedByDefault to True so Traefik is enabled by default for all services

## May 11, 2020

- Added Authelia Lite multifactor authentication

## April 25, 2020

- Added Traefik Certificate Dumper, Cloudflare DDNS

## April 19, 2020

- Switched to Traefik 2.2 as default

## March 31, 2020

- Added Ombi, PhotoShow
- Moved Traefik-Home, MQTT Admin, xTeVe, Piwigo, MiFlora Daemon, xTeVe, Logarr to Obsolete list

## January 14, 2020

- Added dozzle, smokeping, Traefik-Home, and VSCode Server - Thanks github.com/thefrenchmatt

## January 9, 2020

- Replace TellyTV with xTeve
- Re-added Emby for Testing

## January 7, 2020

- Added MiFlora MQTT Daemon to monitor plant status, AirSonic, and MariaDB
- Obsoleted Varken

## January 6, 2020

- Switched radarr and sonarr to "preview" tag to use the new low resource UI.
- Renamed Traefik 1 folder from "traefik" to "traefik1"

## December 16, 2019

- Significant changes - too many to list
- Included first draft of Traefik 2.1 setup
- Included a draft of Traefik 1 in Docker Swarm mode
- Removed monitorr (use statping instead)

## November 22, 2019

- Replaced Emby with Jellyfin
- Added Postgres database for StatPing

## November 21, 2019

- Added Autoindex
- Addded TellyTV for IPTV proxy for plex
- Added StatPing with Grafana Dashboard - not working yet
- Separated VPN apps into different compose file
- Removed IPVanish container and put vpn apps behind Transmission-VPN's network

## November 8, 2019

- Harmonized paths and removed unused volumes
- Moved Plex and Emby transcoding to /dev/shm (RAM)

## November 7, 2019

- Added IPVanish VPN container.
- Added VPN support for Jackett, qBittorrent, and jDownloader.
- Initial push to GitHub

## November 6, 2019

- Moved environmental variables to .env file

## November 4, 2019

- Added plex-sync to sync two plex servers.
- Added MakeMKV.

## October 28, 2019

- Added Plex, MKVToolNix, QDirStat

## October 24, 2019

- Added Picard, Handbrake, and Filebot

## Oct 14, 2019

- Implemented Google OAuth

## Oct 11, 2019

- Added Firefox, Glances, jDownloader, Logarr, Monitorr, and apcupsd
- Replaced watchtower with Ouroboros

## Oct 4, 2019

- Added Heimdall

## Sep 17, 2019

- Fixed traefik v1.7.16
- Added organizr
- Fixed traefik labels
- Switched to hydra2.
- Removed Heimdall.
- Cleaned up docker compose.

## Aug 20, 2019

- Removed Unifi (moved to VPS).
- Switched back to linuxserver for sonarr and radarr.

## Feb 25, 2019

- Moved to NUC.

## Feb 8, 2019

- Added jlesage/handbrake
- Switched from linuxserver/sonarr to aront/sonarr, linuxserver/radarr to aront/radarr for mp4_automator support

## Feb 5, 2019

- Removed Plexms, Nodered, Hole, Syncthing
