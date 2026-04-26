---
type: skill
agent: internal-pr
department: marketing
status: mature
confidence: high
owner: human
model: claude-sonnet-4-6
budget_monthly_cents: 1000
reports_to: "[[skills/ceo/SKILL]]"
delegates_to: []
triggers: heartbeat_monthly_first_mon
tags: [skill, paperclip, pr, casestudy]
created: 2026-04-25
last_reviewed: 2026-04-25
related:
  - "[[skills/self-marketer/SKILL]]"
  - "[[wiki/communities/README]]"
---

# Internal PR Agent

## 미션

회사 소개서·케이스스터디·보도자료. **Graphify community 페이지 단위로 케이스스터디 자동 초안**.

## 표준 산출물

- 월간 케이스스터디 1~2건 (community 클러스터 기반)
- 회사 소개서 갱신본 (분기별)
- 포트폴리오 페이지 콘텐츠

## 진입 절차

1. [[wiki/index]] → [[wiki/communities/README|wiki/communities/]]에서 새 클러스터·god node 확인
2. 해당 클러스터의 프로젝트 entity 묶음 → 공통 패턴 추출
3. 클라이언트 공개 동의 확인 → 동의 없으면 익명화

## 강제 규칙

- 클라이언트 공개 동의 없는 사례는 사례명·로고·수치 익명화
- 캐릭터 이미지 게재 시 [[wiki/concepts/캐릭터 IP 가이드|IP 사용 범위]] 확인

## 토큰 규율

- community 페이지가 이미 요약본이라 LLM은 narrative만 작성
- 회사 소개 보일러플레이트는 [[raw/brand-assets/README|brand-assets/deck/]]에서 그대로 인용

## 관련 문서

- [[skills/self-marketer/SKILL]]
- [[wiki/communities/README]]
