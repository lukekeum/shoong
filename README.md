# Shoong

---

# 프로젝트 목표

다음과 같은 주제를 학습하고 탐구하는 것을 목표로 합니다.

* RTMP 기반 송출
* HLS 기반 재생
* 실시간 스트리밍 파이프라인
* 분산 시스템 설계
* 이벤트 기반 아키텍처
* 인증(Authentication)
* 인가(Authorization)
* 실시간 통신
* 미디어 저장 및 전송
* 서비스 운영 및 관측성

---

# 전체 흐름

```text
OBS
 ↓
RTMP
 ↓
Ingest
 ↓
Transcode
 ↓
MinIO
 ↓
HLS
 ↓
Player
 ↓
Viewer
```

최종적으로는 스트리머가 OBS를 통해 방송을 송출하면, 플랫폼 내부에서 트랜스코딩과 저장 과정을 거쳐 시청자에게 HLS 형태로 전달되는 구조를 목표로 합니다.

---

# 서비스 구성

## Backend

### Node.js

* Auth Service
* User Service
* Streaming Service

### Go

* Ingest Service
* Transcode Service

### Elixir/Phoenix

* Chat Service

### Future

* AuthZ Service
* Clip Service
* VOD Service

---

# 인프라

## Database

* PostgreSQL
* Redis

## Object Storage

* MinIO

## Messaging

* Kafka (예정)

## Service Communication

* gRPC

---

# Frontend

## Main

사용자를 위한 메인 서비스

예정 기술 스택

* React
* Next.js

---

## Admin

운영 및 관리 페이지

예정 기술 스택

* React
* Apollo

---

## Design System

공통 UI 컴포넌트 및 디자인 토큰 관리

* Storybook
* Emotion

---

# Repository 구조

```text
.
├── apps
├── packages
├── proto
├── infra
├── docs
│   ├── adr
│   └── architecture
│
├── docker-compose.yml
└── pnpm-workspace.yaml
```

---

# 문서 관리

## Architecture

현재 시스템 구조와 데이터 흐름을 기록합니다.

```text
docs/architecture
```

---

## ADR

Architecture Decision Record

프로젝트 진행 과정에서 내린 주요 아키텍처 의사결정을 기록합니다.

```text
docs/adr
```
