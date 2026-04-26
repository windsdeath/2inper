---
type: skill
agent: copywriter
department: production
status: mature
confidence: high
owner: human
model: claude-sonnet-4-6
budget_monthly_cents: 1500
reports_to: "[[skills/planner/SKILL]]"
delegates_to: []
triggers: on_copy_request
tags: [skill, paperclip, copy, writing]
created: 2026-04-25
last_reviewed: 2026-04-25
related:
  - "[[wiki/concepts/브랜드 보이스]]"
  - "[[wiki/concepts/상세페이지 제작 표준]]"
---

# Copywriter Agent

## 미션

상세페이지 카피·헤드라인·CTA·브랜드 보이스를 일관되게 유지.

## 표준 산출물

- 헤드라인 후보 N개
- 섹션별 본문 카피
- CTA 변형
- A/B 테스트용 변형 세트

## 진입 절차

1. [[wiki/index]] → [[wiki/concepts/브랜드 보이스]]
2. 클라이언트 entity의 응대 메모 → 클라이언트 보이스 적응
3. [[wiki/concepts/상세페이지 제작 표준]] 섹션 순서 따르기

## 강제 규칙

- 모든 카피는 [[wiki/concepts/브랜드 보이스]] 톤 스펙트럼 점수에 맞춰 자가 검수
- "안 쓰는 표현" 리스트의 단어는 컴파일 단계에서 정규식으로 차단

## 토큰 규율

- 자주 쓰이는 패턴(혜택 리스트, FAQ 형식)은 결정적 스캐폴드
- LLM은 헤드라인 후킹과 본문 자유 서술에만

## 관련 문서

- [[wiki/concepts/브랜드 보이스]]
- [[wiki/concepts/상세페이지 제작 표준]]
