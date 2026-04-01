# References

## Requirements Source

- `docs/REQUIREMENTS.md`: Canonical requirements set for prompt behavior and shared operational instructions.

## Updated Prompt Artifacts

- `src/prompts/analyze.md`: Final analysis-report instruction now targets human readers with clear sentences and readable Markdown while preserving the fixed report schema and exact final status line.
- `src/prompts/{change,cover,create,fix,implement,new,readme,recreate,refactor,references,renumber,workflow}.md`: Final results instruction now targets human readers with clear sentences and readable Markdown while preserving the fixed report schema and exact final status line.
- `src/prompts/check.md`: Final requirements-check report instruction now targets human readers with clear sentences and readable Markdown while preserving the fixed report schema and exact final status line.
- `src/prompts/write.md`: Final structured-summary instruction now targets human readers with clear sentences and readable Markdown while preserving the fixed report schema and exact final status line.

## Runtime Skill Artifacts

- `.github/skills/req-analyze/SKILL.md`: Final analysis-report instruction now targets human readers with clear sentences and readable Markdown while preserving the fixed report schema and exact final status line.
- `.github/skills/{req-change,req-cover,req-create,req-fix,req-implement,req-new,req-readme,req-recreate,req-refactor,req-references,req-renumber,req-workflow,req-write}/SKILL.md`: Final results instruction now targets human readers with clear sentences and readable Markdown while preserving the fixed report schema and exact final status line.
- `.github/skills/req-check/SKILL.md`: Final requirements-check report instruction now targets human readers with clear sentences and readable Markdown while preserving the fixed report schema and exact final status line.

## Requirement Updates

- `docs/REQUIREMENTS.md`: Updated `ANZ-STP-002` to require a human-readable analysis report that keeps the fixed report schema and exact final status line.
- `docs/REQUIREMENTS.md`: Updated `CHG-STP-011`, `COV-STP-010`, `CRT-STP-003`, `FIX-STP-010`, `IMP-STP-010`, `NEW-STP-011`, `RCR-STP-008`, `RFR-STP-010`, `REF-STP-006`, `RNB-STP-008`, `WFL-STP-007`, `WRT-STP-002`, and `RDM-STP-007` to require human-readable final reports that keep the fixed report schema and exact final status line.
- `docs/REQUIREMENTS.md`: Updated `CHK-STP-003` to require a human-readable requirements-check report and Implementation Delta that keep the fixed report schema and exact final status line.

## Workflow Model Update

- `docs/WORKFLOW.md`: Updated `PROC:main` lifecycle behavior to encode that final report instructions preserve the fixed report schema and exact final status line while explicitly targeting human readers with clear sentences and readable Markdown formatting.
