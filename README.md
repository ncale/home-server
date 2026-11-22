# Home Server

Single-node Proxmox VE 9.1.4 server running on a [GMKtec NucBox G3 Plus Mini PC](https://www.gmktec.com/products/nucbox-g3-plus-enhanced-performance-mini-pc-with-intel-n150-processor?variant=ac9b8b20-ab4a-4fc3-bea1-40356b114c17). Hosts media, file storage, and local network services.

## Remote Access

- Tailscale subnet router runs on the Proxmox host, exposing the full home network (192.168.0.0/24) to connected devices.
- Split DNS configured in Tailscale: specified subdomains (e.g. `home.example.com`) route to AdGuard Home as the nameserver.
- This allows local domains to resolve correctly over Tailscale.

## Notes

- iGPU passthrough configured on the Jellyfin LXC for hardware transcoding
- Must enable "nesting" in priviledged LXCs running Debian 13 to get console access in proxmox UI; Unsure why; This also does not seem to be an issue for other distributions like Ubuntu.
- Must enable "keyctl" in unpriviledged LXCs for docker.
