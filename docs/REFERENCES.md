# References

## Requirements Source

- `docs/REQUIREMENTS.md`: Canonical requirements set for prompt behavior and shared operational instructions.

## Updated Prompt Artifacts

- `src/prompts/{change,cover,fix,implement,new,readme,recreate,refactor,references,renumber,workflow}.md`: Worktree-generation bullet now explicitly requires deriving `<BASE_PATH>` with `req --base-path` and `<GIT_PATH>` with `req --git-path` before generating `<WORKTREE_NAME>` with `req --git-wt-name`.
- `.github/skills/{req-change,req-cover,req-fix,req-implement,req-new,req-readme,req-recreate,req-refactor,req-references,req-renumber,req-workflow}/SKILL.md`: Mirrored Step 3 worktree instruction now explicitly requires `cd ../<WORKTREE_NAME>` immediately after `req --git-wt-create <WORKTREE_NAME>` and before the next step.
- `src/prompts/{change,cover,fix,implement,new,readme,recreate,refactor,references,renumber,workflow}.md`: Final repository-cleanliness verification step now uses `req --git-check` instead of `git status --porcelain`.
- `src/prompts/change.md`: Removed rollback/revert git-state cleanup instructions from failure branches; cleanup now uses only `req --git-wt-delete <WORKTREE_NAME>`.
- `src/prompts/cover.md`: Removed rollback/revert git-state cleanup instructions from failure branches; cleanup now uses only `req --git-wt-delete <WORKTREE_NAME>`.
- `src/prompts/fix.md`: Removed rollback/revert git-state cleanup instructions from failure branches; cleanup now uses only `req --git-wt-delete <WORKTREE_NAME>`.
- `src/prompts/implement.md`: Removed rollback/revert git-state cleanup instructions from failure branches; cleanup now uses only `req --git-wt-delete <WORKTREE_NAME>`.
- `src/prompts/new.md`: Removed rollback/revert git-state cleanup instructions from failure branches; cleanup now uses only `req --git-wt-delete <WORKTREE_NAME>`.
- `src/prompts/refactor.md`: Removed rollback/revert git-state cleanup instructions from failure branches; cleanup now uses only `req --git-wt-delete <WORKTREE_NAME>`.
- `src/prompts/change.md`: Step 6 verification now audits ALL SRS requirements with progressive-disclosure evidence (`OK` pointer-only, `FAIL` full evidence) instead of only related requirements.
- `src/prompts/new.md`: Step 6 verification now audits ALL SRS requirements with progressive-disclosure evidence (`OK` pointer-only, `FAIL` full evidence) instead of only related requirements.
- `src/prompts/fix.md`: Step 5 verification now audits ALL SRS requirements with progressive-disclosure evidence (`OK` pointer-only, `FAIL` full evidence) instead of only related requirements.
- `src/prompts/{change,new,fix,cover,implement,refactor}.md`: Verification flow now executes existing unit-test suites during verification when relevant tests are present, using language-specific test-suite priority policy.
- `src/prompts/fix.md`: Defect-fix flow now explicitly prefers creating one failing reproducer unit test (when relevant suites exist) before designing and implementing source changes, then requires explicit reproducer-pass evidence in verification.
- `src/prompts/{change,new,fix,cover,implement,refactor,check}.md`: Verification flow now treats `Error: no source files found in configured directories.` from `req --here --static-check` as successful no-source completion.

## Requirement Updates

- `docs/REQUIREMENTS.md`: Updated `REQ-019` to require deriving `<BASE_PATH>` with `req --base-path` and `<GIT_PATH>` with `req --git-path` before generating `<WORKTREE_NAME>` with `req --git-wt-name`.
- `docs/REQUIREMENTS.md`: Updated `REQ-019` to require final repository-cleanliness verification via `req --git-check` and to forbid `git status --porcelain` for that final check.
- `docs/REQUIREMENTS.md`: Updated `REQ-019` to enforce exclusive early-termination cleanup via `req --git-wt-delete <WORKTREE_NAME>` after successful worktree creation and to forbid rollback/revert commands (`git restore .`, `git checkout .`, `git clean -fd`) in those branches.
- `docs/REQUIREMENTS.md`: Updated `REQ-025` interruption rules to forbid rollback/revert git-state commands in authorized post-create interruption branches and require cleanup through `req --git-wt-delete <WORKTREE_NAME>` only.
- `docs/REQUIREMENTS.md`: Updated `CHG-STP-006`, `NEW-STP-006`, and `FIX-STP-005` to normatively require full-SRS verification audits with progressive-disclosure evidence in final verification steps.
- `docs/REQUIREMENTS.md`: Updated change/cover/fix/implement/new/refactor scope and step requirements to require conditional execution of existing unit tests during verification using language-specific test-suite priority policy.
- `docs/REQUIREMENTS.md`: Updated `FIX-CTX-002`, `FIX-CTX-004`, `FIX-STP-004`, and `FIX-STP-005` to require a preferred reproducer unit-test-first bug-fix approach when relevant suites exist, with explicit pass verification evidence.
- `docs/REQUIREMENTS.md`: Added `REQ-028` to define `Error: no source files found in configured directories.` as a successful completion outcome for `req --here --static-check` in this repository.

## Workflow Model Update

- `docs/WORKFLOW.md`: Updated `PROC:main` lifecycle behavior to encode explicit `<BASE_PATH>`/`<GIT_PATH>` derivation via `req --base-path` and `req --git-path` before `req --git-wt-name`.
- `docs/WORKFLOW.md`: Updated `PROC:main` lifecycle behavior to require final repository-cleanliness verification via `req --git-check` and encode exclusive worktree-delete cleanup with explicit prohibition of rollback/revert git-state commands in post-create early termination branches.
- `docs/WORKFLOW.md`: Updated `PROC:main` lifecycle behavior to record global requirement-audit verification in `change`, `new`, and `fix` workflows with progressive-disclosure evidence.
- `docs/WORKFLOW.md`: Updated `PROC:main` lifecycle behavior to encode static-analysis verification, no-source static-check success handling, and conditional execution of existing unit-test suites via language-specific priority policy.
- `docs/WORKFLOW.md`: Updated `PROC:main` lifecycle behavior to encode defect-fix workflow preference for a reproducer unit-test-first sequence before source fixes when relevant suites exist.
