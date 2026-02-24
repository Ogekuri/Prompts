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
  - Filesystem read/write operations over `README.md`, `docs/*.md`, and `src/prompts/*.md`.

## Communication Edges

- None detected: no explicit multi-process or multi-thread communication mechanisms are defined under `src/` or `.github/workflows/`.
