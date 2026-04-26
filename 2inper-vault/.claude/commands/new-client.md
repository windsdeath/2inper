---
description: 새 클라이언트 entity를 생성합니다
---

다음 절차로 새 클라이언트를 vault에 등록합니다:

1. `wiki/index.md`를 먼저 읽어 vault 컨텍스트 확인
2. `wiki/concepts/타겟 고객.md`을 읽어 우리 타겟에 맞는 클라이언트인지 점검
3. `templates/client-template.md`를 복사해 `raw/clients/$ARGUMENTS/index.md`로 저장
4. frontmatter의 `created`, `last_reviewed`를 오늘 날짜로 갱신
5. 제공된 정보로 채울 수 있는 필드를 채우고, 채울 수 없는 필드는 `(미확인)`으로 표시
6. 파일 생성 완료 후 git에 커밋: `raw/clients: <클라이언트명> 추가`

작업 시 주의:
- 클라이언트명에 공백이 있으면 폴더명은 그대로 두되 wikilink가 깨지지 않게 frontmatter `aliases`에 변형 등록
- 결제·세금계산서 정보는 입력 시 사람에게 한 번 더 확인
- 같은 이름이 이미 있으면 덮어쓰지 말고 사람에게 알림

내가 줄 정보: $ARGUMENTS
