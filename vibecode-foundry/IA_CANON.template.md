# IA_CANON.md — [Product Name]
*Canon-lite. Instantiate one per product repo, at repo root, next to CLAUDE.md.*

- **Product:** [name] — [one-line identity: what this is, for whom]
- **Canon version:** [semver-lite, e.g. 1.0]
- **Created:** [date] · **Last amended:** [date]

## Section 1 — Controlled Vocabulary

| Concept | Canonical term | Banned synonyms | Notes |
|---------|-----------------|------------------|-------|
| ex. | `finding` | issue, problem, observation | user-facing + code identifiers |

One canonical term per concept — no exceptions in user-facing strings. Bilingual products (EN/FR/RO): one canonical term per language, mapped in the same row. Executors may propose new terms; only ACP rules.

## Section 2 — Content Types

- `[type name]` — [one-line definition] — [canonical / draft / deprecated]

Every piece of content in the product must fit a declared type. Content that fits none is an audit flag.

## Section 3 — Structure Map

- Hierarchy: [parent → child, max 3 levels for canon-lite]
- Top-level navigation items, in order, canonical terms only: [...]
- Dependency notes: [where one thing must exist for another to make sense]

## Optional Annex
*(only when the product earns it)*

- Labeling rules: capitalization, button verb conventions, microcopy tone (cross-ref `acp-writing-style`)
- Status conventions: how canonical/draft/deprecated is marked in-product
- Relationships & permissions map — mandatory before any agentic feature ships (what an agent may touch)

## Changelog
*(mandatory, no exceptions — silent edits are a protocol violation)*

- YYYY-MM-DD — v1.0 — initial canon

---
Size cap: canon-lite fits one page (~60 lines). Past ~150 lines, the product has outgrown lite — split the annex or graduate to full canon.
