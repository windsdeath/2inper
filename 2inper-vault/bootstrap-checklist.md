---
type: concept
status: mature
owner: human
tags: [meta, onboarding, checklist]
created: 2026-04-25
last_reviewed: 2026-04-25
---

# Bootstrap Checklist

이 vault를 처음 셋업할 때의 순서. 4주 플랜에 매핑됩니다.

## 1주차 — 골격

- [ ] Obsidian에 이 vault를 열고 graph view 확인
- [ ] 코어 플러그인 활성화: Templates, Daily Notes, Backlinks, Outgoing Links
- [ ] 커뮤니티 플러그인 (선택): Dataview, Graph Explorer Base View
- [ ] [[frontmatter-standard]] 숙지
- [ ] `npm i -g graphify` 또는 Claude Code 스킬 설치
- [ ] git 저장소 초기화: `git init && git add . && git commit -m "vault bootstrap"`

## 2주차 — 자료 ingest

- [ ] 두 분이 가진 모든 자료를 [[raw/README|raw/]] 적합한 폴더로 덤프
- [ ] [[templates/README|templates/]] 따라 첫 클라이언트 1건, 첫 프로젝트 1건 시범 생성
- [ ] `graphify build --wiki` 첫 빌드
- [ ] `wiki/index.md`가 자동 갱신됐는지 확인
- [ ] [[graph/README|graph/audit.md]] 검토 (orphan, gap, 모순)

## 3주차 — 에이전트 통합

- [ ] Paperclip 설치 + 회사 생성 ("2INPER")
- [ ] [[skills/README|skills/]] 아래 21개 SKILL.md를 Paperclip에 등록
- [ ] [[skills/router/SKILL]]을 모든 작업 진입 게이트로 설정
- [ ] [[skills/ceo/SKILL]]에 두 분 직속 보고 라인 연결
- [ ] 각 에이전트 월 예산 한도 입력 (Paperclip의 `budgetMonthlyCents`)

## 4주차 — 자동화

- [ ] `graphify --watch` 백그라운드 실행
- [ ] `graphify hook install`로 git 훅 설치
- [ ] LLM Wiki 컴파일러를 Ollama 로컬 모델로 (선택)
- [ ] [[skills/knowledge-manager/SKILL|Knowledge Manager Agent]] 주간 health check 스케줄 등록
- [ ] Paperclip 대시보드에 vault health 메트릭 위젯 추가

## 관련 문서

- [[README]]
- [[skills/README]]
- [[wiki/index]]
