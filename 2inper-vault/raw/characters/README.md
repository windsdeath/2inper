---
type: folder-readme
status: mature
owner: human
tags: [meta, raw, characters, ip]
created: 2026-04-25
last_reviewed: 2026-04-25
---

# raw/characters/

2INPER가 만들거나 다루는 모든 캐릭터의 1차 자료. **2INPER의 핵심 차별화 영역**이므로 가장 풍부하게 채워져야 합니다.

## 폴더 구조 권장

```
characters/
├── <캐릭터명>/
│   ├── index.md                  ← templates/character-template 기반
│   ├── concept-notes.md          ← 컨셉, 성격, 세계관
│   ├── design-rationale.md       ← 디자인 결정 이유
│   ├── usage-guide.md            ← 사용 가이드 (브랜드북)
│   ├── reference/                ← 레퍼런스 이미지
│   ├── final/                    ← 최종 시안 (PNG, AI, PSD)
│   └── variants/                 ← 표정·포즈·컬러 변형
```

## 캐릭터 entity의 중요 필드

- `owner_client`: 캐릭터 IP 소유자 (2INPER 자체 / 클라이언트)
- `license_scope`: 사용 범위 (웹 한정 / 굿즈 포함 / 상업 무제한)
- `related_projects`: 이 캐릭터가 등장하는 프로젝트들

[[skills/legal-ip/SKILL|법무/IP Agent]]가 이 정보를 IP 그래프로 추적합니다.

## 관련 문서

- [[raw/README]]
- [[templates/character-template]]
- [[wiki/concepts/캐릭터 IP 가이드]]
- [[skills/character/SKILL]]
- [[skills/legal-ip/SKILL]]
