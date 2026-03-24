# Directus CMS

Deploys a Directus instance backed by SQLite.

## Deploy

1. Copy `.env.example` to `.env` and fill in the required values
2. Create the data directories and set permissions, replacing `DATA_PATH` with your actual path:

```shell
mkdir -p /DATA_PATH/database
mkdir -p /DATA_PATH/uploads
mkdir -p /DATA_PATH/extensions
chmod -R 777 /DATA_PATH
```

3. Deploy via Portainer using the repository method

## Notes

- `DATA_PATH` must be unique per instance if running multiple deployments
- Generate `SECRET` with `openssl rand -base64 32`
