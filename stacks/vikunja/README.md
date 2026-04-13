# Vikunja

Ref: <https://vikunja.io/docs/full-docker-example/#sqlite>

## First boot

```bash
# 1. Generate a JWT secret and set it in `.env`
openssl rand -hex 32

# 2. Set `VIKUNJA_URL` to the public-facing URL — must have a trailing slash (e.g. `https://vikunja.home/`)

# 3. Start
docker compose up -d

# 4. Open the UI and create your admin account on first load.
```

## Maintenance

**Backup:** Files are in `vikunja-files`, the SQLite database is in `vikunja-db` (at `/db/vikunja.db`). Back up both volumes.

```sh
docker run --rm -v vikunja_vikunja-files:/files -v vikunja_vikunja-db:/db -v $(pwd):/backup alpine \
  tar czf /backup/vikunja-backup.tar.gz -C / files db
```

**Upgrade:** `docker compose pull && docker compose up -d`
