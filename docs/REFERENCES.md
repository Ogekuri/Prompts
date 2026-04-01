# References

## Requirements Source

- `docs/REQUIREMENTS.md`: Canonical requirements set for prompt behavior and shared operational instructions.

## Updated Prompt Artifacts

- `src/prompts/{analyze,change,check,cover,create,fix,implement,new,readme,recreate,refactor,references,renumber,workflow,write}.md`: Updated absolute shell-safety rules to require restrictive-filter-compatible linear commands and updated worktree context instructions where worktree workflows reuse command results.

## Runtime Skill Artifacts

- `.github/skills/{req-change,req-cover,req-fix,req-implement,req-new,req-readme,req-recreate,req-refactor,req-references,req-renumber,req-workflow}/SKILL.md`: Updated runtime worktree-context and shell-safety instructions to require restrictive-filter-compatible linear commands and forbid command substitution, complex variable expansion, nested substitution, shell-derived helpers, nested shell logic, and nested pipelines.

## Requirement Updates

- `docs/REQUIREMENTS.md`: Updated `REQ-019` to keep literal sequential `req` command usage for reusable command results and added `REQ-020` to require restrictive-filter-compatible linear shell commands that forbid command substitution, backticks, complex variable expansion, nested substitution, shell-derived helpers, nested shell logic, and nested pipelines.

## Workflow Model Update

- `docs/WORKFLOW.md`: Updated `PROC:main` lifecycle behavior to encode literal-result retention, simple sequential `req` execution, and restrictive-filter-compatible linear shell command generation rules.
