---
type: folder-readme
status: mature
owner: developer
tags: [meta, code]
created: 2026-04-25
last_reviewed: 2026-04-25
related:
  - "[[skills/developer/SKILL]]"
  - "[[graph/README]]"
---

# code/

개발 산출물. **Graphify의 AST 패스 대상**이라 LLM 호출 없이 인덱싱됩니다.

## 폴더 구조

```
code/
└── projects/
    └── <프로젝트명>/
        ├── README.md
        ├── src/
        ├── public/
        └── package.json
```

## 지원 언어 (Graphify tree-sitter)

Python, JS, TS, Go, Rust, Java, C, C++, Ruby, C#, Kotlin, Scala, PHP, Swift, Lua, Zig, PowerShell, Elixir, Objective-C, Julia, Verilog, SystemVerilog, Vue, Svelte, Dart — 25개 언어. 2INPER에서는 주로 TS/JS/Vue/Svelte.

## 디자인 결정 주석

코드 옆 주석에 **왜 이렇게 만들었는지(rationale)**를 평문으로 적으세요. Graphify가 `design_rationale` 엣지로 추출해 그래프에 반영합니다. 같은 이슈가 6개월 후 다시 와도 답변이 자동 검색됩니다.

```ts
// rationale: 클라이언트가 모바일 트래픽 80%라서 SSR 대신 정적 생성 선택
// (related: [[프로젝트A]] 2026-05-12 미팅)
```

## Git 훅

`graphify hook install` 후 모든 커밋이 그래프 자동 갱신을 트리거합니다.

## 관련 문서

- [[skills/developer/SKILL]]
- [[graph/README]]
