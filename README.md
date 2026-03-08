# Home Server

This is a home server config / ops repo. I can optionally add backup and healthcheck scripts, documentation for how to do xyz thing, config files, and more.

## Theory

Before home-rolling any of these services, take a look through the [proxmox helper scripts](https://community-scripts.github.io/ProxmoxVE/). It's more than likely that it has an out-of-the-box method of deployment to a VM or LXC.

## Service Table

| Service                    | ip address | Port  | Websockets Support |
| -------------------------- | ---------- | ----- | ------------------ |
| Proxmox (https)            | subnet:150 | 8006  | true               |
| Jellyfin                   | subnet:151 | 8096  | false              |
| AdGuard Home               | subnet:155 | 80    | false              |
| ?                          | subnet:154 | 25    | false              |
| ?                          | subnet:154 | 80    | false              |
| Nginx Proxy Manager        | subnet:154 | 81    | false              |
| ?                          | subnet:154 | 443   | false              |
| ?                          | subnet:154 | 3001  | false              |
| OpenSpeedTest              | subnet:154 | 4000  | false              |
| OpenSpeedTest              | subnet:154 | 4001  | false              |
| Actual Budget              | subnet:154 | 5006  | false              |
| WorldDB Postgres DB        | subnet:154 | 5432  | false              |
| ?                          | subnet:154 | 7575  | false              |
| ?                          | subnet:154 | 8000  | false              |
| Paperless NGX              | subnet:154 | 8010  | true               |
| Directus CMS               | subnet:154 | 8055  | false              |
| ?                          | subnet:154 | 8384  | false              |
| WorldDB Jupyter Notebook   | subnet:154 | 8800  | true               |
| MeTube                     | subnet:154 | 8888  | false              |
| Miniflux                   | subnet:154 | 9001  | false              |
| Portainer (https)          | subnet:154 | 9443  | false              |
| ?                          | subnet:154 | 22000 | false              |
| Calibre Web                | subnet:154 | ...   | false              |
| Speedtest                  | subnet:154 | ...   | false              |
