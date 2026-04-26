# CLAUDE.md — 2INPER Vault Operating Manual

이 파일은 Claude Code가 매 세션 시작 시 자동으로 읽습니다. 이 vault에서 작업할 때 반드시 따라야 할 규칙입니다. 자세한 내용은 본문 전반의 wikilink를 참조하세요.

## 이 폴더가 무엇인가

이 폴더는 **2INPER(이인페르)** 의 운영 vault입니다. 캐릭터 전문 웹에이전시이며 2인 운영 + AI 에이전트로 모든 직무를 대체합니다. 단순한 markdown 노트 모음이 아니라 **그래프 기반 지식 시스템**입니다 — Obsidian + Graphify + LLM Wiki 패턴 + Paperclip 에이전트.

## 작업 시작 시 반드시 거치는 절차

새 task를 받으면 무조건 이 순서를 따르세요. 건너뛰면 vault의 그래프 무결성이 깨집니다.

1. `wiki/index.md`를 먼저 읽는다. 여기가 단일 진입점입니다.
2. task와 관련된 community/concept/entity 페이지로만 추가 진입합니다. 모든 파일을 훑지 마세요.
3. `frontmatter-standard.md`의 YAML 스키마를 따릅니다.
4. 필요하면 `templates/` 아래 표준 템플릿을 복사해 시작합니다.
5. 결과물은 적합한 폴더에 저장합니다. **어디에 저장하는지 모르면 만들지 말고 사람에게 물어보세요.**

## 폴더 작성 규칙 (가장 중요)

| 폴더 | 누가 쓰나 | 규칙 |
|------|-----------|------|
| `raw/` | 사람·Claude·에이전트 자유 입력 | **단방향 입력 전용**. LLM은 여기서 읽기만, 수정·정리·이동은 금지 |
| `wiki/concepts/` | Knowledge Manager만 본문 갱신 | 다른 에이전트는 frontmatter의 `last_reviewed`만 갱신 가능 |
| `wiki/communities/` | Graphify 자동 생성 | 사람·LLM 모두 직접 편집 금지 |
| `wiki/entities/` | Graphify 자동 생성 | 예외: `legal-ip` 에이전트만 라이선스/캐릭터 entity 직접 갱신 권한 |
| `wiki/queries/` | 답변한 에이전트가 저장 | `templates/query-template.md` 사용 |
| `code/` | Developer 에이전트 | Graphify의 AST 패스 대상 — 디자인 결정은 주석으로 남겨야 그래프에 반영됨 |
| `skills/` | 사람만 편집 | Paperclip에 등록된 에이전트 정의. 함부로 바꾸지 말 것 |
| `templates/` | 사람만 편집 | 새 표준 추가 시에만 사람이 편집 |
| `graph/` | Graphify 자동 생성 | 절대 손대지 말 것 |

이 규칙을 어기는 변경은 거부하거나 사람에게 확인 요청하세요.

## 새 파일을 만드는 결정 트리

- 클라이언트 정보 → `raw/clients/<클라이언트명>/index.md` ([[templates/client-template]])
- 프로젝트 → `raw/projects/<프로젝트명>/index.md` ([[templates/project-template]])
- 캐릭터 → `raw/characters/<캐릭터명>/index.md` ([[templates/character-template]]). **반드시 legal-ip 검토 후 클라이언트에 발송**
- 라이선스 → `raw/ip-licenses/.../<이름>.md` + 같은 폴더에 PDF ([[templates/license-template]])
- 회의 → `raw/meetings/YYYY/MM/YYYY-MM-DD-<이름>.md` ([[templates/meeting-template]])
- 제안서 → `raw/projects/<프로젝트명>/proposal.md` ([[templates/proposal-template]])
- 질의 응답 → `wiki/queries/YYYY-MM-DD-<질문>.md` ([[templates/query-template]])
- 개발 코드 → `code/projects/<프로젝트명>/`
- 그 외 자유 메모 → 가장 가까운 raw 하위 폴더

## YAML 프론트매터는 필수

모든 markdown 파일은 `frontmatter-standard.md`의 스키마를 가져야 합니다. 빠진 채로 만들지 마세요. 최소 필드: `type`, `status`, `owner`, `tags`, `created`, `last_reviewed`, `related`.

## Wikilink 규칙

- 다른 노드를 언급할 때는 항상 `[[페이지명]]` 형식 사용. 단순 텍스트로 적지 마세요 — 그래프에서 누락됩니다.
- 외부 링크는 `[텍스트](URL)` 형식 그대로.
- 링크 대상이 아직 존재하지 않아도 `[[...]]`로 적어두면 Graphify가 frontier로 표시해줍니다.

## 토큰 비용 규율

`wiki/concepts/토큰 예산 정책.md` 참조. 짧게 요약하면:

- 정형 산출물(견적서, 보고서, 체크리스트)은 템플릿 + 변수 치환으로 처리. LLM 호출 최소화.
- 같은 질문은 `wiki/queries/`에 저장된 답을 먼저 확인.
- 로컬 임베딩 검색이 가능한 작업은 LLM에 전달하지 말 것.
- 의심되면 한 모델 위로 올리지 말고 사람에게 에스컬레이션.

## Graphify 운영

- `graphify build --wiki` — 전체 재빌드 (LLM 비용 발생)
- `graphify build --code-only` — 코드만 (LLM 0)
- `graphify update` — 증분
- `graphify --watch` — 백그라운드
- 매주 수요일 22시 KST에 자동 빌드. `graph/audit.md` 검토 결과는 Knowledge Manager가 처리.

## 보안 / 민감정보

- `raw/finance/`, `raw/ip-licenses/`는 **민감 정보**. 외부 공유·포트폴리오·SNS 게시 절대 금지.
- 주민번호·계좌·카드 전체번호는 vault에 절대 저장 금지(마지막 4자리만).
- git 저장소가 private인지 항상 확인.

## 사람에게 반드시 물어봐야 하는 것

다음은 자동으로 진행하지 마세요. 무조건 사람 승인을 받으세요.

- 견적·계약서·청구서 발송
- 새 캐릭터의 IP 분류 결정
- 클라이언트에 시안·이메일·DM 발송
- 광고비 결제·예산 변경
- 토큰 예산 80% 도달 후 추가 LLM 호출
- 해당 클라이언트의 컴플레인 응대
- `wiki/concepts/`의 본문 변경 (Knowledge Manager 외)
- 변호사 검토 없는 신규 계약 조항

## Git 운영

- 의미 단위로 작은 커밋. 한 커밋에 여러 영역(raw + wiki + skills) 섞지 말 것.
- 커밋 메시지: `<영역>: <한 줄 요약>` 예: `raw/clients: 감자카페 1차 미팅 노트 추가`
- vault 변경 후 가능하면 즉시 git commit. Graphify의 git hook이 그래프 갱신을 트리거합니다.

## 모르겠을 때

- 폴더 결정이 애매하면 → 사람에게 묻기
- 누가 쓰는 영역인지 애매하면 → `skills/<에이전트>/SKILL.md` 확인
- entity가 이미 있는지 애매하면 → `wiki/entities/`와 `raw/`에서 검색

이 vault는 **그래프 무결성 > 속도**입니다. 빠르게 한 번 어기는 것보다 천천히 한 번 더 묻는 게 낫습니다.
