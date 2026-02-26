# OpenClaw X

> Sponsored by [xman.ink](https://xman.ink) — 智能推特书签管理平台

让 AI Agent 操控你的 X/Twitter 账号。本地运行，零 API 费用。

## 快速开始

### 1. 下载

从 [Releases](https://github.com/bosshuman/openclaw-x/releases) 下载对应平台的可执行文件：

| 平台 | 文件 |
|------|------|
| macOS (Apple Silicon) | `openclaw-x-macos-arm64` |
| macOS (Intel) | `openclaw-x-macos-x64` |
| Linux | `openclaw-x-linux-x64` |
| Windows | `openclaw-x-windows-x64.exe` |

### 2. 配置 Cookies

从 Chrome 导出 X 的 cookies：

1. 登录 [x.com](https://x.com)
2. 安装 [Cookie-Editor](https://chromewebstore.google.com/detail/cookie-editor/hlkenndednhfkekhgcdicdfddnkalmdm) 扩展
3. 点击扩展图标 → Export → 保存为 `cookies.json` 放在可执行文件同目录

### 3. 启动

```bash
# macOS / Linux
chmod +x openclaw-x-macos-arm64
./openclaw-x-macos-arm64

# Windows
openclaw-x-windows-x64.exe
```

服务启动在 `http://localhost:19816`，API 文档：`http://localhost:19816/docs`

### 4. 配置 OpenClaw

将 `SKILL.md` 复制到 OpenClaw skills 目录：

```bash
cp SKILL.md ~/.openclaw/skills/openclaw-x/SKILL.md
```

## API 概览

| 端点 | 方法 | 功能 |
|------|------|------|
| `/health` | GET | 健康检查 |
| `/timeline` | GET | 首页时间线 |
| `/tweet/{id}` | GET | 推文详情 |
| `/search?q=关键词` | GET | 搜索推文 |
| `/tweet` | POST | 发推文 |
| `/tweet/{id}/like` | POST | 点赞 |
| `/tweet/{id}/retweet` | POST | 转推 |
| `/tweet/{id}/bookmark` | POST | 收藏 |
| `/user/{username}` | GET | 用户信息 |
| `/user/{username}/tweets` | GET | 用户推文 |

## 示例

```bash
# 获取时间线
curl http://localhost:19816/timeline

# 搜索推文
curl "http://localhost:19816/search?q=AI&count=10"

# 发推
curl -X POST http://localhost:19816/tweet \
  -H "Content-Type: application/json" \
  -d '{"text": "Hello from OpenClaw!"}'

# 点赞
curl -X POST http://localhost:19816/tweet/1234567890/like
```

## ⚠️ 注意事项

- 属于非官方 API 调用，存在账号风险
- 仅监听 localhost，请勿暴露到公网
- cookies.json 包含敏感登录信息，请勿泄露
