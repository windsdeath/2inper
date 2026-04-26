---
type: folder-readme
status: mature
owner: human
tags: [meta, skills, agents, paperclip]
created: 2026-04-25
last_reviewed: 2026-04-25
---

# skills/

Paperclip의 SKILLS.md 시스템에 등록되는 21개 에이전트의 정의. 각 폴더의 `SKILL.md`가 해당 에이전트의 페르소나·워크플로우·예산·진입 절차를 담습니다.

## 조직도

### 메타 레이어 (게이트키퍼)

- [[skills/router/SKILL]] — 모든 작업의 진입 게이트, "정말 LLM 필요한가?" 판정
- [[skills/knowledge-manager/SKILL]] — vault 무결성, audit, stale 관리

### 최상위

- [[skills/ceo/SKILL]] — 라우팅·의사결정·인간 에스컬레이션

### 제작팀 (Production)

- [[skills/planner/SKILL]] — 기획자
- [[skills/designer/SKILL]] — UI/UX 디자이너
- [[skills/character/SKILL]] — 캐릭터/일러스트
- [[skills/developer/SKILL]] — 개발자
- [[skills/copywriter/SKILL]] — 카피라이터
- [[skills/qa/SKILL]] — 품질관리

### 마케팅팀

- [[skills/self-marketer/SKILL]] — 자사 마케팅
- [[skills/client-marketer/SKILL]] — 고객사 마케팅
- [[skills/ad-ops/SKILL]] — 광고 운영
- [[skills/seo/SKILL]] — SEO/콘텐츠
- [[skills/internal-pr/SKILL]] — 사내 홍보·케이스스터디

### 영업·운영

- [[skills/sales/SKILL]] — 영업
- [[skills/proposal/SKILL]] — 제안서·견적
- [[skills/cs/SKILL]] — 고객 응대

### 백오피스

- [[skills/accountant/SKILL]] — 경리·회계
- [[skills/legal-ip/SKILL]] — 법무·IP
- [[skills/data-analyst/SKILL]] — 데이터 분석
- [[skills/researcher/SKILL]] — 리서치

## 공통 진입 절차

모든 에이전트는 작업 시작 시:

1. `wiki/index.md`를 먼저 읽는다
2. 작업과 관련된 community / concept / entity 페이지로만 추가 진입
3. 결과는 raw에 추가 (entity 직접 수정 금지, 단 [[skills/legal-ip/SKILL|legal-ip]] 예외)
4. 비용 한도(`budgetMonthlyCents`)를 초과하면 자동 정지

## 모델·예산 정책

[[wiki/concepts/토큰 예산 정책]] 참조.

## 관련 문서

- [[README]]
- [[wiki/concepts/토큰 예산 정책]]
- [[bootstrap-checklist]]
