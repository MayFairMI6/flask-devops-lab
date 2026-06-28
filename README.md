# Flask DevOps Lab

## Usage

```bash
source .venv/bin/activate
pip install -r requirements.txt
python app.py
```

## Routes

- `/api/health` returns a JSON health check for the Flask app.
- `/api/config` returns the app configuration from `config.json`.
- `/api/report` returns diagnostic information such as hostname, Python version, and uptime.
