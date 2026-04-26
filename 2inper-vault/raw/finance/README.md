---
type: folder-readme
status: mature
owner: human
tags: [meta, raw, finance, sensitive]
created: 2026-04-25
last_reviewed: 2026-04-25
---

# raw/finance/

매출·매입·세금계산서·정산 1차 자료. **민감 정보**이므로 git 저장소가 비공개인지 반드시 확인하세요.

## 권장 구조

```
finance/
├── invoices/
│   └── 2026/
│       └── 2026-05-감자카페-1차.md
├── expenses/
│   └── 2026/
├── tax/
│   ├── vat/                      ← 부가세
│   └── income/                   ← 종합소득세
└── reports/
    └── 2026-05-월간정산.md
```

## 보안

- 계좌번호·카드번호 전체는 **여기에도 저장하지 않음**. 마지막 4자리만.
- 주민번호·사업자등록번호는 별도 암호화 저장소.
- Git 저장소는 반드시 private.

## 자동화

[[skills/accountant/SKILL|경리/회계 Agent]]가 매월 1일 [[wiki/queries/README|wiki/queries/]]에 월간 리포트를 자동 생성합니다.

## 관련 문서

- [[raw/README]]
- [[skills/accountant/SKILL]]
- [[skills/data-analyst/SKILL]]
