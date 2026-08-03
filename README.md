<div align="center">

# ☁️ Quasar Sniper

**Tokenless Discord username checker** with a rich terminal UI, proxy rotation, and a full Multi-Tool suite.

**Async. Fast. Polished. Educative.**

<br>

<img src="assets/preview.png" alt="Quasar Sniper — Main Menu" width="100%">

<br>

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-Educational-purple?style=for-the-badge)](#️-disclaimer)
[![Status](https://img.shields.io/badge/Status-Maintained%20(School)-amber?style=for-the-badge)](#)

</div>

---

> **PR status:** I will review pull requests when they are opened, but I will not be updating this project right now because I have school. If you want faster attention, open a PR with a clear description and tests.

---

## 👾 Features

<details>
<summary><b>Click to expand</b></summary>

<br>

### Core Engine
- **Async Discord username checker** — no token required; uses `aiohttp` / `httpx` with HTTP/2 support
- **Live terminal dashboard** — powered by `rich`, with real-time stats, progress, and feed
- **Adaptive concurrency** — auto-tunes worker count based on success rate
- **Deduplication** — skips re-checking the same username
- **Dynamic timeout** — adjusts per-request based on response times
- **Latency scoring** — prefers faster proxies
- **Jitter & backoff** — avoids pattern detection by Discord
- **Circuit breaker** — protects proxies from being hammered
- **Webhook notifications** — sends hits to Discord with custom JSON payloads
- **Theme system** — choose from 7 color palettes (purple, maroon, cyan, green, amber, blue, light)
- **Nebula AI** — interactive assistant for help and tips
- **Headless mode** — run with `--auto` for automation
- **Export / Import settings** — easily backup and restore configurations

### Proxy Management
- **Scraped proxies** — auto-tested, scored, and rotated
- **Static lists** — supports HTTP, HTTPS, and SOCKS5
- **Scoring** — proxies with higher success rates are preferred
- **Cooldowns** — rate-limited proxies are temporarily disabled
- **Validation cache** — avoids repeated tests (TTL 1 hour)

### Multi-Tool Suite
- **guns.lol viewbot** — send views to a target username
- **Roblox username sniper** — check availability with custom length generation
- **Snapchat snapscore bot** — auto-send snaps (Windows only)
- **TikTok username sniper** — check availability via profile pages
- **Minecraft** — coming soon

</details>

---

## 🚀 Quick Start

### Prerequisites
- **Python 3.9** or higher
- **pip** (Python package manager)

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/quasar.git
cd quasar

# Create a virtual environment (recommended)
python -m venv .venv

# Activate it
# macOS / Linux:
source .venv/bin/activate
# Windows:
.venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

> **Note:** For SOCKS5 proxies, install `aiohttp-socks`.  
> For the Snapchat bot, `pyautogui` and `keyboard` are required (Windows only).

---

## 🖥️ Usage

### Interactive Mode

```bash
python quasar.py
```

| Option | Description |
|--------|-------------|
| **Setup Wizard** | Step-by-step configuration of proxies, usernames, speed, and webhook |
| **Settings** | Adjust timeouts, concurrency, engine, theme, and toggles |
| **Multi-Tool** | Access all extra tools (guns.lol, Roblox, Snapchat, TikTok) |
| **Sniper Mode** | Quick run with the last saved config |
| **Nebula AI** | Interactive assistant for help |

### Headless / Auto Mode

```bash
python quasar.py --auto
```

Uses the last saved configuration and exits when finished — perfect for scheduled runs.

### Performance Profiles

```bash
python quasar.py --profile fast      # high concurrency, short timeout
python quasar.py --profile safe      # low concurrency, long timeout
python quasar.py --profile balanced  # default
```

### CLI Flags

| Flag | Description |
|------|-------------|
| `--debug` | Enable verbose debug output |
| `--no-wizard` | Skip wizard and use saved files |
| `--generate-license 365` | Generate a license key valid for 365 days |
| `--validate-proxies-only` | Validate proxies and exit |
| `--export-hits report.json` | Export found usernames to JSON |
| `--dry-run` | Show config without executing |

---

## ⚙️ Configuration

All settings are stored in `data/config.json`.  
You can also export/import settings from the **Settings** menu.

### Proxy Files
- `data/proxies.txt` — one proxy per line  
  Format: `http://user:pass@host:port` or `socks5://host:port`
- **Built-in scraper** — fetches free proxies from 50+ sources, deduplicates, and scores them

### Username Files
- `data/names_to_check.txt` — used by Quick Check and Sniper Mode
- `data/tiktok_usernames.txt` — optional input for TikTok mode

### Theme Customisation
Choose from **7 themes** in Settings:  
`purple` · `maroon` · `cyan` · `green` · `amber` · `blue` · `light`

---

## 🔬 Multi-Tool Features

### 1. guns.lol Viewbot
Send views to a target username. Requires at least one account with a valid cookie.  
The bot cycles through accounts and proxies to avoid detection.

### 2. Roblox Username Checker
Checks Roblox usernames for availability.  
Supports generating random usernames of custom length (2–5+ chars) with adjustable concurrency.  
Results saved to `valid.txt`.

### 3. Snapchat Snapscore Bot
Automates sending snaps to a shortcut list on Snapchat Web.

> **Platform warning:** This bot uses `pyautogui` and `keyboard` and is **Windows-only** (mouse/keyboard simulation).  
> Set mouse positions for the Camera, Send To, Shortcut, and Select All buttons.

### 4. TikTok Username Sniper
Checks TikTok usernames for availability by fetching the user profile page.  
If the page returns `404`, the username is available.  
Can generate random names or load from a file.

---

## 🌐 Proxy Management

| Feature | Description |
|---------|-------------|
| Scraped proxies | Auto-tested, scored, and rotated |
| Static lists | Supports HTTP, HTTPS, and SOCKS5 |
| Scoring | Proxies with higher success rates are preferred |
| Cooldowns | Rate-limited proxies are temporarily disabled |
| Validation cache | Avoids repeated tests (TTL 1 hour) |

---

## ⚡ Engine Features

| Feature | Description |
|---------|-------------|
| Adaptive concurrency | Auto-tunes worker count based on success rate |
| Deduplication | Skips re-checking the same username |
| Dynamic timeout | Adjusts per-request based on response times |
| Latency scoring | Prefers faster proxies |
| Jitter & backoff | Avoids pattern detection by Discord |
| Circuit breaker | Protects your proxies from being hammered |
| HTTP/2 support | Optional via `httpx` engine |

---

## 📁 Project Structure

```text
.
├── assets/             # README images (preview.png)
├── data/               # Proxy, username, and config files
├── logs/               # Log files (quasar.log, performance.log)
├── results/            # hits.txt (found usernames)
├── tests/              # Unit tests (pytest)
├── config.py           # Configuration, constants, themes
├── engine.py           # Core checker, circuit breaker, webhook
├── proxy.py            # Proxy manager, scoring, validation
├── ui.py               # Terminal UI with rich
├── wizard.py           # Setup wizard
├── guns.py             # guns.lol viewbot
├── roblox.py           # Roblox username checker
├── snapchat.py         # Snapchat snapscore bot
├── tiktok.py           # TikTok username sniper
├── nebula.py           # AI assistant
├── quasar.py           # Main entry point
├── requirements.txt    # Dependencies
└── README.md           # This file
```

---

## 🧪 Testing

```bash
pytest tests/
```

Tests cover proxy scoring, circuit breaker, config persistence, and stats atomicity.

---

## ❓ Q&A

<details>
<summary><b>Click to expand</b></summary>

<br>

**Q: Do I need a Discord token?**  
A: No — Quasar uses Discord’s public username validation API, which does not require authentication.

**Q: What proxies work best?**  
A: Static residential proxies give the best speed. Scraped free proxies (~2–5% work) can also be used but are slower.

**Q: How do I get a license key?**  
A: Run `python quasar.py --generate-license 365` to generate a key valid for 365 days.

**Q: Why does the Snapchat bot only work on Windows?**  
A: It uses `pyautogui` and `keyboard` for mouse/keyboard simulation, which are platform-specific.

**Q: Can I run Quasar without proxies?**  
A: Yes — it will fall back to proxyless mode with a single worker and a configurable RPS limit.

**Q: Where are found usernames saved?**  
A: They are stored in `results/hits.txt` (Discord) or `valid.txt` (Roblox), etc.

**Q: How do I change the theme?**  
A: Go to **Settings → Change theme** and select from 7 options.

</details>

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=yourusername/quasar&type=Date)](https://star-history.com/#yourusername/quasar&Date)

> Replace `yourusername/quasar` with the actual repository path.

---

## ⚠️ Disclaimer

**DISCLAIMER:** This repository is intended for **EDUCATIONAL PURPOSES ONLY**.  
The author takes no responsibility for any issues that arise from using this tool.  
By using this tool, you acknowledge and accept this disclaimer.

---

## 🙏 Credits

- **Main developer** — p93s
- **Snapchat bot** — original concept by vhs8
- **TikTok sniper** — original concept by MDEVIO

<br>

<div align="center">

**Made with ❤️ by the Quasar team.**

</div>
