---
name: openclaw-x
description: 操控你的 X/Twitter 账号——查看时间线、搜索推文、发推、点赞、转推、收藏。
---

# OpenClaw X

通过本地 API 操控你的 X/Twitter 账号。

## 前置要求

1. 确保 openclaw-x 服务已启动：`http://localhost:19816`
2. 如未启动，进入 openclaw-x 目录执行 `python main.py`

## 可用操作

### 1. 获取首页时间线

```bash
curl http://localhost:19816/timeline?count=20
```

返回最新的推文列表，包含内容、作者、媒体 URL 等。

### 2. 获取推文详情

```bash
curl http://localhost:19816/tweet/{tweet_id}
```

支持传入推文 ID 或完整 URL（如 `https://x.com/user/status/123456`）。

### 3. 搜索推文

```bash
curl "http://localhost:19816/search?q=关键词&sort=Latest&count=20"
```

参数：
- `q`：搜索关键词（必填）
- `sort`：`Latest`（最新）或 `Top`（热门），默认 Latest
- `count`：结果数量，默认 20

### 4. 发推文

```bash
curl -X POST http://localhost:19816/tweet \
  -H "Content-Type: application/json" \
  -d '{"text": "你好世界"}'
```

回复推文：

```bash
curl -X POST http://localhost:19816/tweet \
  -H "Content-Type: application/json" \
  -d '{"text": "回复内容", "reply_to": "原推文ID"}'
```

### 5. 点赞推文

```bash
curl -X POST http://localhost:19816/tweet/{tweet_id}/like
```

### 6. 转推

```bash
curl -X POST http://localhost:19816/tweet/{tweet_id}/retweet
```

### 7. 收藏推文

```bash
curl -X POST http://localhost:19816/tweet/{tweet_id}/bookmark
```

### 8. 获取用户信息

```bash
curl http://localhost:19816/user/{username}
```

返回用户名、头像、简介、粉丝数等。

### 9. 获取用户推文

```bash
curl http://localhost:19816/user/{username}/tweets?count=20
```

## 常见使用场景

1. "帮我看看我的时间线有什么新推"
2. "搜索关于 AI Agent 的最新推文"
3. "发一条推文说：今天天气真好"
4. "帮我点赞这条推文 https://x.com/xxx/status/123"
5. "看看 @elonmusk 最近发了什么"
6. "帮我收藏这条推文"
