# Caddy LXC

Initialized this from the community-script

## Deployment steps

1. Copy the caddy config over to the LXC.

```shell
cd /opt
git clone <this-repo>
ln -sf /opt/<this-repo>/caddy/Caddyfile /etc/caddy/Caddyfile
```

2. Export your environment variables as needed.
3. Start the server.

```shell
caddy start --config /etc/caddy/Caddyfile
```
