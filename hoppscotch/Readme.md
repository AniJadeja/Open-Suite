# Hoppscotch Docker

This project provides a Docker-based setup for self-hosting the [Hoppscotch](https://hoppscotch.io/) API development ecosystem.

## What is Hoppscotch?

Hoppscotch is a lightweight, open-source API development and testing tool. It provides a beautiful and easy-to-use interface for interacting with REST, GraphQL, and Realtime APIs.

![Hoppscotch UI](https://hoppscotch.com/images/hero-screenshot.png)

## Getting Started

This setup uses Docker Compose to orchestrate the necessary services. To get started, you will need to configure your environment variables.

### Environment Variables

Environment variables are used to configure the Hoppscotch instance. You can use one of the provided templates to create your own `.env` file.

#### `template.env`

This file is a template that shows all the available environment variables. Copy this file to `.env` and fill in the values for your setup.

```bash
cp template.env .env
```

#### `env.local.example`

This file provides an example configuration for local testing. It is pre-configured to use `hopp-ui.localhost` for the UI and `hopp-api.localhost` for the API. To use it, copy it to `.env`:

```bash
cp env-examples/env.local.example .env
```

#### `env.prod.example`

This file is intended for production setups. It uses placeholders like `<your-domain>` that you should replace with your actual domain names. To use it, copy it to `.env` and replace the placeholders:

```bash
cp env-examples/env.prod.example .env
```

## Quick Start

1.  Create your `.env` file using one of the methods described above.
2.  Run the following command to start the services:

    ```bash
    docker compose up --build -d
    ```

3.  Once the services are running, you can access the Hoppscotch UI in your browser at the domain you configured.

## Further Documentation

For more detailed information on configuring and running Hoppscotch with Docker, please refer to the official documentation:

[https://docs.hoppscotch.io/self-host/docker](https://docs.hoppscotch.io/self-host/docker)
