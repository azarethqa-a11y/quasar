<div align="center">

# ☁️ Quasar Sniper ☁️

**(｡◕‿◕｡)** Tokenless Discord username checker with a rich terminal UI, proxy rotation, and a full Multi-Tool suite.

**Async. Fast. Polished.** ʕ•ᴥ•ʔ

<br>

<img src="Screenshot%202026-08-03%20151440.png" alt="Quasar Sniper — Main Menu" width="100%">

<br>

[![Python](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](#️-disclaimer)
[![PRs](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/azarethqa-a11y/quasar/pulls)
[![Stars](https://img.shields.io/github/stars/azarethqa-a11y/quasar.svg)](https://github.com/azarethqa-a11y/quasar/stargazers)

</div>

---

## 📖 Table of Contents

- [✨ Features](#-features)
- [🚀 Quick Start](#-quick-start)
- [🖥️ Usage](#️-usage)
- [⚙️ Configuration](#️-configuration)
- [🔬 Multi-Tool Features](#-multi-tool-features)
- [🌐 Proxy Management](#-proxy-management)
- [⚡ Engine Features](#-engine-features)
- [📁 Project Structure](#-project-structure)
- [🧪 Testing](#-testing)
- [❓ Q&A](#-qa)
- [⚠️ Disclaimer](#️-disclaimer)
- [🙏 Credits](#-credits)

---

## 🎀 About Quasar

> 📝 **PR status:** I will review pull requests when they are opened, but I will not be updating this project right now because I have school. If you want faster attention, open a PR with a clear description and tests ♡

Quasar is an advanced, **tokenless** Discord username availability checker with a beautiful terminal interface. It supports three request engines, intelligent proxy rotation, and a comprehensive Multi-Tool suite for various platforms.

---

## ✨ Features

| Category | Features |
|----------|----------|
| ⚡ **Performance** | Async I/O, 500–1500+ RPS with proxies, adaptive concurrency |
| 🔄 **Proxy Management** | HTTP / HTTPS / SOCKS5 support, scoring, rotation, auto-validation |
| 🎨 **User Interface** | Rich terminal UI, 7 colour themes, real-time live dashboard |
| 🛡️ **Reliability** | Circuit breaker, retry logic, checkpointing, deduplication |
| 🔌 **Request Engines** | `aiohttp`, `httpx`, `curl_cffi` (TLS impersonation) |
| 🧩 **Multi-Tool** | guns.lol, Roblox, Minecraft, Snapchat, TikTok |
| 📊 **Webhooks** | Discord notifications with rich embeds |
| 💾 **Data Export** | JSON, CSV, HTML export formats |

---

## 🚀 Quick Start

### ✨ Prerequisites

- Python **3.9** or higher
- `pip` (Python package manager)

### 📦 Installation

```bash
# Clone the repository
git clone https://github.com/azarethqa-a11y/quasar.git
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

> 💡 **Note:** For SOCKS5 proxies, install `aiohttp-socks`.  
> For the Snapchat bot, `pyautogui` and `keyboard` are required (Windows only).

---

## 🖥️ Usage

### 🌸 Interactive Mode

```bash
python quasar.py
```

| Option | Description |
|--------|-------------|
| **01. Quasar** | Run the main username checker with full setup wizard |
| **02. Settings** | Adjust timeouts, concurrency, engine, theme, and toggles |
| **03. Multi-Tool** | Access all extra tools (guns.lol, Roblox, Snapchat, TikTok, Minecraft) |
| **04. Sniper Mode** | Quick run with the last saved configuration |
| **05. Nebula Helper** | Interactive AI assistant for help |
| **06. Export Results** | Export found usernames to JSON, CSV, or HTML |
| **00. Exit** | Quit Quasar |

### 🤖 Headless / Auto Mode

```bash
python quasar.py --auto
```

Uses the last saved configuration and exits when finished — perfect for scheduled runs ✧

### ⚡ Performance Profiles

```bash
python quasar.py --profile fast      # high concurrency, short timeout
python quasar.py --profile safe      # low concurrency, long timeout
python quasar.py --profile balanced  # default
```

### 🏳️ CLI Flags

| Flag | Description |
|------|-------------|
| `--debug` | Enable verbose debug output |
| `--no-wizard` | Skip wizard and use saved files |
| `--validate-proxies-only` | Validate proxies and exit |
| `--export-hits report.json` | Export found usernames to JSON |
| `--dry-run` | Show configuration without executing |
| `--instance NAME` | Isolate data/logs/results in named subdirectories |

---

## ⚙️ Configuration

All settings are stored in `data/config.json`.  
You can also export/import settings from the **Settings** menu ♡

### 📂 Proxy Files

- `data/proxies.txt` — one proxy per line  
  Format: `http://user:pass@host:port` or `socks5://host:port`
- **Built-in scraper** — fetches free proxies from **70+** sources, deduplicates, and scores them

### 📝 Username Files

- `data/names_to_check.txt` — used by Quick Check and Sniper Mode
- `data/tiktok_usernames.txt` — optional input for TikTok mode

### 🎨 Theme Customisation

Choose from **7 themes** in Settings:  
`purple` · `maroon` · `cyan` · `green` · `amber` · `blue` · `light`

### 🔧 Available Settings

| Category | Settings |
|----------|----------|
| **Core** | Timeout, Concurrency, Adaptive Concurrency, Deduplication, Dynamic Timeout, Latency Scoring, Verbose Logging, Color Mode, UI Style, Theme |
| **Performance** | Proxy Validation Timeout, Request Engine, Proxyless RPS, Proxy Failure Retries, Proxy Failure Backoff, Impersonation (`curl_cffi`) |
| **Proxies** | Auto-remove dead proxies, Health Check, Proxy Countries, Proxy Scoring, Autopilot |
| **Webhook** | URL, Message Template, Embeds |
| **Checkpoint** | Enabled, Interval |

---

## 🔬 Multi-Tool Features

**(｡♥‿♥｡)**

### 1. 🔫 guns.lol Viewbot

Send views to a target username. Requires at least one account with a valid cookie.  
The bot cycles through accounts and proxies to avoid detection.

### 2. 🧱 Roblox Username Checker

Checks Roblox usernames for availability.  
Supports generating random usernames of custom length (2–5+ chars) with adjustable concurrency.  
Results saved to `results/roblox_available.txt`.

### 3. ⛏️ Minecraft Username Sniper *(Beta)*

Monitors a username and notifies you the moment it becomes available.  
Supports Windows toasts and Discord webhook alerts.

### 4. 👻 Snapchat Snapscore Bot

Automates sending snaps to a shortcut list on Snapchat Web.

> ⚠️ **Platform warning:** This bot uses `pyautogui` and `keyboard` and is **Windows-only** (mouse/keyboard simulation).  
> Set mouse positions for the Camera, Send To, Shortcut, and Select All buttons.

### 5. 🎵 TikTok Username Sniper

Checks TikTok usernames for availability by fetching the user profile page.  
If the page returns `404`, the username is available.  
Can generate random names or load from a file.  
Results saved to `results/tiktok_available.txt`.

---

## 🌐 Proxy Management

| Feature | Description |
|---------|-------------|
| 🔍 Scraped proxies | Auto-tested, scored, and rotated |
| 📋 Static lists | Supports HTTP, HTTPS, and SOCKS5 |
| ⭐ Scoring | Proxies with higher success rates are preferred |
| 🧊 Cooldowns | Rate-limited proxies are temporarily disabled |
| 🗂️ Validation cache | Avoids repeated tests (TTL 1 hour) |
| 🚀 Health Check | Periodic validation of proxy pool |
| 🤖 Autopilot | Automatically fetches fresh proxies when pool runs low |

---

## ⚡ Engine Features

| Feature | Description |
|---------|-------------|
| 🧠 Adaptive concurrency | Auto-tunes worker count based on success rate |
| 🧹 Deduplication | Skips re-checking the same username |
| ⏱️ Dynamic timeout | Adjusts per-request based on response times |
| 📶 Latency scoring | Prefers faster proxies |
| 🎲 Jitter & backoff | Avoids pattern detection by Discord |
| 🛡️ Circuit breaker | Protects your proxies from being hammered |
| 🚀 HTTP/2 support | Optional via `httpx` engine |

### 🧠 Engine Choices

| Engine | Description | Best For |
|--------|-------------|----------|
| **aiohttp** | Default, reliable, HTTP/1.1 | General use, stability |
| **httpx** | HTTP/2 support, faster for some workloads | High concurrency, HTTP/2 |
| **curl_cffi** | TLS impersonation (Chrome / Firefox) | Bypassing rate-limits |

---

## 📁 Project Structure

```text
.
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
├── minecraft.py        # Minecraft username sniper
├── nebula.py           # Nebula Helper (AI assistant)
├── quasar.py           # Main entry point
├── requirements.txt    # Dependencies
└── README.md           # This file ♡
```

---

## 🧪 Testing

```bash
pytest tests/
```

Tests cover:

- Proxy scoring and rotation
- Circuit breaker logic
- Configuration persistence
- Stats atomicity
- Username validation

---

## ❓ Q&A

**Q: Is this against Discord's ToS?**  
A: Yes, automating username changes via self-bots is against Discord's Terms of Service. This tool is intended for educational purposes only.

**Q: Can I use it without proxies?**  
A: Yes, but you'll be rate-limited quickly. Proxies are strongly recommended.

**Q: Which engine should I choose?**  
A: Start with `aiohttp`. If you experience rate-limits, try `curl_cffi` (requires installation). `httpx` is great for HTTP/2.

**Q: How do I get proxies?**  
A: Use the built-in scraper (option `s` in the wizard) or provide your own static list.

**Q: Can I run it headlessly?**  
A: Yes, use `python quasar.py --auto` for headless operation.

**Q: Where are results saved?**  
A: `results/hits.txt` for Discord username checks. Each tool saves to its own file (e.g. `results/roblox_available.txt`).

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=azarethqa-a11y/quasar&type=Date)](https://star-history.com/#azarethqa-a11y/quasar&Date)

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
- **Contributors** — Thank you to everyone who has contributed to this project!

<br>

<div align="center">

**Made with 💖 by the Quasar team**  
