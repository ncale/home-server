# Vikunja

## First boot

```bash
# 1. Generate a JWT secret and set it in `.env`
openssl rand -hex 32

# 2. Set `VIKUNJA_URL` to the public-facing URL (e.g. `https://vikunja.home`). Used for redirect links and sharing.

# 3. Start
docker compose up -d

# 4. Open the UI and create your admin account on first load.
```

## Maintenance

**Backup:** The SQLite database and all file attachments are in the `vikunja-data` volume at `/app/vikunja/files/`. Back up that directory.

```sh
docker run --rm -v vikunja_vikunja-data:/data -v $(pwd):/backup alpine \
  tar czf /backup/vikunja-backup.tar.gz -C /data .
```

**Upgrade:** `docker compose pull && docker compose up -d`
