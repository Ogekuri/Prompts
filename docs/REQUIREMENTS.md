---
title: "Prompts Project Requirements"
description: Software requirements specification
version: "0.2.0"
date: "2026-02-23"
author: "req-write"
scope:
  paths:
    - "src/prompts/**/*.md"
    - "src/docs/**/*.md"
    - "README.md"
  excludes:
    - ".*/**"
visibility: "draft"
tags: ["srs", "prompts", "templates"]
---

# Prompts Project Requirements

## 1. Introduction

### 1.1 Document Rules
Prefix `DOC` is reserved for document-authoring constraints in this section.

- **DOC-001**: MUST write and maintain this document in English.
- **DOC-002**: MUST use only RFC 2119 keywords (MUST, MUST NOT, SHOULD, SHOULD NOT, MAY) and MUST NOT use "shall".
- **DOC-003**: MUST express every requirement bullet using the canonical format `- **<ID>**: <RFC2119 keyword> <single-sentence requirement>.`.
- **DOC-004**: MUST keep requirement IDs unique, stable, and non-repurposed across revisions.
- **DOC-005**: MUST write requirements for LLM Agents and automated parsers using high semantic density and no conversational filler.

### 1.2 Project Scope
This project defines and maintains prompt and template artifacts used by the useReq process to enforce SRS-driven development with the sequence Requirements -> Design -> Implementation -> Verification.

### 1.3 Assumptions
- No application runtime source code is in scope for this SRS.
- No mandatory third-party runtime library was requested.
- Verification can be implemented with deterministic textual checks on Markdown artifacts.

## 2. Project Requirements

### 2.1 Project Functions
- **PRJ-001**: MUST maintain prompt artifacts in `src/prompts/` for SRS-driven workflows.
- **PRJ-002**: MUST maintain template artifacts in `src/docs/` as mandatory authoring guides.
- **PRJ-003**: MUST maintain `README.md` as the operational index for prompts and templates.
- **PRJ-004**: MUST define each prompt with a single primary workflow intent and deterministic output objective.
- **PRJ-005**: MUST preserve the process order Requirements -> Design -> Implementation -> Verification when edits prompt instructions.
- **PRJ-006**: `docs/REQUIREMENTS.md` MUST include role classifications for prompts that generate, review, or consume `%%DOC_PATH%%/REQUIREMENTS.md`.
- **PRJ-007**: `docs/REQUIREMENTS.md` MUST include role classifications for prompts that generate, review, or consume `%%DOC_PATH%%/WORKFLOW.md`.
- **PRJ-008**: MUST allow adding or removing prompt/template files only through an explicit change request that updates `docs/REQUIREMENTS.md` and documents the artifact delta.

### 2.2 Project Constraints
- **CTN-001**: When you edits prompt and template, LLM agent MUST act as a Senior AI Prompt Engineer and Senior LLM-Ops Engineer.
- **CTN-002**: When you edits `README.md`, LLM agent MUST as a Technical Writer activity.
- **CTN-003**: MUST NOT modify placeholders `%%ARGS%%`, `%%DOC_PATH%%`, `%%GUIDELINES_FILES%%`, `%%SRC_PATHS%%`, and `%%TEST_PATH%%`.
- **CTN-004**: MUST NOT change the files referenced by `%%ARGS%%`, `%%DOC_PATH%%`, `%%GUIDELINES_FILES%%`, `%%SRC_PATHS%%`, and `%%TEST_PATH%%` through placeholder redefinition.
- **CTN-005**: MUST ensure prompts and templates are free of typographical errors.
- **CTN-006**: MUST ensure prompts and templates are free of grammatical errors.
- **CTN-007**: MUST enforce uniform terminology and semantics across prompts for identical actions, references, and process keywords.
- **CTN-008**: MUST reuse identical instruction phrasing when different prompts describe the same action.
- **CTN-009**: MUST NOT include instructions that interrupt agent reasoning flow unless the interruption is explicitly required by workflow conditions.
- **CTN-010**: MUST NOT include instructions that increase hallucination risk unless explicitly required by a formal requirement.
- **CTN-011**: MUST optimize prompts for LLM context efficiency and token economy.
- **CTN-012**: MUST target all prompts and templates to LLM Agent processing and MUST NOT target human-only reading.
- **CTN-013**: MUST NOT include in `src/prompts/` or `src/docs/` any governance instructions describing how prompts or templates are maintained, edited, or verified.
- **CTN-014**: MUST store all governance rules for prompt/template maintenance, modification, and verification exclusively in `docs/REQUIREMENTS.md`.

### 2.3 In-Scope Artifacts
| Category | Path | Intended Function |
| --- | --- | --- |
| Prompt | `src/prompts/analyze.md` | Produce an analysis report. |
| Prompt | `src/prompts/change.md` | Update requirements and implement corresponding changes. |
| Prompt | `src/prompts/check.md` | Run requirements compliance checks. |
| Prompt | `src/prompts/cover.md` | Implement deltas that cover unmet requirements. |
| Prompt | `src/prompts/create.md` | Draft SRS from project source evidence. |
| Prompt | `src/prompts/fix.md` | Fix defects without changing requirements. |
| Prompt | `src/prompts/implement.md` | Implement code from requirements. |
| Prompt | `src/prompts/new.md` | Add new requirements and implement corresponding changes. |
| Prompt | `src/prompts/recreate.md` | Reorganize and renumber the SRS. |
| Prompt | `src/prompts/refactor.md` | Optimize internals without requirement changes. |
| Prompt | `src/prompts/references.md` | Draft `REFERENCES.md` from source evidence. |
| Prompt | `src/prompts/renumber.md` | Renumber SRS requirements deterministically. |
| Prompt | `src/prompts/workflow.md` | Draft `WORKFLOW.md` from source evidence. |
| Prompt | `src/prompts/write.md` | Draft SRS from user-request text. |
| Template | `src/docs/Document_Source_Code_in_Doxygen_Style.md` | Mandatory source-code documentation guideline. |
| Template | `src/docs/HDT_Test_Authoring_Guide.md` | Mandatory unit-test authoring guideline. |
| Template | `src/docs/Requirements_Template.md` | Mandatory SRS authoring guideline. |
| Document | `README.md` | Project-level prompt and template documentation. |

## 3. Requirements

### 3.1 Design and Implementation
- **DES-001**: MUST organize artifacts into dedicated prompt, template, and project-documentation components with explicit responsibilities.
- **DES-002**: MUST implement a deterministic prompt taxonomy for `%%DOC_PATH%%/REQUIREMENTS.md` with generator, reviewer, and consumer roles.
- **DES-003**: MUST map `create.md`, `recreate.md`, and `write.md` as generators of `%%DOC_PATH%%/REQUIREMENTS.md`.
- **DES-004**: MUST map `change.md`, `new.md`, and `renumber.md` as reviewers of `%%DOC_PATH%%/REQUIREMENTS.md`.
- **DES-005**: MUST map `change.md`, `new.md`, `renumber.md`, `recreate.md`, `analyze.md`, `check.md`, `cover.md`, `implement.md`, `refactor.md`, and `workflow.md` as consumers of `%%DOC_PATH%%/REQUIREMENTS.md`.
- **DES-006**: MUST implement a deterministic prompt taxonomy for `%%DOC_PATH%%/WORKFLOW.md` with generator, reviewer, and consumer roles.
- **DES-007**: MUST map `workflow.md` and `implement.md` as generators of `%%DOC_PATH%%/WORKFLOW.md`.
- **DES-008**: MUST map `change.md`, `cover.md`, `fix.md`, `new.md`, and `refactor.md` as reviewers of `%%DOC_PATH%%/WORKFLOW.md`.
- **DES-009**: MUST map `analyze.md`, `change.md`, `check.md`, `cover.md`, `fix.md`, `new.md`, `recreate.md`, and `refactor.md` as consumers of `%%DOC_PATH%%/WORKFLOW.md`.
- **DES-010**: MUST standardize repeated operational instructions, including Git-state checks and completion or error messages, using identical wording across prompts.
- **DES-011**: MUST implement text-first interaction semantics and MUST NOT require GUI-specific behavior.
- **DES-012**: MUST preserve reusable keyword tokens exactly so installation-time substitution remains valid.

Proposed repository structure (max depth 3, depth 4 for `src/`):

```text
Prompts/
├── README.md
├── docs/
│   └── REQUIREMENTS.md
└── src/
    ├── docs/
    │   ├── Document_Source_Code_in_Doxygen_Style.md
    │   ├── HDT_Test_Authoring_Guide.md
    │   └── Requirements_Template.md
    └── prompts/
        ├── analyze.md
        ├── change.md
        ├── check.md
        ├── cover.md
        ├── create.md
        ├── fix.md
        ├── implement.md
        ├── new.md
        ├── recreate.md
        ├── refactor.md
        ├── references.md
        ├── renumber.md
        ├── workflow.md
        └── write.md
```

### 3.2 Functions
- **REQ-001**: MUST define `analyze.md` to produce a read-only analysis report from available project artifacts.
- **REQ-002**: MUST define `change.md` to modify requirements and implement corresponding project changes in a single controlled workflow.
- **REQ-003**: MUST define `check.md` to evaluate requirement compliance and report requirement-level pass or fail outcomes.
- **REQ-004**: MUST define `cover.md` to implement focused deltas that satisfy explicitly uncovered requirement IDs.
- **REQ-005**: MUST define `create.md` to draft an SRS from repository evidence when source implementation already exists.
- **REQ-006**: MUST define `fix.md` to correct behavior defects without modifying requirement intent.
- **REQ-007**: MUST define `implement.md` to implement missing functionality from an authoritative SRS baseline.
- **REQ-008**: MUST define `new.md` to append strictly additive requirements and implement corresponding deltas.
- **REQ-009**: MUST define `recreate.md` to reorganize and NOT renumber an SRS while preserving requirement intent.
- **REQ-010**: MUST define `refactor.md` to improve internals while preserving externally observable behavior and requirement compliance.
- **REQ-011**: MUST define `references.md` to generate `REFERENCES.md` from source-code evidence only.
- **REQ-012**: MUST define `renumber.md` to enforce deterministic requirement ID sequencing in SRS documents.
- **REQ-013**: MUST define `workflow.md` to generate `WORKFLOW.md` from source-code execution evidence.
- **REQ-014**: MUST define `write.md` to generate an SRS from user-request text without relying on source-code evidence.
- **REQ-015**: MUST require `README.md` to document purpose and operating behavior for every prompt file in scope.
- **REQ-016**: MUST require `README.md` to document purpose and operating behavior for every template file in scope.

## 4. Test Requirements

Act as act as a Senior AI Prompt Engineer, Senior LLM-Ops Engineer, and an expert static code analyst. Your task is to validate and review the provided promts and templates. STRICT CONSTRAINT: You must not write, suggest, or execute any unit tests, integration tests, or dynamic tests. All prompts validation, bug hunting, and testing must be performed strictly through static code analysis READING promts and templates.

- **TST-001**: MUST verify that all in-scope prompt, template, and README paths exist and are documented in the SRS scope matrix.
- **TST-002**: MUST verify placeholder tokens `%%ARGS%%`, `%%DOC_PATH%%`, `%%GUIDELINES_FILES%%`, `%%SRC_PATHS%%`, and `%%TEST_PATH%%` remain unchanged in maintained artifacts.
- **TST-003**: MUST verify prompts and templates pass typo, and grammar quality checks with deterministic pass or fail output.
- **TST-004**: MUST verify identical actions across prompts use identical canonical instruction phrasing.
- **TST-005**: MUST verify prompt role mappings for `%%DOC_PATH%%/REQUIREMENTS.md` and `%%DOC_PATH%%/WORKFLOW.md` match requirements DES-003 through DES-009.
- **TST-006**: MUST verify prompts do not include unauthorized chain-interrupt instructions outside explicitly defined workflow interruption points.
- **TST-007**: MUST verify prompts and templates are optimized for LLM-Agent consumption and avoid unnecessary token-heavy content.
- **TST-008**: MUST verify `README.md` documents scope and behavior for every prompt and template listed in section 2.3.
- **TST-009**: MUST verify `src/prompts/` and `src/docs/` do not contain governance instructions about maintaining, editing, or verifying prompts/templates.
- **TST-010**: MUST verify prompt/template file additions or removals are accompanied by an explicit change request and corresponding `docs/REQUIREMENTS.md` updates.
