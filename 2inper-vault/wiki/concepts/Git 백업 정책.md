---
type: concept
status: mature
owner: human
tags: [meta, git, backup, safety]
created: 2026-04-26
last_reviewed: 2026-04-26
related:
  - "[[bootstrap-checklist]]"
  - "[[CLAUDE]]"
---

# Git 백업 정책

이 vault는 git에 올라가 있고, 다음 세 층의 자동 백업·보호 장치를 갖습니다.

## 1층 — Obsidian Git 플러그인 (사람 편집)

두 분이 Obsidian에서 편집하는 동안 **타이머 기반 자동 커밋**.

### 설치

1. Obsidian 설정 → 커뮤니티 플러그인 → 탐색
2. "Obsidian Git" (제작자: Vinzent03) 검색·설치·활성화
3. 플러그인 설정:
   - **Vault backup interval (minutes)**: `10`
   - **Auto pull on startup**: 켬
   - **Auto push after commit**: 켬
   - **Commit message**: `obsidian: vault backup {{date}}` (타임스탬프 자동 삽입)
   - **Disable notifications**: 취향대로

### 효과

- Obsidian 열려있는 동안 10분마다 자동 커밋·푸시
- 다른 기기에서 시작 시 자동 pull → 두 분이 동시에 작업해도 충돌 최소화
- 충돌 나면 Obsidian이 직접 알려줌

## 2층 — Claude Code 작업 단위 커밋

[[CLAUDE]]에 박힌 규칙: Claude Code는 logical task 끝날 때마다 커밋합니다. `raw/clients: 감자카페 추가` 같은 의미 단위 메시지로.

이게 file-by-file 자동 커밋보다 좋은 이유: **나중에 되돌릴 때 의미 단위로 끊어진 히스토리가 훨씬 유용**합니다.

## 3층 — Pre-commit hook (보호 폴더 차단)

[[scripts/git-hooks/README|pre-commit hook]]이 다음 폴더에 대한 직접 수정을 차단:

- `wiki/concepts/` — LLM Wiki 컴파일러만 본문 수정
- `wiki/communities/` — Graphify만
- `wiki/entities/` — Graphify + legal-ip만
- `graph/` — Graphify만
- `skills/*/SKILL.md` — 사람만, 신중히
- `templates/` — 사람만, 신중히

우회는 커밋 메시지 prefix(`compiler:`, `graphify:`, `legal-ip:`, `knowledge-manager:`, `human-override:`)로만 가능합니다. Claude Code도 이 prefix 없이는 보호 폴더를 못 바꿉니다.

### 설치 (vault 클론한 모든 머신에서 1회)

```bash
git config core.hooksPath scripts/git-hooks
chmod +x scripts/git-hooks/*
```

## 위험 작업은 브랜치에서

리스크 큰 변경(예: 컨셉 페이지 대규모 재작성, 스킬 정의 개편)은 `main`에서 직접 하지 말고 브랜치 만들어서:

```bash
git checkout -b experiment/concept-rewrite
# Claude Code로 작업
git push -u origin experiment/concept-rewrite
# 결과 검토 후 main에 merge
```

브랜치에서는 post-commit hook이 자동 push 안 하므로 안전합니다.

## 복구 시나리오

### 실수로 파일 망가졌을 때 (커밋 전)

```bash
git checkout -- <파일경로>   # 마지막 커밋 상태로 복원
```

### 잘못된 커밋 한 후 (push 전)

```bash
git reset --soft HEAD~1      # 커밋 취소, 변경은 유지
git reset --hard HEAD~1      # 커밋·변경 모두 폐기 (위험)
```

### 잘못된 커밋이 push까지 됐을 때

```bash
git revert <커밋해시>         # 새 커밋으로 변경을 되돌림 (히스토리 보존)
```

force push (`git push -f`)는 절대 사용 금지 — 두 분의 작업 충돌 위험이 큽니다.

## 점검

[[skills/knowledge-manager/SKILL|Knowledge Manager Agent]]가 매주 `/vault-health` 실행 시 다음을 함께 점검:
- 마지막 push 시각이 7일 초과면 알림
- 보호 폴더에 prefix 없이 들어온 커밋이 있는지 (보안 감사)

## 관련 문서

- [[CLAUDE]]
- [[bootstrap-checklist]]
- [[scripts/git-hooks/README]]
- [[skills/knowledge-manager/SKILL]]
