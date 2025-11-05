# n8n Docker

This project provides a Docker-based setup for self-hosting [n8n](https://n8n.io/), a powerful workflow automation tool.

## What is n8n?

n8n is a free and open-source workflow automation tool that allows you to connect different applications and services to automate tasks. It provides a visual workflow editor to create complex automations without writing any code.

![n8n UI](https://n8niostorageaccount.blob.core.windows.net/n8nio-strapi-blobs-prod/assets/Home_ITO_Ps_5a5aac3fda.webp)

## Getting Started

This setup uses Docker Compose to orchestrate the necessary services. To get started, you will need to configure your environment variables.

### Environment Variables

Environment variables are used to configure the n8n instance. You can use one of the provided templates to create your own `.env` file.

#### `template.env`

This file is a template that shows all the available environment variables. Copy this file to `.env` and fill in the values for your setup. This is useful when you want to configure everything from scratch.

```bash
cp template.env .env
```

#### `env.local.example`

This file provides an example configuration for local testing. It is pre-configured to use `n8n.localhost` for the UI. To use it, you only need to configure a few variables. Copy it to `.env`:

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

3.  Once the services are running, you can access the n8n UI in your browser at the domain you configured.

## Further Documentation

For more detailed information on configuring and running n8n with Docker, please refer to the official documentation:

[https://docs.n8n.io/hosting/installation/docker/](https://docs.n8n.io/hosting/installation/docker/)