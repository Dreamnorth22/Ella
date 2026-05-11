# Ella Assistant

Ella pinned to Python **3.14.5**. Source files use **UTF-8** (`# -*- coding: utf-8 -*-` in `.py`, `.editorconfig` for editors).

## Official sources

- [Python 3.14 — What's New](https://docs.python.org/3.14/whatsnew/3.14.html)
- [Python 3.14 — venv](https://docs.python.org/3.14/library/venv.html)
- [Python 3.14 — Installing modules](https://docs.python.org/3.14/installing/index.html)
- [PyPA — pip and virtual environments](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/)

## Python version

- Required: **3.14.5** (see `install.py`, `pyproject.toml`).

## Install

```bash
python install.py
```

Optional system packages:

```bash
python install.py --auto-system
```

Null-byte repair:

```bash
python rebuild.py
python install.py
```

## Run

GUI:

```bash
python ella.py --gui
```

Portable launchers (UTF-8 console on Windows):

- **Windows:** double-click `run_ella.bat` or run it from `cmd`.
- **Linux / macOS:** `chmod +x run_ella.sh` once, then `./run_ella.sh`.

CLI:

```bash
python ella.py
```

## Diagnostics

```bash
python diagnostics.py
```

Or use the **Diagnostics** button in the Chat tab.

## UI overview

- **Chat:** **Send**, **Web** (internet answer in chat), **Help**, **Diagnostics**. With **Google in chat** enabled (Settings), normal questions trigger Google-backed answers and self-learning memory.
- **Browser:** opens a **pywebview** window (Edge WebView2 on Windows, WebKit on macOS/Linux) — **WebGL**, **YouTube**, full sites. Uses `ella_browser.py` in a separate process so Tkinter stays responsive.
- **Code:** generate / explain / run / web search output.
- **Manuals:** built-in RU/EN snippets.
- **Providers & keys:** providers registry, API keys (stored locally in `ella_config.json`), reference links, optional pip modules with **pip install**.

### Browser dependencies

- `pip install pywebview` (included in `requirements.txt`).
- **Windows:** [WebView2 Runtime](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) if the window is empty.
- **Linux:** WebKitGTK or Qt per [pywebview docs](https://pywebview.flowrl.com/guide/installation.html).

## Security note

API keys are stored in plain text in `ella_config.json` on your machine. Do not share that file.
