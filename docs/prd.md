# 🧠 SupaChat PRD

Supabase + Next.js + Bun 기반의 실시간 양방향 챗봇 MVP 제품 요구사항 문서입니다.

---

## 📌 개요

| 항목        | 내용                                                          |
| ----------- | ------------------------------------------------------------- |
| 프로젝트명  | SupaChat                                                      |
| 목적        | Supabase와 Next.js (Bun 런타임)을 활용한 실시간 챗봇 MVP 구현 |
| 핵심 가치   | 빠른 구현, 실시간 응답, 간결한 구조                           |
| 대상 사용자 | 개발 테스트 사용자, 사내 PoC 용도                             |

---

## 🎯 핵심 기능

### ✅ 구현 대상

- 사용자 메시지 입력
- Supabase DB에 메시지 저장
- Supabase Realtime을 통한 실시간 수신
- 기본적인 채팅 UI 구성

---

## ⚙️ 기술 스택

| 계층         | 도구              | 설명                   |
| ------------ | ----------------- | ---------------------- |
| 프레임워크   | Next.js 14        | App Router 기반        |
| 런타임       | Bun               | 빠른 개발 및 실행 속도 |
| 데이터베이스 | Supabase          | PostgreSQL + Realtime  |
| 실시간 처리  | Supabase Realtime | `messages` 테이블 기반 |
| UI 스타일    | Tailwind CSS      | 빠른 스타일링          |
| 배포         | Vercel            | 환경변수 사용          |

---

## 🧱 데이터베이스 스키마

### 📄 `messages` 테이블

| 필드명     | 타입        | 설명            |
| ---------- | ----------- | --------------- |
| id         | uuid (PK)   | 고유 ID         |
| role       | text        | 'user' or 'bot' |
| content    | text        | 메시지 본문     |
| created_at | timestamptz | 생성 시간       |

---

## 🖼️ UI 구성

- 메시지 말풍선 형태 (역할에 따라 스타일 차등)
- 하단 입력창 + 전송 버튼
- 메시지는 최신 순 정렬
- 반응형 UI

---

## 🔁 사용자 흐름

```
[홈 접속]
  ↓
[입력창에 메시지 입력 → Supabase 저장]
  ↓
[Realtime으로 사용자 메시지 렌더링]
  ↓
[챗봇 메시지 실시간 표시]
```

---

## 🔜 향후 고도화 아이디어

- 사용자 인증 및 대화 세션 분리
- 챗봇 답변 스트리밍 (SSE)
- RAG 구조 확장
- 관리자 로그 조회 기능

---
