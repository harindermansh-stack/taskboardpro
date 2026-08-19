# TaskBoard Pro Setup Guide

This guide describes the setup paths verified from the included source and upstream Focalboard documentation. Commands may need adjustment for your operating system and infrastructure.

## Requirements

- Docker for the container-based setup path.
- Docker Compose if using the compose files under `docker/`.
- A server or workstation capable of running the application and storing its data volume.

## Docker image setup

From the package source directory:

```powershell
docker build -f docker/Dockerfile -t taskboard-pro .
docker run -it -v "taskboardpro-data:/opt/focalboard/data" -p 80:8000 taskboard-pro
```

Then open `http://localhost` or the mapped host/port in your browser.

## Docker Compose setup

The source includes Docker Compose examples in the `docker/` directory. From that directory, review the compose file you intend to use and run the matching compose command, for example:

```powershell
docker compose up
```

or, for the database and nginx example:

```powershell
docker compose -f docker-compose-db-nginx.yml up
```

## Production notes

- Configure storage, backups, reverse proxying, TLS and access controls for your environment.
- Review upstream Focalboard documentation before exposing the service publicly.
- This package does not include a managed hosting configuration or production deployment warranty.

## Not verified

- One-click cloud deployment.
- Automatic migration from other tools.
- Built-in time tracking.
- Guaranteed compatibility with every Docker host.
