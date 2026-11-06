# OpenWA

OpenWA is a free, open-source WhatsApp API gateway for developers who want full control of their messaging infrastructure. The dashboard ships in the main image and is served on the app port.

This app runs OpenWA with PostgreSQL for data and Redis for cache and rate limiting.

## Before you install

- **API master key:** choose a value of at least 32 letters, digits, dashes or underscores and keep a copy. It seeds the admin key on first start only, so changing it later has no effect: rotate it through the API instead.
- **Database password and API key pepper:** Runtipi generates them and keeps them across updates.

## After you install

Open the dashboard, sign in with the master key, create a session and scan the QR code with WhatsApp.

## MCP server

The MCP endpoint for AI agents is on by default at `/mcp` on the app port, and read-only unless you turn that off. Both switches are in the app settings.

Give each agent a dedicated, non-admin API key limited to its session, without an IP allow-list. Do not expose `/mcp` to the internet without an authenticating proxy.

## Updating

Breaking changes ship in minor releases, so check the [release notes](https://github.com/rmyndharis/OpenWA/releases) before updating. Migrations run on start.
