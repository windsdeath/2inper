---
type: concept
status: draft
confidence: medium
owner: legal-ip
tags: [ip, legal, character, license]
created: 2026-04-25
last_reviewed: 2026-04-25
related:
  - "[[wiki/concepts/라이선스 표준 조항]]"
  - "[[raw/ip-licenses/README]]"
  - "[[skills/legal-ip/SKILL]]"
  - "[[skills/character/SKILL]]"
---

# 캐릭터 IP 가이드

캐릭터 비즈니스의 가장 큰 리스크와 가장 큰 가치는 **저작권/상표권의 명확한 정리**에서 나옵니다. 이 문서는 모든 캐릭터 작업의 기본 원칙입니다.

## 소유 구분

캐릭터는 항상 다음 중 하나로 분류됩니다.

| 구분 | 의미 | 결과물 사용 가능 범위 |
|------|------|----------------------|
| 2INPER 자체 IP | 우리가 만들고 우리가 소유 | 자유롭게 재사용 가능 |
| 클라이언트 양도 | 작업 후 클라이언트에 완전 양도 | **재사용 절대 금지** |
| 클라이언트 사용허락 | 우리가 소유, 특정 범위만 허락 | 허락 범위 내 재사용 가능 |
| 외주 작가 IP | 작가가 소유, 우리는 중개 | 작가 동의 필요 |

모든 캐릭터 entity의 `owner_client` 필드에 이 구분이 들어가야 합니다.

## 필수 계약 조항 체크리스트

새 캐릭터 작업 계약 시 [[wiki/concepts/라이선스 표준 조항]] 참조.

- [ ] 양도 vs 사용허락 명시
- [ ] 사용 매체 (웹/인쇄/굿즈/영상/AR/메타버스)
- [ ] 사용 지역
- [ ] 기간
- [ ] 수정·2차 창작 권한
- [ ] AI 학습 데이터 사용 가부
- [ ] 위반 시 손해배상 조항
- [ ] 작가 크레딧 표기 의무

## 위험 신호

다음이 발견되면 [[skills/legal-ip/SKILL|법무/IP Agent]]가 즉시 사람에게 에스컬레이션.

- 기존 유명 캐릭터와 유사성
- 폰트·소품의 라이선스 미확인
- 클라이언트가 "다른 데도 쓰고 싶다"고 사후 요청
- 외주 작가가 "내 포트폴리오에 올려도 되냐" 문의

## 관련 문서

- [[wiki/concepts/라이선스 표준 조항]]
- [[raw/ip-licenses/README]]
- [[raw/characters/README]]
- [[skills/legal-ip/SKILL]]
- [[skills/character/SKILL]]
