---
type: folder-readme
status: mature
owner: knowledge-manager
tags: [meta, graphify, auto-generated]
created: 2026-04-25
last_reviewed: 2026-04-25
related:
  - "[[skills/knowledge-manager/SKILL]]"
  - "[[wiki/index]]"
  - "[[wiki/communities/README]]"
---

# graph/

**Graphify 자동 생성 산출물.** 사람이 편집하지 않습니다.

## 파일

- `graph.html` — 인터랙티브 시각화 (브라우저에서 열기)
- `graph.json` — 쿼리용 (에이전트는 가급적 쓰지 말 것 — 토큰 비쌈)
- `audit.md` — 감사 리포트 (orphan, frontier, 모순)

## 빌드 명령

```bash
# 전체 재빌드 (LLM 비용 발생)
graphify build --wiki

# 코드만 재빌드 (LLM 0)
graphify build --code-only

# 변경된 것만 (증분)
graphify update

# 백그라운드 watch
graphify --watch

# git 훅 설치
graphify hook install
```

## 출력 처리

`--wiki` 플래그를 켜면 Graphify가 [[wiki/communities/README|wiki/communities/]]에 community 페이지를, [[wiki/entities/README|wiki/entities/]]에 entity 페이지를 자동 생성합니다. 에이전트는 이 markdown만 읽으면 됩니다.

## audit.md 활용

[[skills/knowledge-manager/SKILL|Knowledge Manager Agent]]가 매주 수요일 22시에 자동 점검:

- **orphan** — 다른 노드와 연결 없는 고립 노드. raw에 보강 노트 필요
- **frontier** — 위키에 갭이 있어 LLM이 채울 수 있는 지점
- **contradiction** — 같은 사실에 대해 모순되는 노드들. 사람 결정 필요
- **stale** — `last_reviewed` 6개월 초과

## 관련 문서

- [[skills/knowledge-manager/SKILL]]
- [[wiki/index]]
- [[wiki/communities/README]]
- [[wiki/entities/README]]
