# Proxmox Setup

## Overview

Single-node home server running Proxmox VE 9.1.4 on a [GMKtec NucBox G3 Plus Mini PC](https://www.gmktec.com/products/nucbox-g3-plus-enhanced-performance-mini-pc-with-intel-n150-processor?variant=ac9b8b20-ab4a-4fc3-bea1-40356b114c17). Built to self-host media, maintain private storage, provide local network services, and spin up isolated VMs and LXCs for dev work and small projects.

## Container/VM Layout

| Container        | Type | OS                     | Purpose                                |
| ---------------- | ---- | ---------------------- | -------------------------------------- |
| adguard          | LXC  | Debian 13              | DNS / ad blocking                      |
| jellyfin         | LXC  | Debian 13              | Media server                           |
| docker           | LXC  | Debian 13              | Runs all Docker services via Portainer |
| vm-ubuntu-server | VM   | Ubuntu 24.04           | General purpose                        |
| haos             | VM   | Home Assistant OS 16.3 | Home automation                        |

## Network

IPs are assigned via DHCP reservation on the router by MAC address, starting at 192.168.0.150.

**DNS & Routing**

- AdGuard Home is the local DNS server for the network
- Local subdomains (e.g. `jellyfin.home.example.com`) are resolved via DNS rewrites in AdGuard pointing to Nginx Proxy Manager
- Nginx Proxy Manager handles routing to individual services and SSL termination
- SSL certificates issued by Let's Encrypt via Cloudflare DNS challenge

**Remote Access**

- Tailscale subnet router runs on the Proxmox host, exposing the full home network (192.168.0.0/24) to connected devices
- Split DNS configured in Tailscale: local subdomains (e.g. `*.home.example.com`) route to AdGuard Home as the nameserver
- This allows local domains to resolve correctly over Tailscale without exposing any services publicly

## Notes

- iGPU passthrough configured on the Jellyfin LXC for hardware transcoding
- Must enable "nesting" feature in priviledged LXCs running Debian 13 to get console access in proxmox UI; Unsure why; This also does not seem to be an issue for other distributions like Ubuntu.
- Must enable "keyctl" feature in unpriviledged LXCs running Debian 13 to get docker to run.
