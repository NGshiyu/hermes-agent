```markdown
# hermes-agent Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns, coding conventions, and workflows used in the `hermes-agent` repository. The codebase is primarily Python, with some TypeScript/React for the frontend, and includes scripts for Windows installation. The repository emphasizes clear commit practices, robust testing, and coordinated feature and bugfix workflows across backend and frontend.

## Coding Conventions

- **File Naming:**  
  Use `snake_case` for Python files and directories.  
  Example:  
  ```
  hermes_cli/backup.py
  tests/hermes_cli/test_backup.py
  ```

- **Import Style:**  
  Use aliases for imports to clarify usage.  
  Example:  
  ```python
  import hermes_state as hs
  ```

- **Export Style:**  
  Use named exports in both Python and TypeScript.  
  Example (Python):  
  ```python
  def archive_session(...):
      ...
  ```
  Example (TypeScript):  
  ```typescript
  export function fetchApiData() { ... }
  ```

- **Commit Message Patterns:**  
  - Prefixes: `fix`, `chore`, `feat`, `test`
  - Example:  
    ```
    fix: handle edge case in backup restore logic
    feat: add admin dashboard endpoints and tests
    ```

## Workflows

### Bugfix with Regression Test
**Trigger:** When a bug is found and must be fixed with a test to prevent regression  
**Command:** `/fix-with-test`

1. Identify and fix the bug in the relevant Python or TypeScript file(s).
2. Add or update a test file to cover the fixed behavior.
3. Commit both the code and the test together.

**Example:**
```python
# hermes_cli/backup.py
def restore_backup(...):
    # fixed logic here

# tests/hermes_cli/test_backup.py
def test_restore_backup_handles_edge_case():
    ...
```

---

### Feature Addition with API, UI, and Tests
**Trigger:** When adding a new user-facing feature that requires backend and frontend changes  
**Command:** `/add-feature-api-ui-test`

1. Implement backend logic in Python (e.g., `web_server.py`).
2. Update or add frontend UI components/pages (e.g., `.tsx`, `.ts` files).
3. Add or update tests for the new API/UI.
4. Commit all related files together.

**Example:**
```python
# hermes_cli/web_server.py
def new_feature_endpoint(...):
    ...

// web/src/pages/WebhooksPage.tsx
export function WebhooksPage() {
    // new UI logic
}

// tests/hermes_cli/test_dashboard_admin_endpoints.py
def test_new_feature_endpoint():
    ...
```

---

### Windows Installer Fix and Enhancement
**Trigger:** When improving or fixing the Windows installation process  
**Command:** `/fix-windows-installer`

1. Edit `scripts/install.ps1` to fix bugs or add enhancements.
2. Test changes locally or in CI for Windows environments.
3. Commit the updated PowerShell script.

**Example:**
```powershell
# scripts/install.ps1
# Add logic to handle PATH updates or package manager detection
```

---

### Merge Bugfix or Feature PR
**Trigger:** When a PR with a bugfix or feature is ready to be merged  
**Command:** `/merge-pr`

1. Review and approve the PR.
2. Merge the PR, ensuring both code and test changes are included.
3. Resolve any merge conflicts as needed.

**Example:**  
Merging PR that updates `hermes_state.py` and `tests/hermes_state/test_session_archiving.py`.

---

## Testing Patterns

- **Framework:**  
  - Python: Standard `pytest`-style tests in `tests/` directories.
  - TypeScript: Uses `vitest` for frontend and API tests.

- **File Naming:**  
  - Python: `test_*.py` (e.g., `test_backup.py`)
  - TypeScript: `*.test.ts` (e.g., `api.test.ts`)

- **Example:**  
  ```python
  # tests/hermes_cli/test_backup.py
  def test_restore_backup_handles_edge_case():
      ...
  ```

  ```typescript
  // web/src/lib/api.test.ts
  import { fetchApiData } from './api'
  test('fetchApiData returns expected result', () => {
    ...
  })
  ```

## Commands

| Command                  | Purpose                                                         |
|--------------------------|-----------------------------------------------------------------|
| /fix-with-test           | Fix a bug and add/update a regression/unit test                 |
| /add-feature-api-ui-test | Add a new feature with backend, frontend, and tests             |
| /fix-windows-installer   | Fix or enhance the Windows installer script                     |
| /merge-pr                | Merge a pull request with code and test changes                 |
```
