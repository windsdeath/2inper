---
type: vault-root
status: mature
owner: human
tags: [meta, navigation]
created: 2026-04-25
last_reviewed: 2026-04-25
---

# 2INPER Vault

캐릭터 전문 웹에이전시 **이인페르(2INPER / IINPER)**의 단일 지식 저장소입니다. Obsidian + Graphify + LLM Wiki 패턴 + Paperclip 에이전트 운영을 통합합니다.

## 운영 원칙

1. **`raw/`는 입력 전용** — LLM/에이전트는 절대 수정하지 않음. 사람과 에이전트의 자유 입력 공간.
2. **`wiki/`는 컴파일 출력** — Graphify와 LLM Wiki 컴파일러가 raw를 읽어 자동 생성/갱신.
3. **에이전트의 첫 진입점은 항상 `wiki/index.md`** — JSON 그래프 직접 파싱은 마지막 수단.
4. **모든 파일은 YAML 프론트매터를 가짐** — 표준은 [[frontmatter-standard]] 참조.
5. **변경은 git으로 추적** — Graphify의 git hook이 커밋마다 그래프 갱신.

## 폴더 안내

- [[raw/README|raw/]] — 사람·에이전트의 자유 입력. 미팅 노트, 브리프, 시안, 계약서 등.
- [[wiki/index|wiki/]] — 컴파일된 위키. **에이전트의 진입점.**
- [[code/README|code/]] — 개발 산출물. Graphify의 AST 패스 대상.
- [[skills/README|skills/]] — Paperclip 에이전트별 SKILL.md.
- [[templates/README|templates/]] — 새 엔티티 생성용 표준 템플릿.
- [[graph/README|graph/]] — Graphify 자동 생성물 (graph.html, graph.json, audit.md).

## 시작 가이드

처음 셋업이라면 [[bootstrap-checklist]]를 따라가세요.

## 관련 문서

- [[frontmatter-standard]]
- [[wiki/index]]
- [[skills/README]]
- [[bootstrap-checklist]]
