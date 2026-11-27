# Claude 시작 지침

이 저장소에서 작업을 시작하면 먼저 [AGENTS.md](AGENTS.md)를 끝까지 읽고 그 라우팅을 따른다.

## 함께 쓰는 저장소

| 저장소 | 역할 | 경로 |
|---|---|---|
| `myhousemouse/company_readme` | 기업·직무 분석 원본 | `/workspace/company_readme` (없으면 이 저장소 옆 `../company_readme`) |
| `myhousemouse/experience` | 개인 경험·최신 정정 원본 | `/workspace/experience` (없으면 이 저장소 옆 `../experience`) |

두 저장소가 체크아웃돼 있지 않으면 지원서·윤문 작업 전에 먼저 연결한다. 원본 내용을 이 저장소에 복사하지 않는다.

## 스킬 위치

| 스킬 | 언제 | 경로 |
|---|---|---|
| application-writing | 자소서·지원서·면접 답변 작성, 경험 연결 | `.agents/skills/application-writing/SKILL.md` |
| company-analysis | 기업분석만 요청한 경우 | `company_readme/.agents/skills/company-analysis/SKILL.md` |
| humanize-korean | 윤문 요청 | `experience/.agents/skills/humanize-korean/SKILL.md` (`company_readme`에 같은 사본) |

## 윤문 트리거

사용자가 `다듬어줘`, `글 다듬어줘`, `자연스럽게 써줘`, `AI 티 안 나게`, `사람이 쓴 것처럼`처럼 말하면 humanize-korean 스킬의 `SKILL.md`와 `references/quick-rules.md`를 읽고 적용한다.

- 사실 검증을 마친 뒤 마지막 단계에서 적용한다.
- 사실·수치·날짜·고유명사·개인 역할·성과 범위는 바꾸지 않는다.
- `experience/AGENTS.md`의 말투 선호(자연스러운 본인 말투, 과장된 비유·상투적 교훈 지양)와 사용자가 지정한 문체를 우선한다.
