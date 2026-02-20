---
name: open-source-pr-workflow
description: Workflow for contributing to open-source projects and opening pull requests. Use when the user asks to contribute code to OSS repos, prepare a PR branch, push contribution changes, or open/update a PR. Enforce branch naming as codex/feature/{feature_name}, require user confirmation of the final PR draft before creating the PR, and write PR content in English by default with required sections for related issues or motivation, engineering decisions with rationale, and test results with commands.
---

# Open Source PR Workflow

## Overview

Use this workflow to prepare open-source contributions and open review-ready pull requests with consistent branch naming and PR content quality.

## Workflow

### 1) Clarify PR scope

- Identify related issue links/IDs and summarize the motivation for the change.
- Confirm target base branch and contribution constraints from the repository.

### 2) Create a compliant branch name

- Always use this pattern for PR branches: `codex/feature/{feature_name}`.
- Convert `{feature_name}` to lowercase kebab-case (`[a-z0-9-]` only).
- If the current branch name does not match, create a new compliant branch from current HEAD before opening PR.

Example:

```bash
git checkout -b codex/feature/add-rate-limit-retry
```

### 3) Implement and verify changes

- Make the minimal required code/documentation changes.
- Run relevant checks (lint/test/build) based on repository conventions.
- Record exact test commands and outcomes for PR content.

### 4) Draft PR content and get user confirmation

- Draft the PR title and full PR body before creating the PR.
- Show the draft to the user and wait for explicit confirmation.
- If the user requests edits, revise the draft and ask for confirmation again.
- Only proceed to create the PR after the user confirms the final draft.

### 5) Open the PR

- Prefer `gh pr create` to open the PR.
- Ensure PR title/body are in English by default.
- Switch language only when the user explicitly requests another language.

## Required PR Body Structure

Use this structure (or equivalent headings) every time:

```markdown
## Related Issues / Motivation
- Related: #<issue-id> (or link)
- Why this change is needed

## Engineering Decisions and Rationale
- Key implementation choices
- Why each choice was made
- Trade-offs considered (if applicable)

## Test Results and Commands
- ✅ `command 1`
- ✅ `command 2`
- Summary of outcomes

### Test Cases (for complex changes)
- Case 1: input/scenario -> expected result
- Case 2: input/scenario -> expected result
```

If tests cannot run locally, state why and provide the closest available validation evidence.

## Pre-PR Checklist

- Branch name matches `codex/feature/{feature_name}`.
- User explicitly confirmed the final PR draft.
- PR body includes all three required sections.
- Test commands and results are explicitly listed.
- Language defaults to English unless user requests otherwise.
