# Claude Code

## KR

### 전환 개념

Claude Code에서는 이 저장소의 핵심 자산을 “프로젝트 문서 + 실행 스크립트” 조합으로 가져가는 것이 가장 안전합니다.

### 권장 이식 방식

- 프로젝트 루트에 이 저장소 문서를 둠
- Claude Code에게 `google-jules-control/SKILL.md`를 프로젝트 운영 문서처럼 참조시키기
- 실제 Jules 제어는 여전히 `google-jules-control/scripts/jules_api.py`로 수행

### Claude Code용 적응 포인트

- 스킬이라는 개념이 직접적으로 같지 않을 수 있으므로, `SKILL.md`를 작업 규약 문서처럼 사용
- `doctor`, `repo-to-source`, `cleanup-report`를 먼저 익히게 하는 프롬프트가 좋음
- 긴 JSON 출력은 요약해서 사용자에게 전달하도록 지시

### 시작 프롬프트 예시

```text
Use the local project guide at google-jules-control/SKILL.md. Prefer the bundled Jules control script for all Jules operations. Start with doctor, resolve the repo to a Jules source, then continue with session creation or reporting.
```

## EN

### Adaptation Model

In Claude Code, the safest migration model is to treat this repository as a combination of project docs plus an execution script.

### Recommended Porting Pattern

- Keep these documents in the project root
- Point Claude Code to `google-jules-control/SKILL.md` as the operating guide
- Keep actual Jules control in `google-jules-control/scripts/jules_api.py`

### Claude Code Adaptation Notes

- The skill concept may not map one-to-one, so use `SKILL.md` as a project operating contract
- Prefer prompts that teach Claude Code to start with `doctor`, `repo-to-source`, and `cleanup-report`
- Instruct it to summarize long JSON outputs before responding to users

### Starter Prompt Example

```text
Use the local project guide at google-jules-control/SKILL.md. Prefer the bundled Jules control script for all Jules operations. Start with doctor, resolve the repo to a Jules source, then continue with session creation or reporting.
```
