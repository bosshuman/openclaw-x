<div align="center">

<img src="assets/cover.png" alt="OpenClaw X" width="600" />

# 🦅 OpenClaw X

**AI Agent で X/Twitter アカウントを操作**

ローカル実行 · API費用ゼロ · プライバシー重視

[![Release](https://img.shields.io/github/v/release/bosshuman/openclaw-x?style=flat-square&color=00c853)](https://github.com/bosshuman/openclaw-x/releases)
[![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Linux%20%7C%20Windows-blue?style=flat-square)](https://github.com/bosshuman/openclaw-x/releases)
[![ClawHub](https://img.shields.io/badge/ClawHub-xskill-orange?style=flat-square)](https://clawhub.ai)
[![License](https://img.shields.io/badge/license-proprietary-lightgrey?style=flat-square)]()

[English](README_EN.md) · [中文](README.md) · **日本語** · [한국어](README_KO.md)

</div>

---

## ✨ 特徴

- 🤖 **AI ネイティブ** — OpenClaw Agent 専用の Skill
- 🔒 **ローカル実行** — データは外部に送信されず、`localhost` のみ
- 🍪 **Cookie 認証** — ブラウザの Cookie を使用、API Key 不要
- ⚡ **ゼロセットアップ** — ダウンロードして即実行
- 🌍 **クロスプラットフォーム** — macOS / Linux / Windows

---

## 🚀 クイックスタート

### 1️⃣ ダウンロード

[**Releases**](https://github.com/bosshuman/openclaw-x/releases) からお使いのプラットフォーム用の実行ファイルをダウンロード：

| プラットフォーム | ファイル | アーキテクチャ |
|:----:|:-----|:----:|
| 🍎 macOS | `openclaw-x-macos-arm64` | Apple Silicon |
| 🍎 macOS | `openclaw-x-macos-x64` | Intel |
| 🐧 Linux | `openclaw-x-linux-x64` | x64 |
| 🪟 Windows | `openclaw-x-windows-x64.exe` | x64 |

### 2️⃣ Cookie の設定

> Chrome から X の Cookie をエクスポート

1. [x.com](https://x.com) にログイン
2. [**Cookie-Editor**](https://chromewebstore.google.com/detail/cookie-editor/hlkenndednhfkekhgcdicdfddnkalmdm) 拡張機能をインストール
3. 拡張機能アイコン → **Export** → 実行ファイルと同じディレクトリに `cookies.json` として保存

### 3️⃣ 起動

```bash
# macOS / Linux
chmod +x openclaw-x-macos-arm64
./openclaw-x-macos-arm64

# Windows
openclaw-x-windows-x64.exe
```

> 🟢 サービスは `http://localhost:19816` で起動
> 📖 API ドキュメント：`http://localhost:19816/docs`

### 4️⃣ Skill のインストール

```bash
# ClawHub 経由
npx clawhub@latest install xskill

# または手動
cp SKILL.md ~/.openclaw/skills/openclaw-x/SKILL.md
```

---

## 📡 API

| エンドポイント | メソッド | 機能 |
|:---------|:------:|:------|
| `/health` | `GET` | ヘルスチェック + ログイン状態 |
| `/timeline` | `GET` | 📰 ホームタイムライン |
| `/tweet/{id}` | `GET` | 🔍 ツイート詳細 |
| `/search?q=キーワード` | `GET` | 🔎 ツイート検索 |
| `/tweet` | `POST` | ✏️ ツイート投稿 |
| `/tweet/{id}/like` | `POST` | ❤️ いいね |
| `/tweet/{id}/retweet` | `POST` | 🔁 リツイート |
| `/tweet/{id}/bookmark` | `POST` | 🔖 ブックマーク |
| `/user/{username}` | `GET` | 👤 ユーザー情報 |
| `/user/{username}/tweets` | `GET` | 📋 ユーザーのツイート |

---

## ⚠️ 注意事項

> [!CAUTION]
> - 非公式 API を使用しており、アカウントリスクがあります
> - localhost のみでリッスン、**公開ネットワークに公開しないでください**
> - `cookies.json` には機密情報が含まれています、**漏洩しないでください**

> [!WARNING]
> **セキュリティに関する推奨事項**
> - 🛡️ メインアカウントではなく**サブアカウント**の使用を推奨
> - 📦 可能であれば**隔離環境**（コンテナ / VM）で実行してください
> - 🔐 `cookies.json` はパスワードと同様の機密情報として管理してください
> - 🚫 実行ファイルや `cookies.json` を第三者と共有しないでください

---

<div align="center">

**Sponsored by [xman.ink](https://xman.ink)** — スマート Twitter ブックマーク管理

</div>
