---
name: bugfix-with-regression-test
description: Workflow command scaffold for bugfix-with-regression-test in hermes-agent.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /bugfix-with-regression-test

Use this workflow when working on **bugfix-with-regression-test** in `hermes-agent`.

## Goal

Implements a bugfix in Python or TypeScript code, and adds or updates a regression/unit test to cover the fixed behavior.

## Common Files

- `hermes_cli/backup.py`
- `tests/hermes_cli/test_backup.py`
- `cli.py`
- `tests/test_empty_session_hygiene.py`
- `gateway/run.py`
- `tests/gateway/test_restart_drain.py`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Identify and fix the bug in the main code file(s).
- Add or update a test file to cover the fixed behavior.
- Commit both the code and the test together.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.