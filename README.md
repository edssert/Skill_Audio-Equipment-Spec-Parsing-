# Audio Equipment Spec Parsing Skill

This is not a software project — there is no code to build, lint, or test. It is a **Claude Code skill-creator project**: a working directory used to iteratively develop and exercise a skill (the current highest-numbered `SKILL_v*.md` at repo root) that parses audio equipment (amplifiers/controllers and speakers) spec data from heterogeneous source documents — owner's manuals, spec sheet PDFs, A&E (Architectural & Engineering) docx specifications, and website tiers — into unified master-schema markdown files, one per product.

## What's here

- **`SKILL_v{X.Y}.md`** (root) — the current ruleset: how to discover a product's spec schema from its source documents, normalize manufacturer-specific terminology into a consistent set of keys, and write it out as a master schema file. Always read the highest-numbered version at root first; it takes precedence over everything else in this README.
- **`SKILL_Changelog.md`** (root) — append-only version history of the skill document itself.
- **`CLAUDE.md`** (root) — orientation for Claude Code sessions working in this repo; each category folder (e.g. `speakers/CLAUDE.md`) has its own supplementary conventions.
- **`Session_Transfer_v{X.Y}.md`** (root) — a running snapshot of project status and next steps, refreshed periodically. Can lag behind the actual repo state; when the two disagree, trust the files.
- **`TODO.md`** / **`TODO_Archive.md`** (root) — in-progress and completed work log.

## Repository layout

Product data is organized by **category** (product type) then **brand**: `{category}/{brand}/...`.

- `amplifiers/` — amplified controllers, brands `LA` (L-Acoustics) and `db` (d&b audiotechnik).
- `speakers/` — line array elements, point sources, subwoofers, and colinear sources, brands `LA` (L-Acoustics), `db` (d&b audiotechnik), and `MY` (Meyer Sound).

Within each brand folder:

- `{Product}_v{X.Y}.md` — the current master schema file for that product, at the brand folder's root.
- `Original_PDFs/{Product}/` — untouched original source documents (owner's manual, spec sheet, A&E docx). Never edited.
- `Raw_Web_Data/{Product}_Raw_Web_Data.md` — verbatim copy-pasted website spec tiers, where available.
- `Archive/{Product}/` — every superseded version of that product's master schema file.

Root-level `Archive/` holds every superseded `SKILL_v*.md` and `Session_Transfer_v*.md`.

## Coverage snapshot

| Category | Brand | Products |
|---|---|---|
| amplifiers | L-Acoustics | 6 (LA1.16i, LA2Xi, LA4X, LA7.16, LA7.16i, LA12X) |
| amplifiers | d&b audiotechnik | 10 (5D, 5DM, 10D, 25D, 30D, 40D, D25, D40, D80, D90) |
| speakers | L-Acoustics | 41 products across K/A/X/S/L Series, plus subwoofers |
| speakers | d&b audiotechnik | 2 (GSL8, GSL12) |
| speakers | Meyer Sound | 3 (PANTHER-L, PANTHER-M, PANTHER-W) |

This snapshot moves fast — treat it as a rough orientation, not a source of truth. Check the actual folders, or `TODO.md`/`Session_Transfer_v*.md`, for current state.

## Core rules (see `SKILL_v*.md` for the full ruleset)

- **Never fabricate values.** Every value is grounded in the product's own source documents. A value that can't be confirmed is left `null` with a footnote explaining why — never filled in by guessing, by borrowing from a sibling product without justification, or (explicitly banned) by citing time constraints as the reason it wasn't looked up.
- **Bidirectional schema sync.** Every master schema file for products managed together carries an identical key list. A new key discovered in one product's source gets added to every sibling file (as `null` if not applicable to that product), and vice versa.
- **Surgical Versioning Protocol.** Producing a new version of any tracked file follows a strict order: duplicate the file under the new version name with zero edits, move the original into its `Archive/` folder, and only then make edits to the new file.
- **Architecture is never assumed from naming.** A product's electrical/mechanical architecture (active vs. passive, crossover type, connector pinout) is determined by reading that product's own source documents directly — never inferred from its name, its marketing copy, or a sibling product's architecture.
