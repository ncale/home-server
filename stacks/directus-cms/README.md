# Directus CMS

This is a simple deploy.

```.env
# Can be left empty
PORT=8055
DATA_PATH=/root/directus
# Required
SECRET=
DB_CLIENT="sqlite3"
DB_FILENAME="/directus/database/data.db"
```

- PORT: this will default to 8055, but can be overridden.
- DATA_PATH: this is the path of the volumes in the host machine. You have to change this if you want to run multiple instances with the same docker compose file.
- SECRET: run `openssl rand -base64 32` or generate with bitwarden.
- DB_CLIENT: leave this alone.
- DB_FILENAME: leave this alone.

\*\* To note: if you're deploying fresh, you may need to make sure the DATA_PATH dir exists and the user has permissions to edit:

```shell
mkdir -p /root/directus-challenger/database
mkdir -p /root/directus-challenger/uploads
mkdir -p /root/directus-challenger/extensions
chmod -R 777 /root/directus-challenger
```
