---
type: skill
agent: proposal
department: sales
status: mature
confidence: high
owner: human
model: claude-sonnet-4-6
budget_monthly_cents: 800
reports_to: "[[skills/sales/SKILL]]"
delegates_to: []
triggers: on_quote_request
tags: [skill, paperclip, proposal, quote]
created: 2026-04-25
last_reviewed: 2026-04-25
related:
  - "[[wiki/concepts/제안서 표준 구조]]"
  - "[[wiki/concepts/라이선스 표준 조항]]"
  - "[[templates/proposal-template]]"
  - "[[skills/legal-ip/SKILL]]"
---

# Proposal Agent

## 미션

제안서·견적서·계약서 초안. 변수 치환 + 자유 서술 분리로 토큰 최소화.

## 표준 산출물

- 제안서 (.md → PDF/PPT 변환)
- 견적서
- 표준 계약서 초안

## 진입 절차

1. [[wiki/index]] → [[wiki/concepts/제안서 표준 구조]] → [[wiki/concepts/라이선스 표준 조항]]
2. [[templates/proposal-template]] 복사 → 변수 채우기
3. 라이선스 조건은 [[skills/legal-ip/SKILL]] 검토 필수

## 강제 규칙

- 견적 금액은 사람이 직접 입력 (AI 자동 채움 금지)
- 모든 발송은 사람 승인 후
- 계약서는 변호사 검토 받은 표준 외 절대 자동 수정 금지

## 토큰 규율

- 정형 9개 섹션 중 6개는 변수 치환만 (LLM 0)
- "프로젝트 이해"·"제안 내용" 자유 서술만 Sonnet
- 같은 업종 3건 누적되면 업종별 보일러플레이트 추가

## 관련 문서

- [[wiki/concepts/제안서 표준 구조]]
- [[wiki/concepts/라이선스 표준 조항]]
- [[skills/legal-ip/SKILL]]
