# FusionAuth Self-Hosted Setup

This directory contains the Docker Compose configuration for running [FusionAuth](https://fusionauth.io/) locally with PostgreSQL and OpenSearch.

## Components

The stack consists of:
- **FusionAuth App**: The core identity management platform.
- **PostgreSQL**: Relational database for user data and configuration.
- **OpenSearch**: Search engine for powering user search and reporting (alternative to Elasticsearch).

## Prerequisites

- Docker
- Docker Compose

## Getting Started

1. **Environment Configuration**:
   Copy the example environment file to `.env` (if not using the defaults directly, though `.env.example` suggests variables to set):
   ```bash
   cp .env.example .env
   ```
   
   Ensure you set secure passwords for:
   - `POSTGRES_PASSWORD`
   - `DATABASE_PASSWORD`

2. **Start the Services**:
   Run the stack:
   ```bash
   docker compose up -d
   ```

3. **Access FusionAuth**:
   The FusionAuth admin interface will be available at:
   - `http://localhost:9011`

## Configuration Notes

- **Memory**: The configuration is tuned for development with `OPENSEARCH_JAVA_OPTS` set to 512MB heap and `FUSIONAUTH_APP_MEMORY` set to 512MB. Adjust these in `compose.yml` for production use.
- **OpenSearch**: Security features are disabled (`OPENSEARCH_SECURITY_DISABLED=true`) to simplify local deployment.
- **Database**: Uses `postgres:16-alpine`.

## Troubleshooting

If OpenSearch fails to start, ensure your host system's `vm.max_map_count` is set correctly (common requirement for Elasticsearch/OpenSearch):
```bash
sudo sysctl -w vm.max_map_count=262144
```
