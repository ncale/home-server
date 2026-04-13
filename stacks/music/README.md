# Music

Navidrome streams music. Beets tags and organizes it.

Set `MUSIC_DIR` in `.env` to your music library path before starting.

## Beets

Run beets commands against the library:

```sh
docker compose exec beets beet <command>
```

Common commands: `beet import /music/new-album`, `beet update`, `beet ls`.

The web UI at `BEETS_PORT` provides search and browsing. The config file is at `/config/config.yaml` inside the container (persisted in the `beets-config` volume).
