<div align="center">

<img src="assets/cover.png" alt="OpenClaw X" width="600" />

# 🦅 OpenClaw X

**让 AI Agent 操控你的 X/Twitter 账号**

本地运行 · 零 API 费用 · 隐私安全

[![Release](https://img.shields.io/github/v/release/bosshuman/openclaw-x?style=flat-square&color=00c853)](https://github.com/bosshuman/openclaw-x/releases)
[![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Linux%20%7C%20Windows-blue?style=flat-square)](https://github.com/bosshuman/openclaw-x/releases)
[![ClawHub](https://img.shields.io/badge/ClawHub-openclaw--x-orange?style=flat-square)](https://clawhub.ai/bosshuman/openclaw-x)
[![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)](LICENSE)

[English](README.md) · **中文** · [日本語](README_JA.md) · [한국어](README_KO.md)

</div>

---

## ✨ 特性

- 🤖 **AI 原生** — 专为 OpenClaw Agent 设计的 Skill
- 🔒 **本地运行** — 数据不经过第三方，仅监听 `localhost`
- 🍪 **Cookie 认证** — 使用浏览器 Cookie，无需 API Key
- ⚡ **一键启动** — 下载即用，无需安装依赖
- 🌍 **跨平台** — 支持 macOS / Linux / Windows

---

## 🚀 快速开始

### 1️⃣ 下载

从 [**Releases**](https://github.com/bosshuman/openclaw-x/releases) 下载对应平台的可执行文件：

| 平台 | 文件 | 架构 |
|:----:|:-----|:----:|
| 🍎 macOS | `openclaw-x-macos-arm64` | Apple Silicon |
| 🍎 macOS | `openclaw-x-macos-x64` | Intel |
| 🐧 Linux | `openclaw-x-linux-x64` | x64 |
| 🪟 Windows | `openclaw-x-windows-x64.exe` | x64 |

### 2️⃣ 配置 Cookies

> 从 Chrome 导出 X 的 cookies

1. 登录 [x.com](https://x.com)
2. 安装 [**Cookie-Editor**](https://chromewebstore.google.com/detail/cookie-editor/hlkenndednhfkekhgcdicdfddnkalmdm) 扩展
3. 点击扩展图标 → **Export** → 保存为 `cookies.json`，放在可执行文件同目录

### 3️⃣ 启动

```bash
# macOS / Linux
chmod +x openclaw-x-macos-arm64
./openclaw-x-macos-arm64

# Windows
openclaw-x-windows-x64.exe
```

> 🟢 服务启动在 `http://localhost:19816`
> 📖 API 文档：`http://localhost:19816/docs`

### 4️⃣ 安装 Skill

```bash
# 通过 ClawHub 安装
npx clawhub@latest install openclaw-x

# 或手动复制
cp SKILL.md ~/.openclaw/skills/openclaw-x/SKILL.md
```

---

## 📡 API

| 端点 | 方法 | 功能 |
|:-----|:----:|:-----|
| `/health` | `GET` | 健康检查 + 登录状态 |
| `/timeline` | `GET` | 📰 首页时间线 |
| `/tweet/{id}` | `GET` | 🔍 推文详情 |
| `/search?q=关键词` | `GET` | 🔎 搜索推文 |
| `/tweet` | `POST` | ✏️ 发推文 |
| `/tweet/{id}/like` | `POST` | ❤️ 点赞 |
| `/tweet/{id}/retweet` | `POST` | 🔁 转推 |
| `/tweet/{id}/bookmark` | `POST` | 🔖 收藏 |
| `/user/{username}` | `GET` | 👤 用户信息 |
| `/user/{username}/tweets` | `GET` | 📋 用户推文 |

---

## 💬 使用示例

```bash
# 📰 获取时间线
curl http://localhost:19816/timeline

# 🔎 搜索推文
curl "http://localhost:19816/search?q=AI&count=10"

# ✏️ 发推
curl -X POST http://localhost:19816/tweet \
  -H "Content-Type: application/json" \
  -d '{"text": "Hello from OpenClaw! 🦅"}'

# ❤️ 点赞
curl -X POST http://localhost:19816/tweet/1234567890/like
```

---

## ⚠️ 注意事项

> [!CAUTION]
> - 本工具使用非官方接口，存在账号风险
> - 仅监听 localhost，**请勿暴露到公网**
> - `cookies.json` 包含敏感登录信息，**请勿泄露**

> [!WARNING]
> **安全建议**
> - 🛡️ 建议使用 **X 小号**（非主账号）运行
> - 📦 尽量在 **隔离环境**（容器 / 虚拟机）中运行
> - 🔐 `cookies.json` 等同于你的登录凭证，请像对待密码一样保管
> - 🚫 不要将可执行文件或 `cookies.json` 分享给他人

---

<div align="center">

**Sponsored by [xman.ink](https://xman.ink)** — 智能推特书签管理平台

</div>
