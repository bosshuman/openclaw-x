---
name: openclaw-x
version: 0.1.0
description: X/Twitter 계정을 제어 — 타임라인 보기, 트윗 검색, 게시, 좋아요, 리트윗, 북마크.
---

# OpenClaw X

로컬 API로 X/Twitter 계정을 제어합니다.

## 사전 요구사항

1. [GitHub Release](https://github.com/bosshuman/openclaw-x/releases)에서 실행 파일 다운로드
2. Chrome에서 X 쿠키 내보내기 (Cookie-Editor 확장 프로그램 사용), `cookies.json`으로 같은 디렉토리에 저장
3. 실행 파일 실행, 서비스가 `http://localhost:19816`에서 작동 확인

## 사용 가능한 작업

### 1. 홈 타임라인 가져오기

```bash
curl http://localhost:19816/timeline?count=20
```

### 2. 트윗 상세 보기

```bash
curl http://localhost:19816/tweet/{tweet_id}
```

트윗 ID 또는 전체 URL 지원 (예: `https://x.com/user/status/123456`).

### 3. 트윗 검색

```bash
curl "http://localhost:19816/search?q=키워드&sort=Latest&count=20"
```

매개변수:
- `q`: 검색 키워드 (필수)
- `sort`: `Latest` (최신) 또는 `Top` (인기), 기본값 Latest
- `count`: 결과 수, 기본값 20

### 4. 트윗 작성

```bash
curl -X POST http://localhost:19816/tweet \
  -H "Content-Type: application/json" \
  -d '{"text": "안녕하세요"}'
```

답글:

```bash
curl -X POST http://localhost:19816/tweet \
  -H "Content-Type: application/json" \
  -d '{"text": "답글 내용", "reply_to": "원래_트윗_ID"}'
```

### 5. 좋아요

```bash
curl -X POST http://localhost:19816/tweet/{tweet_id}/like
```

### 6. 리트윗

```bash
curl -X POST http://localhost:19816/tweet/{tweet_id}/retweet
```

### 7. 북마크

```bash
curl -X POST http://localhost:19816/tweet/{tweet_id}/bookmark
```

### 8. 사용자 정보 가져오기

```bash
curl http://localhost:19816/user/{username}
```

### 9. 사용자 트윗 가져오기

```bash
curl http://localhost:19816/user/{username}/tweets?count=20
```

## 자주 사용하는 예시

1. "내 타임라인에 새로운 트윗이 있는지 보여줘"
2. "AI Agent에 대한 최신 트윗을 검색해줘"
3. "'오늘 날씨가 정말 좋다'라고 트윗해줘"
4. "이 트윗에 좋아요 눌러줘 https://x.com/xxx/status/123"
5. "@elonmusk이 최근에 뭘 올렸는지 봐줘"
6. "이 트윗을 북마크해줘"
