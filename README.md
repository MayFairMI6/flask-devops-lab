# Flask DevOps Lab

A small Flask service for practicing Git integration, HTTP endpoints, and container packaging. The application exposes enough runtime information to check that the expected version is running after an update.

## Implementation and contribution

The repository separates request handlers in `app.py`, application metadata in `config.json`, and packaging in `Dockerfile` / `compose.yml`. My commits add the status endpoint and container configuration and record the branch/merge exercise. This is a focused software-engineering lab, with no research-performance claim.

**Technologies:** Python, Flask, JSON, Docker, and Docker Compose.

| Route | Purpose |
|---|---|
| `/` | Application name and version |
| `/api/health` | Basic process health response |
| `/api/config` | Contents of the local application configuration |
| `/api/report` | Hostname, Python version, and process uptime |
| `/api/version` | Application name and version as JSON |
| `/api/status` | Name, version, and registered routes |

## Run locally

```sh
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python app.py
```

Open `http://localhost:8080`. Alternatively, run `docker compose up --build` from the repository root.

## Checks and scope

On September 30, 2026, a Flask test-client smoke check returned HTTP 200 for all six application routes. This checks route availability, not load behavior or deployment security. The committed `tests/` directory currently contains only a placeholder, so this repository does not claim a completed automated test suite or load benchmark.

The app runs Flask's development server with debug mode enabled and exposes configuration and host diagnostics. Keep it in a trusted local environment and keep credentials out of `config.json`. Production deployment would require a production server, restricted diagnostics, and authentication where appropriate.
