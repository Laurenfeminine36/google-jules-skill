# Release Checklist / 배포 체크리스트

공유하거나 배포하기 전에 아래 항목을 확인합니다.  
Use this checklist before sharing or publishing the skill.

## 사전 점검 / Pre-Release

- `google-jules-control/SKILL.md`가 현재 명령 셋을 반영하는지 확인 / Confirm `google-jules-control/SKILL.md` reflects the current command set
- `google-jules-control/agents/openai.yaml`이 스킬 이름과 목적에 맞는지 확인 / Confirm `google-jules-control/agents/openai.yaml` still matches the skill name and purpose
- `google-jules-control/.env.example`에 실제 키가 없는지 확인 / Confirm `google-jules-control/.env.example` contains placeholders only
- `google-jules-control/.gitignore`에 `.env`가 포함되는지 확인 / Confirm `google-jules-control/.gitignore` excludes `.env`
- 저장소 루트 `.gitignore`에 `.env`가 포함되는지 확인 / Confirm the repository-root `.gitignore` excludes `.env`
- 저장소 루트와 스킬 폴더에 실제 시크릿이 추적되지 않는지 확인 / Ensure no real secrets are tracked in the repository root or skill folder

## 검증 / Validation

```bash
python3 -m py_compile google-jules-control/scripts/jules_api.py
python3 /path/to/quick_validate.py google-jules-control
```

## 라이브 점검 / Live Checks

```bash
python3 google-jules-control/scripts/jules_api.py doctor --compact
python3 google-jules-control/scripts/jules_api.py repo-to-source --repo owner/repo --compact
python3 google-jules-control/scripts/jules_api.py list-sources
```

권장 / Recommended:

- `--require-plan-approval`로 스모크 테스트 세션 1회 생성 / Create one smoke-test session with `--require-plan-approval`
- 해당 세션에서 `summary` 확인 / Verify `summary` works for that session
- 테스트 후 세션 삭제 / Delete the smoke-test session afterward

## 배포 판단 / Deployment Judgment

배포 가능 / Ready to ship:

- 검증 통과 / Validation passes
- `doctor` 상태 정상 / `doctor` shows the expected healthy state
- 실제 키로 Jules API 호출 성공 / Jules API calls succeed with a real key
- 최소 한 개 실제 저장소에서 source 해석 성공 / Source resolution works for at least one real repository
- 세션 생성과 정리를 최소 1회 end-to-end로 확인 / Session creation and cleanup have been tested end to end at least once

배포 보류 / Hold release if:

- 추적 파일에 시크릿 존재 / Secrets are present in tracked files
- merge 기반 명령을 안내하지만 `gh` 인증이 깨져 있음 / `gh` authentication is broken while merge-aware commands are advertised
- 실제 계정에서 repo lookup 또는 reporting 실패 / Repo lookup or reporting commands fail against a real account
