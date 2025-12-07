# Custom Templates Directory

This directory is mapped to `/templates` inside the Authentik server and worker containers.

## Purpose
Allows for the customization of Authentik's visual appearance and email templates.

## Usage
You can override default HTML templates by placing modified versions here.
Common overrides include:
- Login pages
- Email verification templates
- Error pages

## Structure
Files placed here should mirror the structure of the internal templates directory.
See the [Authentik Documentation](https://goauthentik.io/docs/events/customization) for details on template structure.
