---
type: folder-readme
status: mature
owner: human
tags: [meta, raw, meetings]
created: 2026-04-25
last_reviewed: 2026-04-25
---

# raw/meetings/

회의 녹음·전사·노트. Graphify가 `faster-whisper`로 **로컬 전사**하므로 음성 파일을 그대로 넣어도 됩니다(전사에 LLM 토큰 0).

## 권장 구조

```
meetings/
├── 2026/
│   └── 05/
│       ├── 2026-05-12-감자카페-킥오프.md      ← 노트
│       ├── 2026-05-12-감자카페-킥오프.m4a     ← 녹음
│       └── 2026-05-12-감자카페-킥오프.srt     ← Graphify 자동 전사
```

## 새 회의 추가 시

1. [[templates/meeting-template]] 복사해 `.md` 생성
2. 녹음 파일을 같은 이름으로 옆에 둠
3. 다음 `graphify build` 또는 `--watch` 사이클에서 자동 전사 + 그래프 통합

## 사적 발언 처리

오프-더-레코드 발언은 노트에 기록하지 마세요. 위키 그래프에 그대로 노출됩니다.

## 관련 문서

- [[raw/README]]
- [[templates/meeting-template]]
- [[skills/knowledge-manager/SKILL]]
