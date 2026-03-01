# Changelog

## [0.6.0](https://github.com/Ogekuri/Prompts/compare/v0.5.0..v0.6.0) - 2026-03-01
### 🐛  Bug Fixes
- Minor fixes.

## [0.5.0](https://github.com/Ogekuri/Prompts/compare/v0.4.0..v0.5.0) - 2026-03-01
### 🐛  Bug Fixes
- Remove placehoder from src.

## [0.4.0](https://github.com/Ogekuri/Prompts/compare/v0.3.0..v0.4.0) - 2026-03-01
### ⛰️  Features
- Add src/.place-holder file.

### 🐛  Bug Fixes
- Fix line numbers.
- Replace userReq with useReq.
- Fix .g.conf file.

### 🚜  Changes
- align req-find syntax and line prefixes [useReq] *(prompts)*
  - Update REQ-019 to codify req --find syntax semantics.
  - Apply Source Construct Extraction wording updates across affected prompts.
  - Set req --find examples without explicit --here, forbid --base wording, and use <n>: line prefix.
- enforce worktree cleanup verification [useReq] *(prompts)*
  - update REQ-019 with mandatory pre-step cleanup verification
  - add merge-success verification command to all worktree-based prompts
  - align WORKFLOW and REFERENCES docs with cleanup verification behavior
- Update <EXECUTION_ID> generation.

## [0.3.0](https://github.com/Ogekuri/Prompts/compare/v0.2.0..v0.3.0) - 2026-02-24
### 🐛  Bug Fixes
- Fix workflow file. *(core)*

## [0.2.0](https://github.com/Ogekuri/Prompts/compare/v0.1.0..v0.2.0) - 2026-02-24
### 🐛  Bug Fixes
- Remove src/.place-holder file. *(core)*

## [0.1.0](https://github.com/Ogekuri/Prompts/releases/tag/v0.1.0) - 2026-02-24
### ⛰️  Features
- add workflow. *(core)*
- add .place-holder files. *(core)*
- add guidelines/ and .gitignore. *(core)*
- cap prompt usage length [useReq] *(requirements)*
  - add REQ-027: YAML usage value length MUST be <= 1024
  - validate all prompt usage headers are within the limit
  - update workflow/references docs for traceability
- add readme prompt workflow [useReq] *(prompts)*
  - add src/prompts/readme.md derived from workflow prompt
  - append REQ-015 and RDM-* prompt-specific requirements
  - update WORKFLOW/REFERENCES docs for README-facing workflow
- add docs/REQUIREMENTS.md draft. *(core)*
- simplify doxygen templates. *(core)*
- review README.md. *(core)*
- add REQUIREMENTS.md. *(core)*
- initial commit. *(core)*

### 🐛  Bug Fixes
- Fix .g.conf file. *(core)*
- fix remove branch of worktree. *(core)*
- update the workflow script. *(core)*
- req. with req- *(core)*
- minor fix on src/prompts/change.md. *(core)*
- update docs/REQUIREMENTS.md. *(core)*
- update docs/REQUIREMENTS.md. *(core)*
- update docs/REQUIREMENTS.md. *(core)*
- update docs/REQUIREMENTS.md. *(core)*
- update docs/REQUIREMENTS.md. *(core)*
- update docs/REQUIREMENTS.md. *(core)*
- update docs/REQUIREMENTS.md. *(core)*
- update docs/REQUIREMENTS.md. *(core)*
- update docs/REQUIREMENTS.md. *(core)*
- update docs/REQUIREMENTS.md. *(core)*
- update docs/REQUIREMENTS.md. *(core)*
- update docs/REQUIREMENTS.md. *(core)*
- update docs/REQUIREMENTS.md. *(core)*
- BRAKING typo. *(core)*
- update docs/REQUIREMENTS.md. *(core)*

### 🚜  Changes
- use worktree path for config cleanup [useReq] *(worktree)*
  - Update REQ-019 with explicit worktree cleanup target path.
  - Align all worktree-capable prompts to remove copied config from worktree path before merge.
- prioritize test-oriented defect fix flow [useReq] *(prompts)*
  - update FIX requirements for preferred test-first bug-fix sequence
  - add constrained no-test fallback when one-test reproduction is costly/infeasible
  - align fix prompt behavior/steps and workflow/references traceability
- tighten scoped README edit rules [useReq] *(readme)*
  - update RDM requirements for section-scoped README edits
  - require preserving non-analysis sections and existing format
  - align readme prompt behavior/steps plus workflow and references docs
- normalize workflow wording tokens [useReq] *(requirements)*
  - Refine section 3.3 step wording to use WORKFLOW document contract.
  - Keep DOC-002 and DOC-003 normalization valid after wording cleanup.
- normalize DOC-002 DOC-003 wording [useReq] *(requirements)*
  - Normalize requirement wording in docs/REQUIREMENTS.md section 3.3.
  - Replace non-RFC modal verbs with RFC2119-compliant wording.
  - Normalize listed requirement lines to single-sentence statements.
- rewrite prompt-specific semantics [useReq] *(requirements)*
  - Rework section 3.3 requirements to describe prompt-construction behavior.
  - Remove implementation-reference wording based on exact-text equality and file linkage.
  - Preserve prompt-specific IDs and step granularity while expressing normative intent directly.
- complete prompt section mappings [useReq] *(requirements)*
  - Replace all TODO placeholders in prompt-specific requirements.
  - Add atomic context requirements for Purpose, Scope, Professional Personas, and Behavior sections.
  - Add one step requirement per numbered Step for all prompts under src/prompts/.
  - Remove duplicate orphan TODO block under Renumber section.
- handle gitignored req config in worktree/merge [useReq] *(prompts)*
  - update REQ-019 for canonical .req/config.json handling
  - add copy step after worktree creation in affected prompts
  - add remove step before merge in affected prompts
  - refresh WORKFLOW.md and REFERENCES.md for changed artifacts
- add rule-coverage function requirements [useReq] *(requirements)*
  - Update REQ-015/REQ-016 wording for Section 2.3 traceability.
  - Add REQ-017..REQ-026 to encode Section 1.5 rule checks.
  - Embed explicit exception clauses so current prompt/template corpus remains valid.
- rewrite absolute rules for LLM clarity [useReq] *(core)*
  - update section 1.5 wording for LLM-focused clarity\n- remove redundant repeated action directives\n- keep requirement semantics and scope intact
- add governance constraints for prompt/template maintenance [useReq] *(requirements)*
  - Update PRJ-008 to require explicit change requests for prompt/template artifact changes.
  - Add CTN-013 and CTN-014 to keep prompt/template governance rules only in docs/REQUIREMENTS.md.
  - Add TST-009 and TST-010 for governance and change-request traceability checks.

### 📚  Documentation
- add readme prompt to prompt catalog [useReq] *(prompts)*
  - add `readme` prompt entry under Prompts and Agents\n- describe README alignment behavior from user-visible evidence


# History

- \[0.1.0\]: https://github.com/Ogekuri/Prompts/releases/tag/v0.1.0
- \[0.2.0\]: https://github.com/Ogekuri/Prompts/releases/tag/v0.2.0
- \[0.3.0\]: https://github.com/Ogekuri/Prompts/releases/tag/v0.3.0
- \[0.4.0\]: https://github.com/Ogekuri/Prompts/releases/tag/v0.4.0
- \[0.5.0\]: https://github.com/Ogekuri/Prompts/releases/tag/v0.5.0
- \[0.6.0\]: https://github.com/Ogekuri/Prompts/releases/tag/v0.6.0

[0.1.0]: https://github.com/Ogekuri/Prompts/releases/tag/v0.1.0
[0.2.0]: https://github.com/Ogekuri/Prompts/compare/v0.1.0..v0.2.0
[0.3.0]: https://github.com/Ogekuri/Prompts/compare/v0.2.0..v0.3.0
[0.4.0]: https://github.com/Ogekuri/Prompts/compare/v0.3.0..v0.4.0
[0.5.0]: https://github.com/Ogekuri/Prompts/compare/v0.4.0..v0.5.0
[0.6.0]: https://github.com/Ogekuri/Prompts/compare/v0.5.0..v0.6.0
