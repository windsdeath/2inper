# scripts/git-hooks

이 폴더의 git 훅들은 **버전 관리되는 훅**입니다. 일반적으로 git 훅은 `.git/hooks/`에 들어가서 동기화가 안 되지만, 여기 있는 훅들은 vault에 함께 다니므로 두 분 다 같은 보호를 받습니다.

## 한 번만 실행: 활성화

```bash
git config core.hooksPath scripts/git-hooks
chmod +x scripts/git-hooks/*
```

이 명령은 vault를 클론한 모든 머신에서 한 번씩 실행해야 합니다. (두 분의 노트북 각각, 그리고 우분투 서버.)

## 훅 목록

### `pre-commit`

보호 폴더(`wiki/concepts/`, `wiki/communities/`, `wiki/entities/`, `graph/`, `skills/*/SKILL.md`, `templates/`) 직접 수정을 차단합니다.

우회가 필요한 경우 커밋 메시지를 다음 prefix로 시작:
- `compiler:` — LLM Wiki 컴파일러 빌드 결과
- `graphify:` — Graphify 빌드 결과  
- `legal-ip:` — legal-ip 에이전트의 entity 갱신
- `knowledge-manager:` — KM 에이전트의 메타데이터 갱신
- `human-override:` — 사람이 책임지고 직접 수정

### `post-commit`

커밋 성공 시 origin으로 자동 push (main/master 브랜치만, 백그라운드).

`NO_AUTO_PUSH=1` 환경변수로 끌 수 있습니다.

## Obsidian Git 플러그인과의 관계

Obsidian Git 플러그인이 자동 커밋할 때도 이 훅들이 적용됩니다. 만약 두 분이 Obsidian에서 보호 폴더를 잘못 건드리면, 플러그인의 다음 자동 커밋이 거부됩니다 — 이게 정확히 우리가 원하는 동작입니다.

## 디버깅

훅이 발동 안 한다고 의심되면:

```bash
git config --get core.hooksPath  # → scripts/git-hooks 가 나와야 함
ls -la scripts/git-hooks/         # 실행 권한(x) 확인
```

훅을 일시적으로 비활성화하려면:

```bash
git commit --no-verify -m "..."   # pre-commit 우회 (위급 시만)
```
