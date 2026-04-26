---
type: folder-readme
status: mature
owner: human
tags: [meta, raw, projects]
created: 2026-04-25
last_reviewed: 2026-04-25
---

# raw/projects/

프로젝트 단위 자료 덤프. 한 클라이언트가 여러 프로젝트를 가질 수 있으므로 클라이언트와 분리합니다.

## 폴더 구조 권장

```
projects/
├── <프로젝트명>/
│   ├── index.md                  ← templates/project-template 기반
│   ├── requirements.md
│   ├── revisions/
│   ├── deliverables/
│   └── attachments/
```

## 새 프로젝트 추가 시

1. [[templates/project-template]]을 복사해 `<프로젝트명>/index.md`로 저장
2. frontmatter의 `client:`에 [[클라이언트 entity]]를 wikilink로 연결
3. 코드가 생기면 [[code/README|code/projects/<프로젝트명>/]]에 별도 저장

## 관련 문서

- [[raw/README]]
- [[raw/clients/README]]
- [[templates/project-template]]
- [[code/README]]
