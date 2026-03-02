# Outline - Local Docker Deployment

Self-hosted [Outline](https://www.getoutline.com/) knowledge base using Docker Compose.

## Requirements

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Quick Start

1. **Copy and configure environment:**
   ```bash
   cp docker.env.example docker.env
   ```

2. **Edit `docker.env` and set:**
   - `SECRET_KEY` and `UTILS_SECRET` — generate with `openssl rand -hex 32`
   - At least one auth provider (e.g. Google OAuth) — see [Authentication](https://docs.getoutline.com/s/hosting/doc/authentication-7ViKRmRY5o)

3. **Start services:**
   ```bash
   docker compose up -d
   ```

4. **Open:** http://localhost:3000

5. **First run:** Create your account via the auth provider you configured.

## Auth Setup (required)

Outline needs at least one sign-in method. For local dev:

- **Google:** Create OAuth credentials at [Google Cloud Console](https://console.cloud.google.com/). Add `http://localhost:3000/auth/google.callback` as redirect URI.
- **Slack / Microsoft / Discord:** See [Outline Authentication docs](https://docs.getoutline.com/s/hosting/doc/authentication-7ViKRmRY5o).

## Links

- [Outline Docker docs](https://docs.getoutline.com/s/hosting/doc/docker-7pfeLP5a8t)
- [Configuration](https://docs.getoutline.com/s/hosting/doc/configuration-509J4lAzjo)
- [Requirements](https://docs.getoutline.com/s/hosting/doc/requirements-ULdYnwi4wG)
