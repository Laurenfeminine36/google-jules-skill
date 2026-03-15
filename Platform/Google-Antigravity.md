# Google Antigravity

## KR

### 전환 개념

Google Antigravity에서는 이 저장소를 “에이전트가 읽는 운영 문서 세트 + 로컬 실행 가능한 Jules 제어 스크립트”로 가져가는 방식이 적합합니다.

### 권장 사용 방식

- `Platform/Migration-Guide.md`를 먼저 읽고
- `google-jules-control/SKILL.md`를 운영 규칙 문서로 사용
- 실제 Jules 제어는 `google-jules-control/scripts/jules_api.py` 호출로 유지

### Antigravity용 적응 포인트

- 에이전트가 셸 명령을 안정적으로 실행할 수 있는지 먼저 확인
- `.env` 자동 로드와 현재 작업 디렉토리 기준 동작을 유지
- 작업 결과를 카드형 UI로 보여주는 경우 `--markdown` 출력을 우선 사용

### 시작 프롬프트 예시

```text
Read google-jules-control/SKILL.md first. Use the bundled Jules control script for session management, reporting, and cleanup. Prefer markdown reports for human review and require explicit confirmation before any session deletion.
```

## EN

### Adaptation Model

For Google Antigravity, this repository works best as an agent-readable operating guide plus a local Jules control script.

### Recommended Usage Pattern

- Read `Platform/Migration-Guide.md` first
- Use `google-jules-control/SKILL.md` as the platform operating guide
- Keep actual Jules control in `google-jules-control/scripts/jules_api.py`

### Antigravity Adaptation Notes

- Verify that the agent can execute local shell commands reliably
- Preserve `.env` auto-loading and working-directory-based behavior
- Prefer `--markdown` report output when the UI presents rich review cards or panels

### Starter Prompt Example

```text
Read google-jules-control/SKILL.md first. Use the bundled Jules control script for session management, reporting, and cleanup. Prefer markdown reports for human review and require explicit confirmation before any session deletion.
```
