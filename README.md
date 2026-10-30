# vibe-coding-skills — 바이브 코딩에서 자주 하는 요청 모음

AI(Claude Code)와 바이브 코딩을 하며 **자주 되풀이한 요청**을 [Agent Skills](https://agentskills.io/specification) 형식의 스킬로 묶었습니다. 비개발자가 한 줄로 시켜도 같은 순서 · 같은 확인을 거치게 하는 것이 목적입니다.

## 들어 있는 스킬

한 작업의 흐름: PRD가 있으면 **prd-task**(작업 목록) → **start**(새 브랜치) → 고치기(필요하면 **refactor**) → **ship**(커밋 · 푸시 · PR) → 사람이 병합 → 다시 **start**.

| 스킬 | 부르는 법 | 하는 일 |
|---|---|---|
| [prd-task](prd-task/SKILL.md) | `/prd-task <PRD 경로>`, "task.md 만들어줘", "작업 목록으로 쪼개줘" | 완성된 PRD를 작업 목록(TASK.md)으로. 요구마다 시험 → 구현 순서로 쪼개고, PR마다 고쳐도 되는 파일 · 안 되는 파일을 계약으로 적고, 정할 것은 기본값과 함께 작업에 잇는다. 숫자는 다시 세고, 빼자는 것은 누가 넣었는지 확인한다 |
| [start](start/SKILL.md) | `/start`, "새 브랜치 따줘", "새 기능 시작할게" | 새 작업을 시작할 때. 앞 PR이 병합됐는지 · 남은 수정이 없는지 보고, 원격의 최신 main을 받아 그사이 들어온 변경을 알린 뒤 새 브랜치를 판다 |
| [ship](ship/SKILL.md) | `/ship`, "커밋해", "커밋하고 PR 올려", "깃 최신화해" | 브랜치 · PR 상태를 보고, 시험을 돌리고, 고친 파일만 골라 커밋 · 푸시 · PR. 부딪치면 양쪽을 살려 풀고 다시 시험. 시킨 만큼만 |
| [refactor](refactor/SKILL.md) | `/refactor`, "리팩토링해줘", "코드 정리해줘" | 겉 동작은 그대로 두고 속만 정리. 고치기 전 출력을 떠 두고 고친 뒤 한 글자까지 비교해 "그대로"임을 보인다 |

## 설치

쓰고 싶은 스킬 폴더를 스킬 자리에 복사합니다.

| 쓰는 곳 | 복사할 자리 |
|---|---|
| 내 컴퓨터의 모든 프로젝트 | `~/.claude/skills/<스킬>/` |
| 한 프로젝트만 | `<프로젝트>/.claude/skills/<스킬>/` |

```bash
git clone https://github.com/Frost0313z/vibe-coding-skills.git
cp -r vibe-coding-skills/prd-task vibe-coding-skills/start vibe-coding-skills/ship vibe-coding-skills/refactor ~/.claude/skills/
```

## 공통 원칙

- **시킨 만큼만** 한다. 안 시킨 일은 하지 않고 알려 준다.
- **재 본 것만** "확인함"이라고 쓴다. 언제 쟀는지 같이 적고, 못 본 것은 "확인 못 함"으로 남긴다.
- 프로젝트의 규칙 문서(CLAUDE.md 등)가 있으면 **그것이 먼저**다.

## 만든 배경

2026-10-25, 팀 프로젝트에서 한 사람이 하루 동안 Claude Code에 되풀이해 시킨 일(새 브랜치 · 리팩토링 · 커밋 · 푸시 · PR · 깃 최신화)과 그때 생긴 실수(병합된 PR에 커밋을 더 올리려다 막힘, 되돌리다 수정이 날아갈 뻔함)를 절차로 옮겼습니다. 초안은 Claude(Claude Code)가 썼습니다.

같은 사람이 만든 다른 스킬: [socratic](https://github.com/Frost0313z/socratic-inquiry-skill) — 소크라테스 문답.

## 라이선스

[MIT](LICENSE)
