# References

## Requirements Source

- `docs/REQUIREMENTS.md`: Canonical requirements set for prompt behavior, prompt inventory, and shared operational instructions.

## Updated Prompt Artifacts

- `src/prompts/flowchart.md`: Adds FLOWCHART-only maintenance workflow that generates `docs/FLOWCHART.md` as a Mermaid flowchart from source evidence, grouping primary-flow phases, extracting atomic parameterless prototypes, and verifying branches and joins against the runtime model.

## Requirement Updates

- `docs/REQUIREMENTS.md`: Updates the prompt inventory for `src/prompts/flowchart.md`, adds `REQ-016`, and adds `FCH-CTX-001..017` plus `FCH-STP-001..010` for the new flowchart prompt.

## Workflow Model Update

- `docs/WORKFLOW.md`: Updates `PROC:main` prompt-artifact entrypoints to include `src/prompts/flowchart.md`.
