---
type: concept
status: mature
owner: human
tags: [meta, standard, schema]
created: 2026-04-25
last_reviewed: 2026-04-25
---

# Frontmatter Standard

모든 markdown 파일은 다음 YAML 프론트매터를 갖습니다. Graphify의 그래프 추출, Graph Explorer Base View 시각화, LLM Wiki 컴파일러의 maturity 추적이 모두 이 스키마에 의존합니다.

## 공통 필드

| 필드 | 타입 | 값 | 설명 |
|------|------|-----|------|
| `type` | enum | vault-root, folder-readme, template, concept, entity, skill, community, query, log | 노드 종류 |
| `status` | enum | seed, draft, substantial, mature | LLM Wiki maturity. Knowledge Manager가 갱신 |
| `confidence` | enum | low, medium, high | Graph Explorer 색깔 코딩용 |
| `owner` | string | human / agent 이름 | 누가 책임지는가 |
| `tags` | array | 자유 태그 | 검색·클러스터링 보조 |
| `created` | date | YYYY-MM-DD | 생성일 |
| `last_reviewed` | date | YYYY-MM-DD | 마지막 검토일. 6개월 이상 묵으면 stale |
| `related` | array | `[[wikilink]]` 배열 | 명시적 관계 |

## type별 추가 필드

### entity (clients, projects, characters)

| 필드 | 설명 |
|------|------|
| `entity_type` | client / project / character / license / vendor |
| `aliases` | 별칭 (그래프 머지용) |
| `parent` | 상위 entity (`[[프로젝트A]]`의 `parent: [[클라이언트X]]`) |

### skill (Paperclip 에이전트)

| 필드 | 설명 |
|------|------|
| `agent` | 에이전트 식별자 |
| `department` | production / marketing / sales / backoffice / meta |
| `model` | claude-haiku-4-5 / claude-sonnet-4-6 / claude-opus-4-7 |
| `budget_monthly_cents` | Paperclip 월 예산 한도 (센트 단위) |
| `reports_to` | `[[ceo]]` 등 |
| `delegates_to` | 하위 에이전트 배열 |
| `triggers` | heartbeat 스케줄 또는 이벤트 |

### project entity

| 필드 | 설명 |
|------|------|
| `client` | `[[클라이언트명]]` |
| `phase` | brief / design / build / launch / maintain / closed |
| `start_date`, `due_date` | 일정 |

## 예시

```yaml
---
type: entity
entity_type: project
status: substantial
confidence: high
owner: planner
tags: [web, character-design, food-and-beverage]
created: 2026-05-01
last_reviewed: 2026-05-20
client: "[[감자카페]]"
phase: design
start_date: 2026-05-01
due_date: 2026-06-15
related:
  - "[[감자카페]]"
  - "[[브랜드 보이스]]"
  - "[[캐릭터-감자군]]"
---
```

## 관련 문서

- [[README]]
- [[wiki/index]]
- [[skills/knowledge-manager/SKILL]]
