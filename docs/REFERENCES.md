# References

## Requirements Source

- `docs/REQUIREMENTS.md`: Canonical requirements with shared operational-instruction constraints (`REQ-019`).

## Prompt Artifacts Updated for Worktree/Merge Config Handling

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

## Requirement Updates

- `docs/REQUIREMENTS.md`: Added `REQ-027` requiring all prompt YAML `usage` values to be generated with a maximum length of 1024 characters.
