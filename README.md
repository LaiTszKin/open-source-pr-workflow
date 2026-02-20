# open-source-pr-workflow

A Codex skill focused on preparing and opening review-ready pull requests for open-source projects.

## What this repository contains

- `SKILL.md`: The main workflow definition.
- `agents/openai.yaml`: Agent integration settings.

## Highlights

- Enforces branch naming convention: `codex/feature/{feature_name}`
- Focuses on PR preparation/creation instead of feature implementation
- Requires explicit user confirmation of the final PR draft before `gh pr create`
- Defaults forked repositories to open PRs against the upstream parent repository (unless user explicitly requests the fork)
- Requires clear PR sections for motivation, engineering rationale, and test results
- Encourages minimal, verifiable, review-ready contributions

## License

Released under the MIT License. See `LICENSE` for details.
