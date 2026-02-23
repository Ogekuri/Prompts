---
title: "Prompts Project Requirements"
description: Software requirements specification
version: "0.2.1"
date: "2026-02-23"
author: "req-write"
scope:
  paths:
    - "src/prompts/**/*.md"
    - "src/docs/**/*.md"
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
- **DOC-002**: MUST use only RFC 2119 keywords (MUST, MUST NOT, SHOULD, SHOULD NOT, MAY) and MUST NOT use modal verbs outside that set in requirement statements.
- **DOC-003**: MUST express every requirement bullet using the canonical format `- **<ID>**: <RFC2119 keyword> <single-sentence requirement>.`.
- **DOC-004**: MUST keep requirement IDs unique and non-repurposed within each published revision, and MUST update internal cross-references deterministically when IDs are renumbered.
- **DOC-005**: MUST write requirements for LLM Agents and automated parsers using high semantic density and no conversational filler.

### 1.2 Project Scope
This project defines and maintains prompt and template artifacts used by the useReq process to enforce SRS-driven development with the sequence Requirements -> Design -> Implementation -> Verification.

### 1.3 Assumptions
- No application runtime source code is in scope for this SRS.
- No mandatory third-party runtime library was requested.
- Verification can be implemented with deterministic textual checks on Markdown artifacts.
- **CRITICAL**: You MUST NOT write, suggest, or execute any unit tests, integration tests, or dynamic tests. All prompts and template validation, bug hunting, and testing must be performed strictly through static code analysis READING prompts and templates.

### 1.4 Persona
- When you edit prompts and templates, act as a Senior AI Prompt Engineer and Senior LLM-Ops Engineer.
- When performing checks and tests on prompts and templates, act as a Senior AI Prompt Engineer, Senior LLM-Ops Engineer, and an expert static code analyst. Your task is to validate and review the provided prompts and templates.

### 1.5 Absolute Rules, Non-Negotiable
- When editing prompt or template artifacts:
  - MUST preserve placeholder tokens `%%ARGS%%`, `%%DOC_PATH%%`, `%%GUIDELINES_FILES%%`, `%%SRC_PATHS%%`, and `%%TEST_PATH%%` exactly as-is.
  - MUST keep all prompt/template text free of typographical and grammatical errors.
  - MUST use uniform terminology and identical canonical instruction phrasing for identical actions, references, and process keywords.
  - MUST keep interruption rules explicit: prompts MUST NOT interrupt agent reasoning flow unless the interruption is required by defined workflow conditions.
  - MUST optimize prompts/templates for LLM-agent parsing, context efficiency, and token economy.
  - MUST target prompts/templates to LLM-agent execution and MUST NOT target human-only reading.
  - MUST require an explicit change request and corresponding `docs/REQUIREMENTS.md` update for any prompt/template file addition or removal.
  - MUST keep `src/prompts/` and `src/docs/` free of governance instructions about maintaining, editing, or verifying prompts/templates.
  - MUST NOT add instructions that increase hallucination risk unless explicitly required by a formal requirement.

## 2. Project Requirements

### 2.1 Project Functions
- **PRJ-001**: MUST maintain prompt artifacts in `src/prompts/` for SRS-driven workflows.
- **PRJ-002**: MUST maintain template artifacts in `src/docs/` as mandatory authoring guides.
- **PRJ-003**: MUST define each prompt with a single primary workflow intent and deterministic output objective.
- **PRJ-004**: MUST preserve the process order Requirements -> Design -> Implementation -> Verification when editing prompt instructions.

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

## 3. Requirements

### 3.1 Design and Implementation
- **DES-001**: MUST organize artifacts into dedicated prompt and template with explicit responsibilities.
- **DES-002**: MUST standardize repeated operational instructions, including Git-state checks and completion or error messages, using identical wording across prompts, except for the prompt's name specialization.
- **DES-003**: MUST implement text-first interaction semantics and MUST NOT require GUI-specific behavior.
- **DES-004**: MUST preserve reusable keyword tokens exactly so installation-time substitution remains valid.

Proposed repository structure (max depth 3, depth 4 for `src/`):

```text
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
- **REQ-017**: MUST validate placeholder tokens by allowing only `%%ARGS%%`, `%%DOC_PATH%%`, `%%GUIDELINES_FILES%%`, `%%SRC_PATHS%%`, and `%%TEST_PATH%%`, except artifacts that intentionally contain no placeholder tokens.
- **REQ-018**: MUST NOT contain typo and grammar errors, except fenced code blocks, inline-code spans, literal error strings, placeholders, and command snippets.
- **REQ-019**: MUST enforce canonical phrasing for shared operational instructions, including conditional `.req/config.json` copy during worktree setup and conditional `.req/config.json` removal before merge when `.gitignore` excludes that path.
- **REQ-021**: MUST optimize prompts/templates for parser efficiency and token economy, except mandatory compliance blocks (`Professional Personas`, `Execution Protocol`, `Execution Directives`, `Steps`) that are retained verbatim.
- **REQ-022**: MUST be optimized for LLM-Agent.
- **REQ-023**: MUST use identical canonical instruction phrasing for identical actions across prompts, outside explicitly prompt specifications, except where explicitly allowed below.
  - Workflow identity literals MAY vary where required to bind the emitting prompt (`/req.<name>`, commit-type prefix, workflow-specific title/scope text, and step labels tied to workflow intent).
  - Workflow-scoped failure or warning strings MAY vary only in workflow-name specialization while preserving the same control action pattern (`OUTPUT exactly "<STRING>"`, then terminate or override final line as explicitly defined).
  - Numeric bounds and scoped nouns MAY vary when they encode workflow-specific semantics (for example step-count cardinality and requirement-type nouns), while shared operational commands MUST remain byte-identical.
- **REQ-024**: MUST avoid instructions that cause unnecessary token-heavy content, except where explicitly allowed below.
  - Mandatory compliance blocks MAY remain verbose when retained verbatim by policy (`Professional Personas`, `Execution Protocol`, `Execution Directives`, and `Steps`).
  - Canonical executable literals MAY remain fully expanded where determinism depends on exact text (shell commands, fixed report schema, fixed error strings, and WORKFLOW.md schema contracts).
  - High-detail enumerations MAY be used only when they constrain behavior and reduce ambiguity (supported tag sets, allowed temp/cache paths, and explicit termination-condition matrices).
- **REQ-025**: MUST reject unauthorized chain-interrupt instructions outside explicitly defined workflow interruption points, except where explicitly allowed below.
  - Authorized interruption points are only the explicit Step branches that require exact-string output and immediate stop/override (git-status failure, required-file absence, incompatibility guards, test-loop exhaustion, and no-op commit termination).
  - Read-only or coverage workflows MAY emit a declared no-change terminal string when explicitly defined by that workflow step (for example "All requirements are already covered. No changes needed.").
  - Merge-conflict handling MAY override only the final status line with the predefined warning string, without adding new interruption branches.
- **REQ-026**: MUST reject new hallucination-risk instructions, except where explicitly allowed below.
  - Evidence-first high-recall directives MAY remain when uncertainty is explicitly downgraded to candidates and never asserted as complete without file-backed proof.
  - Autonomous disambiguation directives MAY remain only when constrained to least-invasive choices anchored to repository evidence and requirement traceability.
  - Tool-gated execution directives MAY require waiting for actual tool responses and exact-string outputs to prevent fabricated results.
