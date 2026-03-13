<div align="center">

<img src="assets/cover.png" alt="OpenClaw X" width="600" />

# 🦅 OpenClaw X

**AI Agent로 X/Twitter 계정을 제어하세요**

로컬 실행 · API 비용 제로 · 프라이버시 보호

[![Release](https://img.shields.io/github/v/release/bosshuman/openclaw-x?style=flat-square&color=00c853)](https://github.com/bosshuman/openclaw-x/releases)
[![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Linux%20%7C%20Windows-blue?style=flat-square)](https://github.com/bosshuman/openclaw-x/releases)
[![ClawHub](https://img.shields.io/badge/ClawHub-openclaw--x-orange?style=flat-square)](https://clawhub.ai/bosshuman/openclaw-x)
[![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)](LICENSE)

[English](README.md) · [中文](README_CN.md) · [日本語](README_JA.md) · **한국어**

</div>

---

## ✨ 특징

- 🤖 **AI 네이티브** — OpenClaw Agent 전용 Skill
- 🔒 **로컬 실행** — 데이터가 외부로 전송되지 않으며 `localhost` 에서만 동작
- 🍪 **쿠키 인증** — 브라우저 쿠키 사용, API Key 불필요
- ⚡ **제로 설정** — 다운로드 후 바로 실행
- 🌍 **크로스 플랫폼** — macOS / Linux / Windows

---

## 🚀 빠른 시작

### 1️⃣ 다운로드

[**Releases**](https://github.com/bosshuman/openclaw-x/releases)에서 플랫폼에 맞는 실행 파일을 다운로드:

| 플랫폼 | 파일 | 아키텍처 |
|:------:|:-----|:-------:|
| 🍎 macOS | `openclaw-x-macos-arm64` | Apple Silicon |
| 🍎 macOS | `openclaw-x-macos-x64` | Intel |
| 🐧 Linux | `openclaw-x-linux-x64` | x64 |
| 🪟 Windows | `openclaw-x-windows-x64.exe` | x64 |

### 2️⃣ 쿠키 설정

> Chrome에서 X 쿠키를 내보내기

1. [x.com](https://x.com)에 로그인
2. [**Cookie-Editor**](https://chromewebstore.google.com/detail/cookie-editor/hlkenndednhfkekhgcdicdfddnkalmdm) 확장 프로그램 설치
3. 확장 프로그램 아이콘 → **Export** → 실행 파일과 같은 디렉토리에 `cookies.json`으로 저장

### 3️⃣ 실행

```bash
# macOS / Linux
chmod +x openclaw-x-macos-arm64
./openclaw-x-macos-arm64

# Windows
openclaw-x-windows-x64.exe
```

> 🟢 서비스: `http://localhost:19816`
> 📖 API 문서: `http://localhost:19816/docs`

### 4️⃣ Skill 설치

```bash
# ClawHub를 통해
npx clawhub@latest install openclaw-x

# 또는 수동으로
cp SKILL.md ~/.openclaw/skills/openclaw-x/SKILL.md
```

---

## 📡 API

| 엔드포인트 | 메서드 | 기능 |
|:---------|:------:|:------|
| `/health` | `GET` | 상태 확인 + 로그인 상태 |
| `/timeline` | `GET` | 📰 홈 타임라인 |
| `/tweet/{id}` | `GET` | 🔍 트윗 상세 |
| `/search?q=키워드` | `GET` | 🔎 트윗 검색 |
| `/tweet` | `POST` | ✏️ 트윗 작성 |
| `/tweet/{id}/like` | `POST` | ❤️ 좋아요 |
| `/tweet/{id}/retweet` | `POST` | 🔁 리트윗 |
| `/tweet/{id}/bookmark` | `POST` | 🔖 북마크 |
| `/user/{username}` | `GET` | 👤 사용자 정보 |
| `/user/{username}/tweets` | `GET` | 📋 사용자 트윗 |

---

## ⚠️ 주의사항

> [!CAUTION]
> - 비공식 API를 사용하므로 계정 위험이 있을 수 있습니다
> - localhost에서만 수신, **공용 네트워크에 노출하지 마세요**
> - `cookies.json`에는 민감한 정보가 포함, **유출하지 마세요**

> [!WARNING]
> **보안 권장사항**
> - 🛡️ 메인 계정 대신 **부계정** 사용을 권장합니다
> - 📦 가능하면 **격리된 환경**(컨테이너 / VM)에서 실행하세요
> - 🔐 `cookies.json`은 비밀번호와 동일하게 관리하세요 — 전체 계정 접근 권한을 부여합니다
> - 🚫 실행 파일이나 `cookies.json`을 타인과 공유하지 마세요

---

<div align="center">

**Sponsored by [xman.ink](https://xman.ink)** — 스마트 트위터 북마크 관리

</div>
