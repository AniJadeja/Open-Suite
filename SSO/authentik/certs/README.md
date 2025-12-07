# Certificates Directory

This directory is mapped to `/certs` inside the Authentik worker container.

## Purpose
Store your custom SSL/TLS certificates here if you wish to use your own domain and HTTPS configuration.

## Usage
Place your certificate files (e.g., `cert.pem`, `key.pem`) in this folder.
You may need to update the Authentik configuration to reference these specific filenames.

## Current Status
If this folder is empty, Authentik is using its default self-signed certificates or operating in HTTP mode.
