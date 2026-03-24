# Deploying Stacks via Portainer

Docker Compose files for services deployed via Portainer on the `docker` LXC.

## How It Works

Services are deployed as Portainer stacks. Each stack has its own dir containing a `docker-compose.yml` file. To deploy, point Portainer at the file using the "Repository" method and select the path to the compose file (e.g. `stacks/miniflux/docker-compose.yml`).

Copy the `.env.example` file (if it exists) and navigate to the environment variables section in Portainer. Select "Advanced Mode". This allows you to paste the `.env` in a text editor rather than editing the variables one by one.

## Services

See subdirectories for available stacks. Each contains a `docker-compose.yml`
and an `.env.example` if environment variables are required.
