---
description: vault의 건강 상태를 점검하고 보고합니다 (Knowledge Manager 주간 루틴)
---

`skills/knowledge-manager/SKILL.md`의 주간 루틴을 수행합니다.

다음을 순서대로 진행하세요. **읽기 전용** 점검입니다 — 발견 사항은 보고만 하고 자동 수정은 하지 마세요.

## 1. Graphify 상태

- `graph/` 폴더의 마지막 빌드 시각 확인 (`graph.json` mtime)
- 마지막 빌드가 7일을 넘으면 알림: "graphify build --wiki 실행이 필요합니다"
- `graph/audit.md`가 있으면 읽고 다음을 추출:
  - **orphan** 노드 개수와 상위 5개
  - **frontier** (위키 갭) 상위 5개
  - **contradiction** 모든 항목 (있으면)

## 2. Stale 페이지 점검

`wiki/concepts/`와 `wiki/queries/`의 모든 .md 파일을 훑어:
- `last_reviewed`가 6개월(180일) 초과인 페이지 목록 → "갱신 필요"로 분류
- `status: seed`로 90일 초과 머문 페이지 → "사람 작성 필요"로 분류

## 3. 미완성 entity 점검

`raw/projects/`와 `raw/characters/` 안의 index.md를 훑어:
- frontmatter에 `client` 또는 `owner_client`가 비어있는 entity 찾기
- `(미확인)` 또는 빈 필수 필드가 있는 entity 찾기

## 4. 라이선스 만료 점검

`raw/ip-licenses/` 와 `wiki/entities/`의 license entity의 `expiry_date` 확인:
- 90일 이내 만료 → 알림
- 30일 이내 만료 → 강조 알림 (사람 즉시 확인 필요)

## 5. 보고서 생성

위 결과를 `wiki/queries/YYYY-MM-DD-vault-health.md`로 저장하고 콘솔에도 요약 출력.

frontmatter:
```yaml
---
type: query
status: substantial
confidence: high
owner: knowledge-manager
tags: [audit, vault-health, weekly]
created: <오늘>
last_reviewed: <오늘>
asked_by: human
---
```

자동 수정은 절대 하지 마세요. 모든 발견 사항은 보고로만 끝냅니다.
