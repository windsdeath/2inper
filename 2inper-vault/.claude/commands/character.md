---
description: 새 캐릭터를 vault에 등록하고 IP 분류를 안내합니다
---

`skills/character/SKILL.md` + `skills/legal-ip/SKILL.md` 기준으로 캐릭터를 등록합니다.

## 절차

1. `wiki/concepts/캐릭터 IP 가이드.md` 읽기 (IP 분류 기준 파악)
2. `wiki/concepts/캐릭터 디자인 원칙.md` 읽기
3. 같은 이름의 캐릭터가 `raw/characters/`에 이미 있는지 확인 — 있으면 중단하고 사람에게 알림
4. `templates/character-template.md`를 `raw/characters/$ARGUMENTS/index.md`로 복사
5. 제공된 정보로 채움:
   - `owner_client`: 원작자/의뢰 클라이언트 wikilink
   - `ip_type`: `original` / `licensed` / `collaboration` 중 하나
   - `legal_status`: 아직 모르면 `(legal-ip 검토 대기)`
6. **IP 분류 판단이 애매하면** 본문 끝에 다음을 붙임:
   ```
   > ⚠️ legal-ip 에이전트 검토 필요: <애매한 이유>
   ```
7. git 커밋: `raw/characters: <캐릭터명> 추가`
8. 사람에게 안내: "캐릭터 등록 완료. 클라이언트 발송 전 반드시 legal-ip 검토를 받으세요."

## 절대 하지 않는 것

- 클라이언트에게 캐릭터 시안 발송
- IP 분류 확정 (사람 + legal-ip 검토 필요)
- 라이선스 조건 해석

캐릭터 이름 및 정보: $ARGUMENTS
