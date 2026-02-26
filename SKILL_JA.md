---
name: openclaw-x
version: 0.1.0
description: X/Twitterアカウントを操作——タイムライン閲覧、ツイート検索、投稿、いいね、リツイート、ブックマーク。
---

# OpenClaw X

ローカルAPIでX/Twitterアカウントを操作。

## 前提条件

1. [GitHub Release](https://github.com/bosshuman/openclaw-x/releases) から実行ファイルをダウンロード
2. ChromeからXのCookieをエクスポート（Cookie-Editor拡張機能を使用）、`cookies.json` として同ディレクトリに保存
3. 実行ファイルを起動、サービスが `http://localhost:19816` で動作していることを確認

## 利用可能な操作

### 1. ホームタイムラインの取得

```bash
curl http://localhost:19816/timeline?count=20
```

### 2. ツイート詳細の取得

```bash
curl http://localhost:19816/tweet/{tweet_id}
```

ツイートIDまたは完全なURL（例：`https://x.com/user/status/123456`）に対応。

### 3. ツイート検索

```bash
curl "http://localhost:19816/search?q=キーワード&sort=Latest&count=20"
```

パラメータ：
- `q`：検索キーワード（必須）
- `sort`：`Latest`（最新）または `Top`（人気）、デフォルト Latest
- `count`：結果数、デフォルト 20

### 4. ツイート投稿

```bash
curl -X POST http://localhost:19816/tweet \
  -H "Content-Type: application/json" \
  -d '{"text": "こんにちは世界"}'
```

リプライ：

```bash
curl -X POST http://localhost:19816/tweet \
  -H "Content-Type: application/json" \
  -d '{"text": "返信内容", "reply_to": "元のツイートID"}'
```

### 5. いいね

```bash
curl -X POST http://localhost:19816/tweet/{tweet_id}/like
```

### 6. リツイート

```bash
curl -X POST http://localhost:19816/tweet/{tweet_id}/retweet
```

### 7. ブックマーク

```bash
curl -X POST http://localhost:19816/tweet/{tweet_id}/bookmark
```

### 8. ユーザー情報の取得

```bash
curl http://localhost:19816/user/{username}
```

### 9. ユーザーのツイート取得

```bash
curl http://localhost:19816/user/{username}/tweets?count=20
```

## よくある使い方

1. 「タイムラインの新しいツイートを見せて」
2. 「AI Agentについての最新ツイートを検索して」
3. 「『今日はいい天気だ』とツイートして」
4. 「このツイートをいいねして https://x.com/xxx/status/123」
5. 「@elonmusk の最近の投稿を見せて」
6. 「このツイートをブックマークして」
