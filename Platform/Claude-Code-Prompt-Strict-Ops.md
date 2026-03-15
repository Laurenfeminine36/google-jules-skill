# Claude Code Prompt Strict Ops

## KR

```text
Use google-jules-control/SKILL.md as the project operating contract for Jules work.

Rules:
- Use google-jules-control/scripts/jules_api.py for all Jules operations.
- Start with `python3 google-jules-control/scripts/jules_api.py doctor --compact`.
- Resolve owner/repo with `repo-to-source --repo owner/repo --compact` when only a repo name is provided.
- Prefer `.env` auth with JULES_API_KEY.
- Use `summary`, `cleanup-report --markdown`, `close-ready-report --markdown`, and `notify-close-plan --markdown` for user-facing communication.
- Check `gh-auth-check --compact` before merge-aware cleanup.
- Never delete or close a Jules session without explicit user confirmation.
- Summarize long JSON outputs into concise operational messages.

Sequence:
1. doctor
2. repo-to-source
3. list-sources or create-session
4. summary
5. cleanup only after confirmation
```

## EN

```text
Use google-jules-control/SKILL.md as the project operating contract for Jules work.

Rules:
- Use google-jules-control/scripts/jules_api.py for all Jules operations.
- Start with `python3 google-jules-control/scripts/jules_api.py doctor --compact`.
- Resolve owner/repo with `repo-to-source --repo owner/repo --compact` when only a repo name is provided.
- Prefer `.env` auth with JULES_API_KEY.
- Use `summary`, `cleanup-report --markdown`, `close-ready-report --markdown`, and `notify-close-plan --markdown` for user-facing communication.
- Check `gh-auth-check --compact` before merge-aware cleanup.
- Never delete or close a Jules session without explicit user confirmation.
- Summarize long JSON outputs into concise operational messages.

Sequence:
1. doctor
2. repo-to-source
3. list-sources or create-session
4. summary
5. cleanup only after confirmation
```
