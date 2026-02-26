<div align="center">

<img src="assets/cover.png" alt="OpenClaw X" width="600" />

# 🦅 OpenClaw X

**Let AI Agents control your X/Twitter account**

Local execution · Zero API cost · Privacy-first

[![Release](https://img.shields.io/github/v/release/bosshuman/openclaw-x?style=flat-square&color=00c853)](https://github.com/bosshuman/openclaw-x/releases)
[![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Linux%20%7C%20Windows-blue?style=flat-square)](https://github.com/bosshuman/openclaw-x/releases)
[![ClawHub](https://img.shields.io/badge/ClawHub-xskill-orange?style=flat-square)](https://clawhub.ai)
[![License](https://img.shields.io/badge/license-proprietary-lightgrey?style=flat-square)]()

[**English**](README_EN.md) · [中文](README.md) · [日本語](README_JA.md) · [한국어](README_KO.md)

</div>

---

## ✨ Features

- 🤖 **AI-Native** — Purpose-built Skill for OpenClaw Agent
- 🔒 **Local-First** — Data never leaves your machine, listens on `localhost` only
- 🍪 **Cookie Auth** — Uses browser cookies, no API key needed
- ⚡ **Zero Setup** — Download and run, no dependencies required
- 🌍 **Cross-Platform** — macOS / Linux / Windows

---

## 🚀 Quick Start

### 1️⃣ Download

Grab the executable for your platform from [**Releases**](https://github.com/bosshuman/openclaw-x/releases):

| Platform | File | Arch |
|:--------:|:-----|:----:|
| 🍎 macOS | `openclaw-x-macos-arm64` | Apple Silicon |
| 🍎 macOS | `openclaw-x-macos-x64` | Intel |
| 🐧 Linux | `openclaw-x-linux-x64` | x64 |
| 🪟 Windows | `openclaw-x-windows-x64.exe` | x64 |

### 2️⃣ Configure Cookies

> Export your X cookies from Chrome

1. Log in to [x.com](https://x.com)
2. Install [**Cookie-Editor**](https://chromewebstore.google.com/detail/cookie-editor/hlkenndednhfkekhgcdicdfddnkalmdm) extension
3. Click the extension icon → **Export** → Save as `cookies.json` in the same directory

### 3️⃣ Launch

```bash
# macOS / Linux
chmod +x openclaw-x-macos-arm64
./openclaw-x-macos-arm64

# Windows
openclaw-x-windows-x64.exe
```

> 🟢 Service runs at `http://localhost:19816`
> 📖 API docs: `http://localhost:19816/docs`

### 4️⃣ Install Skill

```bash
# Via ClawHub
npx clawhub@latest install xskill

# Or manually
cp SKILL.md ~/.openclaw/skills/openclaw-x/SKILL.md
```

---

## 📡 API

| Endpoint | Method | Description |
|:---------|:------:|:------------|
| `/health` | `GET` | Health check + login status |
| `/timeline` | `GET` | 📰 Home timeline |
| `/tweet/{id}` | `GET` | 🔍 Tweet details |
| `/search?q=keyword` | `GET` | 🔎 Search tweets |
| `/tweet` | `POST` | ✏️ Post a tweet |
| `/tweet/{id}/like` | `POST` | ❤️ Like |
| `/tweet/{id}/retweet` | `POST` | 🔁 Retweet |
| `/tweet/{id}/bookmark` | `POST` | 🔖 Bookmark |
| `/user/{username}` | `GET` | 👤 User info |
| `/user/{username}/tweets` | `GET` | 📋 User tweets |

---

## 💬 Examples

```bash
# 📰 Get timeline
curl http://localhost:19816/timeline

# 🔎 Search tweets
curl "http://localhost:19816/search?q=AI&count=10"

# ✏️ Post a tweet
curl -X POST http://localhost:19816/tweet \
  -H "Content-Type: application/json" \
  -d '{"text": "Hello from OpenClaw! 🦅"}'

# ❤️ Like a tweet
curl -X POST http://localhost:19816/tweet/1234567890/like
```

---

## ⚠️ Disclaimer

> [!CAUTION]
> - Uses unofficial API — account risk possible
> - Listens on localhost only, **do not expose to public network**
> - `cookies.json` contains sensitive login data, **keep it safe**

> [!WARNING]
> **Security Recommendations**
> - 🛡️ Use a **secondary X account** (not your primary) for safety
> - 📦 Run in an **isolated environment** (container / VM) when possible
> - 🔐 Treat `cookies.json` like a password — it grants full account access
> - 🚫 Never share the executable or `cookies.json` with untrusted parties

---

<div align="center">

**Sponsored by [xman.ink](https://xman.ink)** — Smart Twitter Bookmark Manager

</div>
