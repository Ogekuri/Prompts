## Execution Units Index

- `PROC:main` | type: process | role: prompt-workflow execution | entrypoint: external CLI invocation (`req ...`) | defining paths: `src/prompts/*.md`

## Execution Units

### `PROC:main`

- Entrypoint(s): external CLI invocation (`req ...`) that executes repository prompt workflows.
- Lifecycle/trigger: starts on explicit operator command, executes selected prompt workflow steps, then exits.
- Internal Call-Trace Tree:
  - No internal callable symbols are defined under `src/` or `.github/workflows/`; repository artifacts under `src/prompts/` are declarative Markdown workflow definitions.
- External Boundaries:
  - Git CLI commands (`git worktree add`, `git checkout`, `git merge`, `git worktree remove`).
  - Filesystem read/write operations over `README.md` (targeted section updates preserving unrelated structure/format when possible), `docs/*.md`, and `src/prompts/*.md`.
  - Prompt YAML metadata handling by external tooling, including bounded `usage` header values.
  - Test-runner boundaries used by defect-fix workflows, including preferred reproducer-test-first validation with conditional no-test fallback.

## Communication Edges

- None detected: no explicit multi-process or multi-thread communication mechanisms are defined under `src/` or `.github/workflows/`.
