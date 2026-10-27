# Instagram Scraper — Base

A local Python and Playwright application for collecting public Instagram profile and post data and exploring it in a dashboard. This base edition does not include Big Five or Benford analysis.

## Features

- Collects posts, captions, public follower/following lists, and visible profile counters. Instagram may limit or round the data, and lists may be partial.
- Builds a local dashboard with profile details, post media, search, sorting, and follower/following lists.
- Stores extraction output locally; do not commit browser sessions, credentials, or collected data.

## Requirements and installation (Windows PowerShell)

```powershell
py -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m playwright install chromium
```

## Collect data

```powershell
.\.venv\Scripts\python.exe scraper.py --username josedeodo --limit 50 --relationship-limit 100
```

The scraper opens a browser for your Instagram session. Sign in only in the browser window it opens. Follow Instagram’s rules and use a modest collection rate. The platform may limit data visibility.

## Build and open the dashboard

```powershell
.\.venv\Scripts\python.exe dashboard.py
```

Open the generated `dashboard.html` directly in a browser, or serve the project folder with a local static server.

## Project files

- `scraper.py` — Playwright data collection and extraction options.
- `dashboard.py` — dashboard layout and generated HTML.
- `requirements.txt` — Python dependencies.
