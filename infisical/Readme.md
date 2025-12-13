````markdown
# Infisical (Local Docker)

This directory contains the Docker Compose configuration for running an Infisical instance as part of the Open-Suite collection of services.

## Overview

Infisical provides secrets management and environment synchronization for applications. The `compose.yml` in this folder configures the service and any required sidecars/volumes.

## Prerequisites

- Docker and Docker Compose (v2+) installed.
- Sufficient ports free on the host (check `compose.yml`).

## Setup

1. Inspect `compose.yml` to see environment variable references and port mappings.
2. Create an environment file if required. The project does not ship a `template.env` for Infisical by default, so create a `.env` in this folder if the compose file expects variables:

```bash
cd infisical/
# create .env from scratch or from another example
touch .env
```

3. Fill in any environment variables referenced by the Compose file (for example, database credentials, hostnames, or root keys).

## Starting

From the `infisical/` directory, build and start the service in detached mode:

```bash
cd infisical/
docker compose up --build -d
```

To view logs:

```bash
docker compose logs -f
```

## Stopping

To stop the service:

```bash
docker compose down
```

To stop and remove volumes (clean data):

```bash
docker compose down -v
```

## Notes

- If you need persistent storage, confirm volumes in `compose.yml` are configured and mapped correctly.
- Check the compose file for any external dependencies (databases, message brokers) that may need to be started first.

If you want, I can extract required env var names from `compose.yml` and create a `env.local.example` for this folder — tell me to proceed.
````
