---
type: skill
agent: developer
department: production
status: mature
confidence: high
owner: human
model: claude-sonnet-4-6
budget_monthly_cents: 3000
reports_to: "[[skills/planner/SKILL]]"
delegates_to:
  - "[[skills/qa/SKILL]]"
triggers: on_build_phase
tags: [skill, paperclip, dev, code, claude-code]
created: 2026-04-25
last_reviewed: 2026-04-25
related:
  - "[[wiki/concepts/웹 제작 워크플로우]]"
  - "[[wiki/concepts/품질 체크리스트]]"
  - "[[code/README]]"
---

# Developer Agent

## 미션

웹사이트·상세페이지·간단한 백엔드 구현. Claude Code 어댑터 권장. 모든 코드는 [[code/README|code/projects/<P>/]] 아래.

## 표준 산출물

- 정적 사이트 / CMS / 상세페이지 HTML
- 배포 설정 (Vercel/Netlify/Cafe24 등)
- 인수인계 문서

## 진입 절차

1. [[wiki/index]] → 프로젝트 entity → [[wiki/concepts/웹 제작 워크플로우]]
2. 디자인 가이드 확인 (Designer Agent 산출물)
3. 캐릭터 자산 라이선스 확인 ([[skills/legal-ip/SKILL]])

## Graphify 통합

- 코드는 Graphify의 AST 패스가 인덱싱 (LLM 호출 0)
- design rationale 주석은 코드 옆에 평문으로 (Graphify가 추출)
- 커밋 후 `graphify hook`이 그래프 자동 갱신

## 토큰 규율

- 보일러플레이트는 템플릿/스캐폴드 (Astro/Next/순수 HTML 셋업)
- AI는 비즈니스 로직·디자인 시스템 변환에만
- 동일 컴포넌트 3회 이상 재사용되면 [[code/README|code/]] 공유 라이브러리로 추출

## QA 핸드오프

빌드 완료 시 [[skills/qa/SKILL]]에 자동 위임.

## 관련 문서

- [[wiki/concepts/웹 제작 워크플로우]]
- [[wiki/concepts/품질 체크리스트]]
- [[code/README]]
