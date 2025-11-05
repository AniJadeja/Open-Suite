# Open-Suite Docker Project

This repository contains a multi-service Docker application designed to provide a comprehensive development and automation environment. It integrates two key tools:

*   **Hoppscotch:** An open-source API development and testing tool.
*   **n8n:** A powerful workflow automation tool.

Both applications are orchestrated using Docker Compose, allowing for easy setup and management.

## Getting Started

To get started with the Open-Suite project, you will need to configure and run each sub-project (Hoppscotch and n8n) individually.

### 1. Configure Hoppscotch

*   Navigate to the `hoppscotch/` directory:
    ```bash
    cd hoppscotch/
    ```
*   Create a `.env` file by copying the `template.env` or one of the example environment files (e.g., `env-examples/env.local.example` or `env-examples/env.prod.example`). For local development, `env.local.example` is a good starting point:
    ```bash
    cp template.env .env
    # or
    cp env-examples/env.local.example .env
    ```
*   Open the newly created `.env` file and fill in the required environment variables according to your setup.

### 2. Configure n8n

*   Navigate to the `n8n/` directory:
    ```bash
    cd n8n/
    ```
*   Similar to Hoppscotch, create a `.env` file by copying `template.env` or one of the example environment files (e.g., `env-examples/env.local.example` or `env-examples/env.prod.example`). For local development, `env.local.example` is a good starting point:
    ```bash
    cp template.env .env
    # or
    cp env-examples/env.local.example .env
    ```
*   Open the newly created `.env` file and fill in the required environment variables.

### 3. Start the Services

Once both Hoppscotch and n8n are configured, you can start their respective services:

*   **For Hoppscotch:** From within the `hoppscotch/` directory, run:
    ```bash
    docker compose up --build -d
    ```
*   **For n8n:** From within the `n8n/` directory, run:
    ```bash
    docker compose up --build -d
    ```

### 4. Accessing Services

After the services are running, you can access Hoppscotch and n8n by navigating to the domains you configured in their respective `.env` files in your web browser.

## Stopping the Services

To stop the services for each sub-project:

*   **For Hoppscotch:** From within the `hoppscotch/` directory, run:
    ```bash
    docker compose down
    ```
*   **For n8n:** From within the `n8n/` directory, run:
    ```bash
    docker compose down
    ```

To stop services and remove data volumes (useful for a clean restart), add `-v` to the `down` command (e.g., `docker compose down -v`).
