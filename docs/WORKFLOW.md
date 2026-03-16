## Execution Units Index

- `PROC:main` | type: process | parent: none | role: prompt-workflow execution orchestrator for repository prompt artifacts with bell-free terminal output contracts | entrypoint: prompt frontmatter documents under `src/prompts/*.md` consumed by external runtime | defining files: `src/prompts/analyze.md`, `src/prompts/change.md`, `src/prompts/check.md`, `src/prompts/cover.md`, `src/prompts/create.md`, `src/prompts/fix.md`, `src/prompts/implement.md`, `src/prompts/new.md`, `src/prompts/readme.md`, `src/prompts/recreate.md`, `src/prompts/refactor.md`, `src/prompts/references.md`, `src/prompts/renumber.md`, `src/prompts/workflow.md`, `src/prompts/write.md`
- `PROC:gha-check-branch` | type: process | parent: none | role: validates tagged commit ancestry and emits release-gate output | entrypoint: workflow `Release (markdown)` job `check-branch` | defining files: `.github/workflows/release-markdown.yml`
- `PROC:gha-build-release` | type: process | parent: none | role: builds changelog and publishes GitHub release assets | entrypoint: workflow `Release (markdown)` job `build-release` | defining files: `.github/workflows/release-markdown.yml`

## Execution Units

### `PROC:main`

- Entrypoint(s):
  - Prompt frontmatter declarations consumed by external runtime [`src/prompts/analyze.md`, `src/prompts/change.md`, `src/prompts/check.md`, `src/prompts/cover.md`, `src/prompts/create.md`, `src/prompts/fix.md`, `src/prompts/implement.md`, `src/prompts/new.md`, `src/prompts/readme.md`, `src/prompts/recreate.md`, `src/prompts/refactor.md`, `src/prompts/references.md`, `src/prompts/renumber.md`, `src/prompts/workflow.md`, `src/prompts/write.md`].
- Lifecycle/trigger:
  - Starts when an operator invokes the external prompt runtime with a selected prompt file.
  - Executes the selected prompt steps with exact terminal strings that do not append bell-control suffixes; final repository-cleanliness verification uses `req --git-check` (not `git status --porcelain`); authorized early-termination branches after successful worktree creation use only explicit `req --git-wt-delete <WORKTREE_NAME>` cleanup before termination and do not include rollback or revert git-state commands (`git restore .`, `git checkout .`, `git clean -fd`), while pre-create branches, create-failure branches, and prompts without worktree creation do not use `req --git-wt-delete <WORKTREE_NAME>`; exits after workflow completion.
- Internal Call-Trace Tree:
  - No internal functions detected under `src/` or `.github/workflows`.
- External Boundaries:
  - External prompt runtime parses Markdown prompt artifacts and executes tool/shell instructions declared in prompt steps.
- Thread Model:
  - no explicit threads detected.

### `PROC:gha-check-branch`

- Entrypoint(s):
  - Workflow trigger `on.push.tags: v[0-9]+.[0-9]+.[0-9]+` activates workflow run [`.github/workflows/release-markdown.yml`].
  - Job definition `check-branch` on `ubuntu-latest` [`.github/workflows/release-markdown.yml`].
- Lifecycle/trigger:
  - Starts as first job in workflow graph.
  - Performs checkout and branch-containment check for `${GITHUB_SHA}`.
  - Writes `is_master` output to `$GITHUB_OUTPUT`; exits.
- Internal Call-Trace Tree:
  - No internal functions detected under `src/` or `.github/workflows`.
- External Boundaries:
  - `actions/checkout@v4` action execution [`.github/workflows/release-markdown.yml`].
  - Shell + git boundary (`git fetch`, `git branch -r --contains`, `grep`) [`.github/workflows/release-markdown.yml`].
  - GitHub Actions output-file boundary (`$GITHUB_OUTPUT`) [`.github/workflows/release-markdown.yml`].
- Thread Model:
  - no explicit threads detected.

### `PROC:gha-build-release`

- Entrypoint(s):
  - Job definition `build-release` with dependency `needs: check-branch` and gate `if: needs.check-branch.outputs.is_master == 'true'` [`.github/workflows/release-markdown.yml`].
- Lifecycle/trigger:
  - Starts only after `PROC:gha-check-branch` completion and positive gate output.
  - Performs checkout, changelog generation, and release publication.
  - Exits after release action completes.
- Internal Call-Trace Tree:
  - No internal functions detected under `src/` or `.github/workflows`.
- External Boundaries:
  - `actions/checkout@v4` action execution [`.github/workflows/release-markdown.yml`].
  - `mikepenz/release-changelog-builder-action@v6` boundary [`.github/workflows/release-markdown.yml`].
  - `softprops/action-gh-release@v2` boundary [`.github/workflows/release-markdown.yml`].
- Thread Model:
  - no explicit threads detected.

## Communication Edges

- `EDGE:gha-check-branch->gha-build-release`
  - direction: `PROC:gha-check-branch -> PROC:gha-build-release`
  - mechanism: GitHub Actions job dependency (`needs`) + job output propagation
  - endpoint/channel: `needs.check-branch.outputs.is_master`
  - payload/data-shape: string enum (`"true" | "false"`) written via `$GITHUB_OUTPUT`
  - evidence: `.github/workflows/release-markdown.yml`
