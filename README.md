☁️ Quasar Sniper ☁️
(｡◕‿◕｡) Tokenless Discord username checker with a rich terminal UI, proxy rotation, and a full Multi-Tool suite. Async. Fast. Polished. ʕ•ᴥ•ʔ

🎀 Quasar Sniper — Main Menu
(◕‿◕) Python Status Version

📝 PR status: I will review pull requests when they are opened, but I will not be updating this project right now because I have school. If you want faster attention, open a PR with a clear description and tests ♡

✧ Features ✧
(Click to expand)

🚀 Quick Start
✨ Prerequisites
Python 3.9 or higher

pip (Python package manager)

📦 Installation
bash
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
💡 Note: For SOCKS5 proxies, install aiohttp-socks.
For the Snapchat bot, pyautogui and keyboard are required (Windows only).

🖥️ Usage
🌸 Interactive Mode
bash
python quasar.py
Option	Description
Setup Wizard	Step‑by‑step configuration of proxies, usernames, speed, and webhook
Settings	Adjust timeouts, concurrency, engine, theme, and toggles
Multi-Tool	Access all extra tools (guns.lol, Roblox, Snapchat, TikTok, Minecraft)
Sniper Mode	Quick run with the last saved config
Nebula Helper	Interactive assistant for help
🤖 Headless / Auto Mode
bash
python quasar.py --auto
Uses the last saved configuration and exits when finished — perfect for scheduled runs ✧

⚡ Performance Profiles
bash
python quasar.py --profile fast      # high concurrency, short timeout
python quasar.py --profile safe      # low concurrency, long timeout
python quasar.py --profile balanced  # default
🏳️ CLI Flags
Flag	Description
--debug	Enable verbose debug output
--no-wizard	Skip wizard and use saved files
--validate-proxies-only	Validate proxies and exit
--export-hits report.json	Export found usernames to JSON
--dry-run	Show config without executing
⚙️ Configuration
All settings are stored in data/config.json.
You can also export/import settings from the Settings menu ♡

📂 Proxy Files
data/proxies.txt — one proxy per line

Format: http://user:pass@host:port or socks5://host:port

Built‑in scraper — fetches free proxies from 70+ sources, deduplicates, and scores them

📝 Username Files
data/names_to_check.txt — used by Quick Check and Sniper Mode

data/tiktok_usernames.txt — optional input for TikTok mode

🎨 Theme Customisation
Choose from 7 themes in Settings:
purple · maroon · cyan · green · amber · blue · light

🔒 SSL Verification
Toggle SSL certificate validation globally via Settings → Core → «SSL Verification».
Enabled by default; disable only for internal testing with self‑signed certificates.

🔬 Multi-Tool Features
(｡♥‿♥｡)

1. 🔫 guns.lol Viewbot
Send views to a target username. Requires at least one account with a valid cookie.
The bot cycles through accounts and proxies to avoid detection.

2. 🧱 Roblox Username Checker
Checks Roblox usernames for availability.
Supports generating random usernames of custom length (2–5+ chars) with adjustable concurrency.
Results saved to results/roblox_available.txt.

3. ⛏️ Minecraft Username Sniper (Beta)
Monitors a username and notifies you the moment it becomes available.
Supports Windows toasts and Discord webhook alerts.

4. 👻 Snapchat Snapscore Bot
Automates sending snaps to a shortcut list on Snapchat Web.
⚠️ Platform warning: This bot uses pyautogui and keyboard and is Windows‑only (mouse/keyboard simulation).
Set mouse positions for the Camera, Send To, Shortcut, and Select All buttons.

5. 🎵 TikTok Username Sniper
Checks TikTok usernames for availability by fetching the user profile page.
If the page returns 404, the username is available.
Can generate random names or load from a file. Results saved to results/tiktok_available.txt.

🌐 Proxy Management
Feature	Description
🔍 Scraped proxies	Auto‑tested, scored, and rotated
📋 Static lists	Supports HTTP, HTTPS, and SOCKS5
⭐ Scoring	Proxies with higher success rates are preferred
🧊 Cooldowns	Rate‑limited proxies are temporarily disabled
🗂️ Validation cache	Avoids repeated tests (TTL 1 hour)
⚡ Engine Features
Feature	Description
🧠 Adaptive concurrency	Auto‑tunes worker count based on success rate
🧹 Deduplication	Skips re‑checking the same username
⏱️ Dynamic timeout	Adjusts per‑request based on response times
📶 Latency scoring	Prefers faster proxies
🎲 Jitter & backoff	Avoids pattern detection by Discord
🛡️ Circuit breaker	Protects your proxies from being hammered
🚀 HTTP/2 support	Optional via httpx engine
🧠 Engine Choices
aiohttp – Default, reliable, HTTP/1.1

httpx – HTTP/2 support, faster for some workloads

curl_cffi – TLS impersonation (Chrome/Firefox), helps bypass rate‑limits

📁 Project Structure
text
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
🧪 Testing
bash
pytest tests/
Tests cover proxy scoring, circuit breaker, config persistence, and stats atomicity.

❓ Q&A
(Click to expand)

⭐ Star History
(Star History Chart)

⚠️ Disclaimer
DISCLAIMER: This repository is intended for EDUCATIONAL PURPOSES ONLY.
The author takes no responsibility for any issues that arise from using this tool.
By using this tool, you acknowledge and accept this disclaimer.

🙏 Credits
Main developer — p93s

Snapchat bot — original concept by vhs8

TikTok sniper — original concept by MDEVIO

Made with 💖 by the Quasar team
ʕ•ᴥ•ʔ ✧ (｡◕‿◕｡)

