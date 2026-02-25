# References

## Requirements Source

- `docs/REQUIREMENTS.md`: Canonical requirements with shared operational-instruction constraints (`REQ-019`).

## Prompt Artifacts Updated for Worktree/Merge Cleanup Handling

- `src/prompts/change.md`: Step 3 (worktree creation) and Step 10 (merge management).
- `src/prompts/cover.md`: Step 3 (worktree creation) and Step 9 (merge management).
- `src/prompts/fix.md`: Step 3 (worktree creation) and Step 9 (merge management).
- `src/prompts/implement.md`: Step 2 (worktree creation) and Step 9 (merge management).
- `src/prompts/new.md`: Step 3 (worktree creation) and Step 10 (merge management).
- `src/prompts/recreate.md`: Step 3 (worktree creation) and Step 7 (merge management).
- `src/prompts/refactor.md`: Step 3 (worktree creation) and Step 9 (merge management).
- `src/prompts/references.md`: Step 2 (worktree creation) and Step 5 (merge management).
- `src/prompts/readme.md`: Step 2 (worktree creation) and Step 6 (merge management).
- `src/prompts/renumber.md`: Step 3 (worktree creation) and Step 7 (merge management).
- `src/prompts/workflow.md`: Step 2 (worktree creation) and Step 6 (merge management).

## Prompt Behavior Updates

- `src/prompts/readme.md`: Behavior and Step 4 now enforce section-scoped README edits, preserving non-analysis content and existing structure/format when possible.
- `src/prompts/fix.md`: Behavior and Steps 4-5 now prefer a reproducer-test-first bug-fix flow with constrained fallback to no-test verification only when one-test guideline-compliant reproduction is too costly or infeasible.
- `src/prompts/{change,cover,fix,implement,new,recreate,refactor,references,readme,renumber,workflow}.md`: Merge-success cleanup now chains worktree removal with temporary branch deletion to prevent residual worktree branches.
- `src/prompts/{analyze,change,check,cover,fix,implement,new,readme,recreate,refactor,references,renumber,workflow}.md`: Execution-context instructions now require `<EXECUTION_ID>` generation via `date +"%Y%m%d%H%M%S"` instead of UUID/`uuidgen`.

## Requirement Updates

- `docs/REQUIREMENTS.md`: Updated `REQ-019` to require `<EXECUTION_ID>` generation via `date +"%Y%m%d%H%M%S"` and successful-merge cleanup that removes both the temporary worktree and its isolated branch.
- `docs/REQUIREMENTS.md`: Added `REQ-027` requiring all prompt YAML `usage` values to be generated with a maximum length of 1024 characters.
