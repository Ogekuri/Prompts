# References

## Requirements Source

- `docs/REQUIREMENTS.md`: Canonical requirements set for prompt behavior and shared operational instructions.

## Updated Prompt Artifacts

- `src/prompts/{change,cover,fix,implement,new,readme,recreate,refactor,references,renumber,workflow}.md`: Updated worktree-context and worktree-generation instructions to retain literal `req` results, require simple sequential execution, and avoid shell-composed multi-step command synthesis.

## Runtime Skill Artifacts

- `.github/skills/{req-change,req-cover,req-fix,req-implement,req-new,req-readme,req-recreate,req-refactor,req-references,req-renumber,req-workflow}/SKILL.md`: Updated runtime worktree-context and worktree-generation instructions to retain literal `req` results, require simple sequential execution, and avoid shell-composed multi-step command synthesis.

## Requirement Updates

- `docs/REQUIREMENTS.md`: Updated `REQ-019` to require literal sequential `req` command usage when workflows retrieve values for later reuse and to forbid shell-composed multi-step command synthesis using command substitution, backticks, indirect expansion, parameter transformation, nested substitution, or shell-derived helper composition.

## Workflow Model Update

- `docs/WORKFLOW.md`: Updated `PROC:main` lifecycle behavior to encode literal-result retention, simple sequential `req` execution, and the prohibition on shell-composed multi-step command synthesis for worktree-enabled workflows.
