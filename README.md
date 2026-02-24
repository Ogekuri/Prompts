# useReq/req (0.1.0)

<p align="center">
  <img src="https://img.shields.io/badge/python-3.11%2B-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python 3.11+">
  <img src="https://img.shields.io/badge/license-GPL--3.0-491?style=flat-square" alt="License: GPL-3.0">
  <img src="https://img.shields.io/badge/platform-Linux-6A7EC2?style=flat-square&logo=terminal&logoColor=white" alt="Platforms">
  <img src="https://img.shields.io/badge/docs-live-b31b1b" alt="Docs">
<img src="https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/uv/main/assets/badge/v0.json" alt="uv">
</p>

<p align="center">
<strong>The <u>prompts</u> for <strong>useReq/req</strong> project.</strong><br>
This repository maintains the prompt set in `src/prompts/` and the documentation templates in `src/docs/` used by the useReq SRS-driven workflow.
</p>

<p align="center">
  <a href="#quick-start">Quick Start</a> |
  <a href="#feature-highlights">Feature Highlights</a> |
  <a href="#prompts-and-agents">Prompts and Agents</a> |
  <a href="#templates">Templates</a> |
  <a href="#usage">Usage</a>
</p>

<p align="center">
<br>
🚧 <strong>DRAFT:</strong>Preliminary Version 📝 - Work in Progress 🏗️ 🚧<br>
⚠️ <strong>IMPORTANT NOTICE</strong>: Created with <a href="https://github.com/Ogekuri/useReq"><strong>useReq/req</strong></a> 🤖✨ ⚠️<br>
<br>
<p>


## Feature Highlights
- Prompt catalog for SRS-driven development (`Requirements -> Design -> Implementation -> Verification`).
- Dedicated prompts for requirement authoring, validation, implementation, and maintenance workflows.
- Reusable template documents for SRS writing, source-code documentation, and unit-test authoring.
- Consistent placeholder-based integration with useReq installation variables.


## Prompts and Agents
| Prompt | Purpose | How it works |
| --- | --- | --- |
| `analyze` | Produce an analysis report. | Performs read-only investigation with requirement/workflow/reference evidence and outputs structured findings. |
| `change` | Update requirements and implement corresponding changes. | Modifies existing requirement IDs and applies aligned code/test updates. |
| `check` | Run the requirements check. | Audits all requirement IDs and returns requirement-by-requirement OK/FAIL evidence. |
| `cover` | Cover uncovered existing requirements. | Implements minimal deltas for specific uncovered requirement IDs without changing SRS. |
| `create` | Draft SRS from existing source code. | Generates `REQUIREMENTS.md` from codebase evidence when implementation already exists. |
| `fix` | Fix a defect without changing requirements. | Restores compliance for incorrect behavior while keeping SRS unchanged. |
| `implement` | Implement source code from requirements. | Builds missing implementation from authoritative SRS without changing requirements. |
| `new` | Add a new requirement and corresponding implementation. | Appends additive requirement IDs and implements related code/test changes. |
| `readme` | Align root `README.md` with implementation evidence. | Updates user-facing README usage based on current external interface surfaces. |
| `recreate` | Reorganize and update SRS from source evidence. | Rewrites SRS structure while preserving existing requirement IDs. |
| `refactor` | Optimize internals without requirement changes. | Improves maintainability/performance while preserving external behavior. |
| `references` | Generate `REFERENCES.md` from source code. | Rebuilds reference index for modules, entrypoints, and dependencies. |
| `renumber` | Renumber SRS requirement IDs deterministically. | Renumbers IDs and internal references without altering requirement text/order. |
| `workflow` | Generate `WORKFLOW.md` from source code. | Produces runtime model with execution units, call traces, and communication edges. |
| `write` | Draft SRS from user request text. | Authors `REQUIREMENTS.md` from textual request in greenfield/kickoff scenarios. |


## Templates
| Template | Purpose | How it works |
| --- | --- | --- |
| `src/docs/Document_Source_Code_in_Doxygen_Style.md` | Source-code documentation standard. | Defines mandatory Doxygen/LLM-first rules for documenting code components. |
| `src/docs/HDT_Test_Authoring_Guide.md` | Unit-test authoring standard. | Defines deterministic, isolated, level-based HDT testing rules for LLM agents. |
| `src/docs/Requirements_Template.md` | SRS authoring template. | Provides canonical structure and rules for `REQUIREMENTS.md` drafting and updates. |


## Quick Start

1. Clone this repository and keep it versioned alongside your useReq project.
2. Copy the required prompt files from `src/prompts/` into your target prompt installation path.
3. Copy required templates from `src/docs/` into your target docs/template installation path.
4. Ensure installation-time placeholders are preserved exactly:
   - `%%ARGS%%`
   - `%%DOC_PATH%%`
   - `%%GUIDELINES_FILES%%`
   - `%%SRC_PATHS%%`
   - `%%TEST_PATH%%`
5. Run your usual useReq workflow by selecting the prompt that matches the current task.



## Usage

Use this repository as the canonical source for prompt/template maintenance.
