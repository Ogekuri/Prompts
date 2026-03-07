# References

## Requirements Source

- `docs/REQUIREMENTS.md`: Canonical requirements with shared operational-instruction constraints (`REQ-019`).

## Prompt Artifacts Updated for Worktree/Merge Cleanup Verification

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

- `src/prompts/{analyze,change,check,cover,create,fix,implement,new,readme,recreate,refactor,references,renumber,workflow,write}.md`: Terminal output literals now require bell-free exact strings for all fixed completion, warning, and error output strings (including final STATUS lines and exact-string early exits).
- `src/prompts/readme.md`: Behavior and Step 4 now enforce section-scoped README edits that also execute explicit additional edits from [User Request](#users-request) (`%%ARGS%%`), while preserving non-analysis content and existing structure/format when possible.
- `src/prompts/fix.md`: Behavior and Steps 4-5 now prefer a reproducer-test-first bug-fix flow with constrained fallback to no-test verification only when one-test guideline-compliant reproduction is too costly or infeasible.
- `src/prompts/{change,cover,fix,implement,new,recreate,refactor,references,readme,renumber,workflow}.md`: Merge-success cleanup now chains worktree removal with temporary branch deletion and requires explicit verification that both artifacts were deleted before the next step.
- `src/prompts/{analyze,change,check,cover,fix,implement,new,readme,recreate,refactor,references,renumber,workflow}.md`: Execution-context instructions now require `<EXECUTION_ID>` generation via `date +"%Y%m%d%H%M%S"` instead of UUID/`uuidgen`.
- `src/prompts/{change,cover,fix,implement,new,refactor}.md`: Doxygen coverage directives now explicitly include objects and structures in the mandatory documented component set.
- `src/prompts/workflow.md`: Professional Personas and Step 4 output-contract rules now require declaration file path references only in generated `docs/WORKFLOW.md`, excluding line numbers, line ranges, and internal file-reference pointers.
- `src/prompts/{change,cover,fix,implement,new,refactor}.md`: WORKFLOW-update steps now explicitly require declaration file paths only and explicitly forbid line numbers, line ranges, and internal file-reference pointers during `docs/WORKFLOW.md` generation/updates.
- `src/docs/Document_Source_Code_in_Doxygen_Style.md` and `.req/docs/Document_Source_Code_in_Doxygen_Style.md`: Canonical Doxygen guideline now explicitly includes objects and structures in mandatory component coverage.

## Requirement Updates

- `docs/REQUIREMENTS.md`: Updated `DES-002`, `REQ-023`, and `REQ-025` to remove terminal bell-marker suffix requirements and enforce bell-free exact-string outputs across completion, warning, and error termination paths.
- `docs/REQUIREMENTS.md`: Updated `REQ-019` to require `<EXECUTION_ID>` generation via `date +"%Y%m%d%H%M%S"`, successful-merge cleanup that removes both the temporary worktree and its isolated branch, and mandatory cleanup-verification before advancing steps.
- `docs/REQUIREMENTS.md`: Added `REQ-027` requiring all prompt YAML `usage` values to be generated with a maximum length of 1024 characters.
- `docs/REQUIREMENTS.md`: Updated `RDM-CTX-005` and `RDM-STP-004` to require `readme.md` to execute explicit additional edits from [User Request](#users-request) (`%%ARGS%%`) in the same targeted README update pass.
- `docs/REQUIREMENTS.md`: Updated `PRJ-002` to require prompt/template taxonomy alignment for Doxygen coverage directives.
- `docs/REQUIREMENTS.md`: Updated `WFL-CTX-003` and `WFL-STP-004` to require workflow output evidence as declaration file paths only and to exclude line numbers, line ranges, and internal file-reference pointers.
- `docs/REQUIREMENTS.md`: Updated `CHG-STP-007`, `COV-STP-006`, `FIX-STP-006`, `IMP-STP-006`, `NEW-STP-007`, and `RFR-STP-006` to require declaration file paths only and forbid line numbers, line ranges, and internal file-reference pointers during `docs/WORKFLOW.md` generation/updates.
- `docs/WORKFLOW.md`: Updated `PROC:main` role and lifecycle notes to enforce bell-free terminal output contracts in prompt workflow execution.
