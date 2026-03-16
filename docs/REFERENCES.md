# References

## Requirements Source

- `docs/REQUIREMENTS.md`: Canonical requirements set for prompt behavior and shared operational instructions.

## Updated Prompt Artifacts

- `src/prompts/{change,cover,fix,implement,new,readme,recreate,refactor,references,renumber,workflow}.md`: Final repository-cleanliness verification step now uses `req --git-check` instead of `git status --porcelain`.
- `src/prompts/change.md`: Removed rollback/revert git-state cleanup instructions from failure branches; cleanup now uses only `req --git-wt-delete <WORKTREE_NAME>`.
- `src/prompts/cover.md`: Removed rollback/revert git-state cleanup instructions from failure branches; cleanup now uses only `req --git-wt-delete <WORKTREE_NAME>`.
- `src/prompts/fix.md`: Removed rollback/revert git-state cleanup instructions from failure branches; cleanup now uses only `req --git-wt-delete <WORKTREE_NAME>`.
- `src/prompts/implement.md`: Removed rollback/revert git-state cleanup instructions from failure branches; cleanup now uses only `req --git-wt-delete <WORKTREE_NAME>`.
- `src/prompts/new.md`: Removed rollback/revert git-state cleanup instructions from failure branches; cleanup now uses only `req --git-wt-delete <WORKTREE_NAME>`.
- `src/prompts/refactor.md`: Removed rollback/revert git-state cleanup instructions from failure branches; cleanup now uses only `req --git-wt-delete <WORKTREE_NAME>`.

## Requirement Updates

- `docs/REQUIREMENTS.md`: Updated `REQ-019` to require final repository-cleanliness verification via `req --git-check` and to forbid `git status --porcelain` for that final check.
- `docs/REQUIREMENTS.md`: Updated `REQ-019` to enforce exclusive early-termination cleanup via `req --git-wt-delete <WORKTREE_NAME>` after successful worktree creation and to forbid rollback/revert commands (`git restore .`, `git checkout .`, `git clean -fd`) in those branches.
- `docs/REQUIREMENTS.md`: Updated `REQ-025` interruption rules to forbid rollback/revert git-state commands in authorized post-create interruption branches and require cleanup through `req --git-wt-delete <WORKTREE_NAME>` only.

## Workflow Model Update

- `docs/WORKFLOW.md`: Updated `PROC:main` lifecycle behavior to require final repository-cleanliness verification via `req --git-check` and encode exclusive worktree-delete cleanup with explicit prohibition of rollback/revert git-state commands in post-create early termination branches.
