☁️ Quasar Sniper
Tokenless Discord username checker with a rich terminal UI, proxy rotation, and a full Multi‑Tool suite.

PR status: I will review pull requests when they are opened, but I will not be updating this project right now because I have school. If you want faster attention, open a PR with a clear description and tests.

👾 Features
<details> <summary>Click to expand</summary>
Async Discord username checker – no token required, uses aiohttp/httpx.

Live terminal dashboard – powered by rich, with real‑time stats and progress.

Proxy rotation & scoring – supports HTTP, HTTPS, and SOCKS5; auto‑tested and weighted.

Multi‑Tool suite – includes:

guns.lol viewbot

Roblox username sniper

Snapchat snapscore bot (Windows only)

TikTok username sniper

Minecraft (coming soon)

Adaptive concurrency – auto‑tunes worker count based on success rate.

Deduplication – skips re‑checking the same username.

Dynamic timeout – adjusts per‑request based on response times.

Latency scoring – prefers faster proxies.

Circuit breaker – protects proxies from being hammered.

Webhook notifications – sends hits to Discord with custom JSON payloads.

Theme system – choose from 7 color palettes (purple, maroon, cyan, green, amber, blue, light).

Nebula AI – interactive assistant for help and tips.

Headless mode – run with --auto for automation.

Export/Import settings – easily backup and restore configurations.

Proxy scraper – fetches free proxies from 50+ sources with deduplication.

</details>
📝 Licensing
Please read the license carefully; failure to comply may result in legal action.

This program is distributed under the AGPL v3.0. Ensure proper credit is given to this project.
You can find the full license text in the LICENSE file.

👁 Preview
A live dashboard during a scan:

https://i.imgur.com/your-screenshot.png
(Replace with a real screenshot or GIF)

❓ Q&A
<details> <summary>Click to expand</summary>
Q: Do I need a Discord token?
A: No – Quasar uses Discord’s public username validation API, which does not require authentication.

Q: What proxies work best?
A: Static residential proxies give the best speed. Scraped free proxies (~2–5% work) can also be used but are slower.

Q: How do I get a license key?
A: Run python quasar.py --generate-license 365 to generate a key valid for 365 days.

Q: Why does the Snapchat bot only work on Windows?
A: It uses pyautogui and keyboard for mouse/keyboard simulation, which are platform‑specific.

Q: Can I run Quasar without proxies?
A: Yes – it will fall back to proxyless mode with a single worker and a configurable RPS limit.

Q: Where are found usernames saved?
A: They are stored in results/hits.txt (Discord) or valid.txt (Roblox), etc.

</details>
⭐ Star History
https://api.star-history.com/svg?repos=yourusername/quasar&type=Date
(Replace yourusername/quasar with the actual repo URL)

⚠️ Disclaimer
DISCLAIMER: This repository is intended for EDUCATIONAL PURPOSES ONLY. The author takes no responsibility for any issues that arise from using this tool. By using this tool, you acknowledge and accept this disclaimer.

🚀 Quick Start
bash
git clone https://github.com/yourusername/quasar.git
cd quasar
python -m venv .venv
source .venv/bin/activate  # or .venv\Scripts\activate on Windows
pip install -r requirements.txt
python quasar.py
For more details, see the full Installation & Usage section (or refer to the original README).

🧠 Credits
Main developer – p93s

Snapchat bot – original concept by vhs8

TikTok sniper – original concept by MDEVIO

<p align="center"> Made with ❤️ by the Quasar team. </p>
