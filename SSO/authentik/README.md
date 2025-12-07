# Authentik Self-Hosted Setup

This directory contains the Docker Compose configuration for running a self-hosted instance of [Authentik](https://goauthentik.io/).

## Components

The setup includes the following services:
- **Server**: The main Authentik application server.
- **Worker**: Background worker for processing tasks.
- **PostgreSQL**: Database for storing application data.
- **Redis**: In-memory data store for caching and session management.

## Prerequisites

- Docker
- Docker Compose

## Getting Started

1. **Environment Configuration**:
   Copy the example environment file to `.env`:
   ```bash
   cp .env.example .env
   ```

2. **Secure Secrets**:
   Edit the `.env` file and set strong values for the following variables:
   - `PG_PASS`: Password for the PostgreSQL database.
   - `AUTHENTIK_SECRET_KEY`: Secret key for Authentik.
   - `AUTHENTIK_EMAIL__PASSWORD`: Password for the SMTP user (if enabling email).

   You can generate a secret key using `openssl rand -base64 32`.

3. **Start the Services**:
   Run the following command to start the stack:
   ```bash
   docker compose up -d
   ```

4. **Access Authentik**:
   Once the services are running, Authentik will be accessible at:
   - HTTP: `http://localhost:9000`
   - HTTPS: `https://localhost:9443`

   (Ports can be configured in `compose.yml` or via environment variables `COMPOSE_PORT_HTTP`/`COMPOSE_PORT_HTTPS`).

## Directory Structure

- `certs/`: Store custom SSL/TLS certificates here.
- `custom-templates/`: Override default HTML templates for customization.
- `media/`: Persists user uploads (avatars, icons) and application assets. **Do not delete.**

## Initial Setup

Upon the first launch, navigate to `http://localhost:9000/if/flow/initial-setup/` to create the initial admin user configuration if it doesn't redirect you automatically.
