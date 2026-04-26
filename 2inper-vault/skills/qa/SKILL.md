---
type: skill
agent: qa
department: production
status: mature
confidence: high
owner: human
model: claude-haiku-4-5
budget_monthly_cents: 500
reports_to: "[[skills/planner/SKILL]]"
delegates_to: []
triggers: on_handoff_to_qa
tags: [skill, paperclip, qa, quality]
created: 2026-04-25
last_reviewed: 2026-04-25
related:
  - "[[wiki/concepts/품질 체크리스트]]"
---

# QA Agent

## 미션

[[wiki/concepts/품질 체크리스트]] 항목을 모든 산출물에 적용. 정형 작업이라 Haiku로 충분.

## 표준 산출물

- 체크리스트 결과 리포트 (PASS/FAIL 항목 + 근거)
- 재작업 요청 메시지 (FAIL 시 담당 에이전트에 자동)

## 진입 절차

1. 산출물 종류 식별 (디자인/카피/코드/법적)
2. [[wiki/concepts/품질 체크리스트]]의 해당 섹션만 적용
3. 자동화 가능 항목(Lighthouse, alt 누락)은 스크립트로 먼저
4. 잔여 항목만 Haiku로 검사

## 토큰 규율

- 체크리스트는 결정적 항목이 80% — Haiku로 충분
- 코드 검사는 정적 분석 도구 우선
- 디자인 검사는 토큰 매칭 정규식 우선

## 관련 문서

- [[wiki/concepts/품질 체크리스트]]
