# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

This is not a software project — there is no code to build, lint, or test. It is a Claude Code **skill-creator project**: a working directory used to iteratively develop and exercise `SKILL_v1.10.md`, a skill that parses audio equipment (amplifiers/controllers) spec data from heterogeneous sources (owner's manuals, spec sheet PDFs, A&E docx specs, website tiers) into unified master-schema markdown files, one per product.

There is no build/test/run command. "Doing work" in this repo means: reading source documents under `Original_PDFs/` and `Raw_Web_Data/`, and producing/updating the master schema `.md` files at the repo root, strictly per the rules in the current `SKILL_v*.md`.

## Essential starting point

**Always read the current-highest-numbered `SKILL_v*.md` at the root first** — it is the full ruleset and takes precedence over anything summarized here. This CLAUDE.md only orients you; it does not restate parsing rules.

Also read `Session_Transfer_v*.md` (highest version at root) for the up-to-date project status, what phase the project is in, and outstanding next steps. Note: `Session_Transfer` can lag behind actual repo state (e.g. new products added to root after the last transfer note was written) — when the two disagree, trust the actual files at root over the narrative in Session_Transfer, and treat the mismatch as a sign the transfer note is due for an update.

## Repository layout

- Root: exactly one latest file per category — `SKILL_v{X.Y}.md` (the skill/ruleset) and one `{Product}_v{X.Y}.md` per product (master schema). No other files belong at root.
- `Original_PDFs/{Product}/` — untouched original source documents (OM PDF, SPS PDF, AE docx), one subfolder per product. Never edit these. Naming convention: `{Product}_{DocType}_EN_{Version}.{ext}` where DocType is OM/SPS/AE.
- `Raw_Web_Data/{Product}_Raw_Web_Data.md` — verbatim, unedited merge of copy-pasted website tiers (list view/overview/full spec) and any non-PDF text sources (e.g. txt A&E). Never paraphrase or clean this up.
- `Archive/Archive_Skill/` — every superseded `SKILL_v*.md`.
- `Archive/Archive_Data/{Product}/` — every superseded `{Product}_v*.md`.
- `Archive/Archive_Meta/` — every superseded `Session_Transfer_v*.md`.
- Small per-folder `CLAUDE.md` files exist inside `Archive/Archive_Data/` and `Original_PDFs/` giving local filing conventions for those folders specifically — read those when working inside them.

## Core workflow rules (see SKILL.md for full detail — this is a map, not the ruleset)

- **Dynamic schema discovery**: manufacturer-specific terms get normalized to snake_case engineering keys; a brand's genuinely novel spec concepts get their own `{brand}_specific` section rather than being force-fit into existing keys.
- **Bidirectional schema sync (mandatory)**: every master schema file for products managed together must have an *identical* key list and section structure. A new key found in one product's source gets added as `null` to every other product file, and vice versa. Every product-file output round must re-verify 100% key-list parity across all files, not just update the one product being worked on.
- **Integrity**: never fabricate values, never silently merge conflicting source values (both are preserved with footnotes explaining the conflict and which was adopted), never add unsupported modifiers/marketing language, never derive totals not explicitly stated in a source. Distinguish confirmed-absent (`0`, only after a full-document scan) from unconfirmed (`null`).
- **Table purity**: data tables contain only Key/Value/Unit. Sourcing, measurement conditions, and adoption rationale go in a `### 주석 및 출처 (Notes & Sources)` block below the table, at section granularity — not per-cell footnotes except for genuinely exceptional values.
- **No emoji/decorative icons** anywhere in the skill doc or output files.
- **Surgical Versioning Protocol (strict order, do not violate)**: when producing a new version of any tracked file (SKILL or a product schema), the sequence is (1) duplicate the current file under the new version filename with zero edits, (2) move the original old-version file into the matching `Archive/` subfolder, (3) only then apply targeted edits to the new file. Never edit the original in place before it's archived — this exact violation happened once already (see SKILL v1.10 changelog) and required manual recovery from Archive. Also never do a full Write-tool rewrite of a large existing file from scratch; prefer Duplicate + Edit.
- No `_latest`/`_final`/`_current` filename tags — versioning is purely `_v{Major}.{Minor}` semantic versioning (Minor: additive/backward-compatible; Major: schema section-structure or parsing-rule overhaul).

## Practical notes

- Master schema files can be large (25–40 KB); when verifying a file's completeness after writing, prefer the Read tool (full read, or targeted offset) or Grep for an end-of-file marker over shell `cat`/`wc`, since this project's history includes cases of shell tools reporting stale content on large files.
- When asked to add or update a product, check both the root file list and `Session_Transfer` for the current count/state of tracked products before starting — the "Phase" the project is in (see SKILL.md workflow section) affects whether all product files must be re-output together or a summarized diff is acceptable first.
