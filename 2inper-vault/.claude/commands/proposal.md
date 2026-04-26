---
description: 클라이언트용 제안서 초안을 작성합니다 (사람 검수 후 발송)
---

`skills/proposal/SKILL.md` 기준으로 제안서 초안을 작성합니다.

## 절차

1. `wiki/index.md` → `wiki/concepts/제안서 표준 구조.md` 순서로 읽어 구조 파악
2. 클라이언트 entity `raw/clients/$ARGUMENTS/index.md` 확인
   - 없으면: "먼저 `/new-client <이름>`으로 클라이언트를 등록하세요" 안내 후 중단
3. 관련 프로젝트 entity `raw/projects/`에서 이 클라이언트 관련 파일 검색
4. `templates/proposal-template.md`를 `raw/projects/<프로젝트명>/proposal.md`로 복사
5. 다음 섹션을 채움:
   - **클라이언트 현황 분석** — entity에서 파악된 정보 기반
   - **제안 범위** — 요청 범위 + 우리 역량 기반
   - **예상 일정** — [[wiki/concepts/웹 제작 워크플로우]] 기준
   - **견적 항목** — 개략 항목만 (확정 금액은 사람이 채울 것)
   - **캐릭터 작업 포함 시** — `(legal-ip 검토 필요)` 표시
6. 파일 저장 후 콘솔에 경로 안내
7. **발송은 절대 하지 않습니다.** 반드시 사람 검수 후 발송.

## 주의

- 금액·일정은 사람이 최종 확인 전까지 `(TBD)`로 표시
- 이미 `proposal.md`가 있으면 덮어쓰지 말고 사람에게 알림

클라이언트명 또는 프로젝트 정보: $ARGUMENTS
