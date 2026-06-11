---
name: feature-addition-with-api-and-ui-and-tests
description: Workflow command scaffold for feature-addition-with-api-and-ui-and-tests in hermes-agent.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-addition-with-api-and-ui-and-tests

Use this workflow when working on **feature-addition-with-api-and-ui-and-tests** in `hermes-agent`.

## Goal

Adds a new feature that involves backend API changes, frontend UI updates, and corresponding tests.

## Common Files

- `hermes_cli/web_server.py`
- `web/src/lib/api.ts`
- `web/src/pages/WebhooksPage.tsx`
- `tests/hermes_cli/test_dashboard_admin_endpoints.py`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Implement backend logic in Python (e.g., web_server.py).
- Update or add frontend UI components/pages (e.g., .tsx, .ts files in web/src/pages or web/src/lib).
- Add or update tests for the new API/UI (e.g., test_dashboard_admin_endpoints.py).
- Commit all related files together.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.