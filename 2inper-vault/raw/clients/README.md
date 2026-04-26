---
type: folder-readme
status: mature
owner: human
tags: [meta, raw, clients]
created: 2026-04-25
last_reviewed: 2026-04-25
---

# raw/clients/

클라이언트별 폴더를 만들고, 그 안에 미팅 노트·브리프·요청사항·연락처 메모 등 1차 자료를 모읍니다.

## 폴더 구조 권장

```
clients/
├── <클라이언트명>/
│   ├── 2026-05-12-1차미팅.md
│   ├── brief.md
│   ├── contact.md
│   └── attachments/
│       └── 화이트보드.jpg
```

## 새 클라이언트 추가 시

[[templates/client-template|클라이언트 템플릿]]을 복사해 `<클라이언트명>/index.md`로 저장하세요. Graphify가 이를 entity 노드로 추출합니다.

## 관련 문서

- [[raw/README]]
- [[templates/client-template]]
- [[wiki/entities/README]]
