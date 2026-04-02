# References

## Requirements Source

- `docs/REQUIREMENTS.md`: Canonical requirements set for prompt behavior and shared operational instructions.

## Updated Prompt Artifacts

- `src/prompts/{analyze,change,check,cover,create,fix,implement,new,readme,recreate,refactor,references,renumber,workflow,write}.md`: Updated the shared shell-command safety rule to require verification and application of correct quoting, escaping, or option termination for literal arguments that could be parsed as options or flags.

## Requirement Updates

- `docs/REQUIREMENTS.md`: Split the shell-command constraint so `REQ-020` keeps the linear-command requirement, `REQ-029` isolates the prohibition on command substitution and nested shell composition, and `REQ-030` requires correct quoting, escaping, or option termination for literal option-like arguments.

## Workflow Model Update

- `docs/WORKFLOW.md`: Updated `PROC:main` lifecycle behavior to encode the shared shell-command rule for safe handling of literal option-like arguments.
