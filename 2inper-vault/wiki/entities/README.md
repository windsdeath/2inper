---
type: folder-readme
status: mature
owner: knowledge-manager
tags: [meta, wiki, entities, auto-generated]
created: 2026-04-25
last_reviewed: 2026-04-25
---

# wiki/entities/

**부분 자동 생성 영역.** Graphify가 raw에서 추출한 클라이언트·프로젝트·캐릭터·라이선스 entity 페이지가 여기 모입니다.

## entity 종류

- 클라이언트 entity (`entity_type: client`)
- 프로젝트 entity (`entity_type: project`)
- 캐릭터 entity (`entity_type: character`)
- 라이선스 entity (`entity_type: license`)
- 벤더 entity (`entity_type: vendor`) — 인쇄·외주 일러스트 등

## 관계 그래프 예시

```
[[감자카페]] ──client_of──→ [[감자카페 리브랜딩]] ──features──→ [[감자군]]
                                  │
                                  └──governed_by──→ [[감자군 라이선스 2026]]
```

이 그래프 덕분에 "감자군 캐릭터를 다른 클라이언트에 재사용해도 되나?" 같은 질문이 한 번의 그래프 조회로 답변됩니다.

## 주의

이 폴더에 직접 새 파일을 만들지 마세요. Entity는 **항상 raw에서 시작**해서 컴파일러가 여기로 옮기거나 요약합니다.

예외: [[skills/legal-ip/SKILL|법무/IP Agent]]가 `entities/` 직접 갱신 권한을 가집니다 (계약 변경 즉시 반영을 위해).

## 관련 문서

- [[wiki/index]]
- [[raw/README]]
- [[skills/legal-ip/SKILL]]
- [[skills/knowledge-manager/SKILL]]
