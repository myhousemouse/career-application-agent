# 클라우드 환경 시작 지침

이 문서는 클라우드 환경 초안이 잠겨 자동 저장되지 못한 세 저장소 구성과 시작 지침을 보존합니다.

## 저장소 구성

| 저장소 | 마운트 경로 | 기준 커밋 |
|---|---|---|
| `myhousemouse/company_readme` | `company_readme` | `d5b7b8b4a1f374712b1264c26487f53941f2ec39` |
| `myhousemouse/experience` | `experience` | `d0b9081772fea9e56b72ca1dac178ebfe4a6524c` |
| `myhousemouse/career-application-agent` | `career-application-agent` | `95cb0dbae53df6d8d32b9d3fb2af7c1e63f9f811` |

환경 설정에 반영할 때는 각 저장소 `main`의 최신 커밋을 다시 확인해 사용합니다.

## 시작 지침

### 공통 시작

- `/workspace` 아래의 기존 체크아웃을 사용한다. 사용자가 명시적으로 요청하지 않는 한 Git worktree를 만들지 않는다.
- 먼저 `/workspace/career-application-agent/AGENTS.md`를 끝까지 읽고 요청을 라우팅한다.
- 작업 대상 저장소의 `git status`, `README.md`, `AGENTS.md`를 확인하고 기존 사용자 변경을 보존한다.
- 날짜와 최신성 판단은 한국 시간(Asia/Seoul)을 기준으로 한다.

### 저장소 역할

- `/workspace/company_readme`: 기업·산업·경쟁사·직무 분석과 공식 출처의 원본
- `/workspace/experience`: 개인 경험, 최신 정정, 자소서 에피소드와 성과 범위의 원본
- `/workspace/career-application-agent`: 공고 매핑, 자기소개서·지원서·포트폴리오 문구·면접 답변의 결합 산출물
- 원본을 다른 저장소에 복제하지 않는다. 결합 산출물에는 사용한 원본 문서 경로를 남긴다.

### 기업분석만 요청한 경우

- `/workspace/company_readme/.agents/skills/company-analysis/SKILL.md`를 끝까지 읽고 적용한다.
- 공식 홈페이지, 공시, IR, 채용 공고 등 공개 근거만 사용한다.
- `/workspace/experience`를 읽거나 개인 경험을 분석에 섞지 않는다.
- 결과는 `/workspace/company_readme/<기업명>/`에 저장한다.

### 경험 연결·직무 적합성 판단을 요청한 경우

- `/workspace/career-application-agent/.agents/skills/application-writing/SKILL.md`를 끝까지 읽고 적용한다.
- 기업·직무 분석과 공고를 먼저 확인한다.
- `/workspace/experience/AGENTS.md`와 지정된 최신 정정 자료를 읽는다.
- 경험 인덱스에서 후보를 고른 뒤 선택한 프로젝트의 원문까지 확인한다.
- 본인 역할과 팀 결과, 실제 성과와 목표·제안·예상 효과를 구분한다.

### 자소서·지원서·포트폴리오 문구·면접 답변을 요청한 경우

- application-writing 스킬에 따라 기업분석과 경험 원본을 모두 검증한다.
- 새 초안을 쓰기 전에 `experience/자소서 정리.md`, 선택한 경험의 에피소드 문서와 과거 자소서 원문에서 활용 회사·직무·문항·강조 관점을 확인한다.
- 과거 활용 이력과 최신 정정이 충돌하면 최신 정정을 우선하고 이전 문장을 검증 없이 재사용하지 않는다.
- 경험 에피소드는 STAR 방식으로 전개한다. S는 배경과 문제, T는 본인의 책임과 성공 기준, A는 판단 기준·대안·선택 이유·실행과 검증, R은 확인된 결과·한계·배운 점을 담는다.
- 분량이 제한되면 S와 T를 먼저 줄이고 A의 판단 과정과 R의 검증 범위를 보존한다.
- 행동을 나열하지 말고 문제, 판단 기준, 선택 이유, 실행, 검증, 직무 연결이 드러나게 쓴다.
- 확인되지 않은 숫자·성과·동기·감정·대화를 만들지 않는다.
- 결과는 `/workspace/career-application-agent/applications/<기업명>/<날짜_직무명>/`에 저장한다.

### 글 다듬기·AI 티 제거를 요청한 경우

- `/workspace/experience/.agents/skills/humanize-korean/SKILL.md`를 끝까지 읽고 필수 참조문서와 검증 절차를 따른다.
- 내용과 사실 검증을 먼저 마친 뒤 마지막 단계에 윤문한다.
- 사실, 수치, 날짜, 고유명사, 개인 역할과 성과 범위를 바꾸지 않는다.

### 저장과 Git

- 기업분석 변경은 `company_readme`, 경험 변경은 `experience`, 결합 지원서는 `career-application-agent`에서만 저장·커밋한다.
- 사용자가 커밋·푸시를 요청한 경우에만 수행한다.
- 커밋 전 `git diff --check`, 내부 링크와 작업 트리 상태를 확인한다.
- 별도 설치나 상시 실행 서비스는 필요하지 않다.
