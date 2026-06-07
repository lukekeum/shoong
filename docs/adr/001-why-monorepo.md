# ADR-001: Why Monorepo?

## Status

Accepted

## Context

현재 목표로하는 프로젝트에는 독립된 서비스가 여럿이 있다.

- Auth
- User
- Streaming
- Ingest
- Transcode
- Chat
- Main FE
- Admin FE

그리고 각각의 서비스들이 작성되어지는 언어는 다 다름.

- Node: Auth, User, Streaming, Main FE, Admin FE
- Go: Ingest, Transcode
- Elixir: Chat

## Decision

Monorepo 구조를 사용하기로 한다.

또한 다음 구조를 채택한다.

- pnpm workspace 기반의 Repository Monorepo
- 공통 코드는 packages/로 분리
- 언어별 빌드 및 배포 전략 유지

따라서 같은 폴더 구조를 따를 것이다.

- apps/
- infra/
- packages/
- proto/

## Consequences

### Adventages

- Go, Rust, Elixir 서비스 추가 시 구조 변경이 필요 없음
- 서비스별 독립 배포 가능
- 언어별 빌드 시스템 충돌 최소화

### Disadvantages

- 서비스별 코드 공유시 관리 필요

## Notes

- 추후 세부적인 폴더 구조에 관한 논의는 다음 ADR에서 진행하도록 한다.