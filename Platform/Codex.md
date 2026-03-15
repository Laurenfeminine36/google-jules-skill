# Codex

## KR

### 현재 기준 플랫폼

이 저장소는 현재 Codex 기준으로 가장 잘 맞춰져 있습니다.

### 어떻게 연결되는가

- 저장소 운영 문서: `README.md`
- 스킬 본문: `google-jules-control/SKILL.md`
- 실행 스크립트: `google-jules-control/scripts/jules_api.py`

### Codex에서의 권장 사용 방식

- 프로젝트 루트에서 실행
- `.env` 자동 로드 사용
- 긴 작업은 `summary`, `wait`, `cleanup-report` 중심으로 운영
- 사용자에게 보이는 메시지는 `notify-close-plan --markdown`으로 생성

### Codex용 운영 패턴

```bash
python3 google-jules-control/scripts/jules_api.py doctor --compact
python3 google-jules-control/scripts/jules_api.py repo-to-source --repo owner/repo --compact
python3 google-jules-control/scripts/jules_api.py create-session ...
python3 google-jules-control/scripts/jules_api.py summary --session sessions/SESSION_ID
```

## EN

### Current Reference Platform

This repository is currently optimized for Codex.

### Main Integration Points

- Repository operations: `README.md`
- Skill instructions: `google-jules-control/SKILL.md`
- Execution script: `google-jules-control/scripts/jules_api.py`

### Recommended Usage in Codex

- Run from the repository root
- Rely on automatic `.env` loading
- Use `summary`, `wait`, and `cleanup-report` for long-running work
- Use `notify-close-plan --markdown` for user-facing close confirmation

### Codex Operating Pattern

```bash
python3 google-jules-control/scripts/jules_api.py doctor --compact
python3 google-jules-control/scripts/jules_api.py repo-to-source --repo owner/repo --compact
python3 google-jules-control/scripts/jules_api.py create-session ...
python3 google-jules-control/scripts/jules_api.py summary --session sessions/SESSION_ID
```
