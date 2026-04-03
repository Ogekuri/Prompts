# References

## Requirements Source

- `docs/REQUIREMENTS.md`: Canonical requirements set for prompt behavior and shared operational instructions.

## Updated Prompt Artifacts

- `src/prompts/{analyze,change,check,cover,create,fix,implement,new,readme,recreate,refactor,references,renumber,workflow,write}.md`: Updated the shared shell-command safety rule to require explicit option termination for `rg` and `git grep` patterns that begin with `-` or `--`, and to forbid reliance on quoting or backslash escaping alone for those patterns.

## Requirement Updates

- `docs/REQUIREMENTS.md`: Updated `REQ-030` to require explicit option termination for `rg` and `git grep` patterns that begin with `-` or `--`, and added `REQ-031` to forbid reliance on quoting or backslash escaping alone for those patterns.

## Workflow Model Update

- `docs/WORKFLOW.md`: Updated `PROC:main` lifecycle behavior to encode the explicit option-termination rule for `rg` and `git grep` patterns that begin with `-` or `--`.
