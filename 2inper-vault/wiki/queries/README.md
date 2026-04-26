---
type: folder-readme
status: mature
owner: knowledge-manager
tags: [meta, wiki, queries]
created: 2026-04-25
last_reviewed: 2026-04-25
---

# wiki/queries/

에이전트나 사람이 vault에 던진 **질의와 그 답변**의 누적 아카이브. ekadetov/llm-wiki 패턴을 차용했습니다.

## 왜 누적하는가

같은 질문이 반복되면 **저장된 답변을 먼저 찾아 비교**하는 게 토큰을 가장 많이 절약합니다. 답변이 stale하면 갱신, 신선하면 그대로 사용.

## 명명 규칙

`YYYY-MM-DD-<짧은 질문>.md` — 예: `2026-05-12-감자군 굿즈 사용 가능 범위.md`

## 표준 구조

```yaml
---
type: query
status: substantial
confidence: high
owner: <답변한 에이전트>
tags: [query, ip]
created: 2026-05-12
last_reviewed: 2026-05-12
asked_by: <사람 이름 또는 에이전트>
related:
  - "[[감자군]]"
  - "[[wiki/concepts/캐릭터 IP 가이드]]"
---

## 질문
...

## 답변
...

## 출처 노드
- [[...]]
```

## 자동 만료

[[skills/knowledge-manager/SKILL|Knowledge Manager]]가 매주 query를 검토해서 6개월 이상 미참조면 archive로 이동시킵니다.

## 관련 문서

- [[wiki/index]]
- [[skills/knowledge-manager/SKILL]]
