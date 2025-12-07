# ZITADEL Self-Hosted Setup

This directory contains the Docker Compose configuration for running [ZITADEL](https://zitadel.com/) self-hosted.

## Components

- **ZITADEL**: The main IAM service (API and Core).
- **ZITADEL Login**: The separate login user interface (Login V2).
- **PostgreSQL**: Database for ZITADEL.

## Prerequisites

- Docker
- Docker Compose

## Getting Started

1. **Personal Access Token (PAT)**:
   The configuration references a PAT file at `./login-client.pat`. Ensure this file exists and contains a valid token if you are connecting an existing instance, or it will be used for the initial setup as configured. 
   
   *Note: The `compose.yaml` is configured to initialize a machine user `login-client`.*

2. **Start the Services**:
   Run the following command:
   ```bash
   docker compose up -d
   ```

3. **Access ZITADEL**:
   - **Console/API**: `http://localhost:8080`
   - **Login UI**: `http://localhost:3000`

## Default Credentials

The `compose.yaml` configures the initial instance with the following admin credentials:
- **Username**: `root`
- **Password**: `RootPassword1!`
- **Organization**: `My Organization`

## Configuration Details

- **External Domain**: Configured as `localhost`.
- **TLS**: Disabled (`ZITADEL_TLS_ENABLED: false`) for local development.
- **Login V2**: Enabled and pointing to the local `zitadel-login` service on port 3000.
- **Database**: Connects to the `db` service (Postgres 17).

## Notes

- The main ZITADEL container is running with the command `start-from-init`, which initializes the database and starts the service.
- The `login` service mounts the current directory as read-only.
