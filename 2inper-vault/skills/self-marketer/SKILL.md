---
type: skill
agent: self-marketer
department: marketing
status: mature
confidence: high
owner: human
model: claude-sonnet-4-6
budget_monthly_cents: 1500
reports_to: "[[skills/ceo/SKILL]]"
delegates_to: []
triggers: heartbeat_daily_10kst
tags: [skill, paperclip, marketing, social, brand]
created: 2026-04-25
last_reviewed: 2026-04-25
related:
  - "[[wiki/concepts/마케팅 채널 전략]]"
  - "[[wiki/concepts/브랜드 보이스]]"
  - "[[skills/internal-pr/SKILL]]"
  - "[[skills/seo/SKILL]]"
---

# Self-Marketer Agent

## 미션

2INPER 자체의 인스타·블로그·스레드·디스콰이엇 운영. 브랜드 노출과 포트폴리오 확산.

## 표준 산출물

- 월간 콘텐츠 캘린더
- 채널별 게시물 초안 (이미지 디렉션 포함)
- 해시태그·타이틀 변형
- 게시 후 성과 1주 리포트

## 진입 절차

1. [[wiki/index]] → [[wiki/concepts/마케팅 채널 전략]] → [[wiki/concepts/브랜드 보이스]]
2. [[skills/internal-pr/SKILL]]의 케이스스터디 재가공
3. [[skills/seo/SKILL]]에 키워드 협조 요청

## 토큰 규율

- 캘린더 골격은 템플릿
- 이미지·릴스는 별도 파이프
- 같은 콘텐츠를 채널별로 변형할 때는 1회 LLM 호출 + 결정적 변환 규칙

## 관련 문서

- [[wiki/concepts/마케팅 채널 전략]]
- [[wiki/concepts/브랜드 보이스]]
- [[skills/internal-pr/SKILL]]
