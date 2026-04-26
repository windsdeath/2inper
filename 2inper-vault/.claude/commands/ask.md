---
description: 질의를 받고 vault 컨텍스트로 답한 뒤 wiki/queries/에 저장합니다
---

다음 절차로 질문에 답합니다:

1. **유사 query 먼저 검색** — `wiki/queries/`에서 비슷한 질문이 있었는지 grep. 있고 `last_reviewed`가 6개월 이내면 그 답을 인용 + 신선도 코멘트 추가하고 끝.
2. 없으면 진행. `wiki/index.md`에서 관련 영역 식별
3. 관련 community/concept/entity 페이지 최소한만 읽기
4. 답변 작성. 본문에 근거 wikilink를 인라인으로 박을 것
5. `wiki/queries/YYYY-MM-DD-<짧은 질문>.md`로 저장
   - 파일명의 `<짧은 질문>`은 5단어 이내, 원문에서 키워드 추출
6. frontmatter:
   - `asked_by: human`
   - `owner: <답변한 에이전트 또는 claude-code>`
   - `related: [...]` 에 본문에서 인용한 wikilink 모음
7. 콘솔에 답변 출력 + 저장 위치 알림

질문: $ARGUMENTS

토큰 규율: 같은 답이 vault에 이미 있으면 LLM 호출 없이 인용. 새 답이면 가장 짧고 명확하게.
