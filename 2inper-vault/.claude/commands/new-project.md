---
description: 새 프로젝트 entity를 생성하고 클라이언트와 연결합니다
---

다음 절차로 새 프로젝트를 등록합니다:

1. `wiki/index.md` 확인
2. `wiki/concepts/웹 제작 워크플로우.md`로 표준 단계 확인
3. 클라이언트 entity가 `raw/clients/<name>/index.md`에 존재하는지 확인. 없으면 먼저 만들지 알려주고 작업 중단
4. `templates/project-template.md`를 `raw/projects/$ARGUMENTS/index.md`로 복사
5. frontmatter:
   - `client:` 에 `[[클라이언트명]]` 정확히 wikilink로
   - `phase: brief`로 시작
   - `start_date`, `due_date` 입력
6. 산출물 체크리스트는 [[wiki/concepts/웹 제작 워크플로우]] 기반으로 기본값 채움
7. 캐릭터 작업이 포함되면 IP 분류를 frontmatter에 추가 — `(legal-ip 검토 대기)`로 표시
8. git 커밋: `raw/projects: <프로젝트명> 신규`

내가 줄 정보: $ARGUMENTS
