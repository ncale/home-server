# Home Server

This is a home server config / ops repo. I can optionally add backup and healthcheck scripts, documentation for how to do xyz thing, config files, and more.

## Theory

Before home-rolling any of these services, take a look through the [proxmox helper scripts](https://community-scripts.github.io/ProxmoxVE/). It's more than likely that it has an out-of-the-box method of deployment to a VM or LXC.

## Service <> Port Map

| Service                    | Port  |
| -------------------------- | ----- |
| ?                          | 25    |
| ?                          | 80    |
| Nginx Proxy Manager        | 81    |
| ?                          | 443   |
| ?                          | 3001  |
| WorldDB Metabase Dashboard | 3100  |
| ?                          | 4000  |
| ?                          | 4001  |
| Actual Budget              | 5006  |
| WorldDB Postgres DB        | 5432  |
| ?                          | 7575  |
| ?                          | 8000  |
| Paperless NGX              | 8010  |
| Directus CMS               | 8055  |
| ?                          | 8384  |
| WorldDB Jupyter Notebook   | 8800  |
| MeTube                     | 8888  |
| Miniflux                   | 9001  |
| ?                          | 9443  |
| ?                          | 22000 |
| Calibre Web                | ...   |
| Speedtest                  | ...   |
