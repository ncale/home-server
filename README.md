# Home Server

This is a home server config / ops repo. I can optionally add backup and healthcheck scripts, documentation for how to do xyz thing, config files, and more.

## Theory

Before home-rolling any of these services, take a look through the [proxmox helper scripts](https://community-scripts.github.io/ProxmoxVE/). It's more than likely that it has an out-of-the-box method of deployment to a VM or LXC.

## Service <> Port Map

| Service             | Port |
| ------------------- | ---- |
| Nginx Proxy Manager | 81   |
| Miniflux            | 9001 |
| Actual Budget       | 5006 |
| Calibre Web         | ...  |
| Speedtest           | ...  |
