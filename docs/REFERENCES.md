# References

## Requirements Source

- `docs/REQUIREMENTS.md`: Canonical PI-Prompts requirements set for prompt behavior, prompt inventory, shared operational instructions, and repository naming rule `PRJ-005`.

## Updated Repository Artifacts

- `README.md`: Repository-facing documentation updated to identify the project as `PI-Prompts`; satisfies `PRJ-005`.
- `docs/WORKFLOW.md`: Runtime-model document updated to identify `PROC:main` as the PI-Prompts prompt-workflow orchestrator.

## Rename Impact Assessment

- `.github/workflows/release-markdown.yml`: No rename patch required; release naming already derives the repository name from `${{ github.event.repository.name }}`.
- `src/prompts/`: No content edits applied; excluded by user request.
- `src/docs/`: No content edits applied; excluded by user request.
- `guidelines/`: No content edits applied; excluded by user request.
