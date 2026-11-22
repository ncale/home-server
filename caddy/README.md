# Caddy LXC

Initialized from the [community-script](https://community-scripts.org/scripts/caddy).

## Deployment steps

1. Clone caddy config to the LXC.

```shell
cd /opt
git clone <this-repo>
ln -sf /opt/<this-repo>/caddy/Caddyfile /etc/caddy/Caddyfile
```

2. Start the server (environment variables have to be exported in the shell).

```shell
export CF_API_TOKEN=...
export DOMAIN=...
caddy start --config /etc/caddy/Caddyfile
```
