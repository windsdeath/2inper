---
type: folder-readme
status: mature
owner: human
tags: [meta, raw, ip, legal]
created: 2026-04-25
last_reviewed: 2026-04-25
---

# raw/ip-licenses/

캐릭터·디자인·코드의 **저작권·상표·라이선스 계약** 1차 문서. 캐릭터 비즈니스에서 가장 위험·가장 가치 있는 영역입니다.

## 들어가야 하는 것

- 작가/일러스트레이터와의 계약서 PDF
- 클라이언트 양도/사용허락 계약서
- 폰트 라이선스 영수증
- 상표 출원·등록 서류
- 음원·이미지 스톡 라이선스

## 권장 구조

```
ip-licenses/
├── characters/
│   └── <캐릭터명>-license-2026.pdf
├── fonts/
├── stock/
├── trademarks/
└── client-agreements/
```

## 새 라이선스 추가 시

[[templates/license-template]]을 복사해 같은 이름의 `.md` 파일을 만들어 PDF 옆에 두세요. PDF는 Graphify가 멀티모달로 추출하지만, **md 메타데이터가 그래프 노드의 1차 정보**가 됩니다.

[[skills/legal-ip/SKILL|법무/IP Agent]]가 만료일·갱신·범위 위반을 모니터링합니다.

## 관련 문서

- [[raw/README]]
- [[templates/license-template]]
- [[wiki/concepts/캐릭터 IP 가이드]]
- [[skills/legal-ip/SKILL]]
