# IA Canon — Feature Specification v1.0
*Post-Tribunal spec — 2026-07-31. Supersedes the three-layer v0 pitched earlier in session (Amber verdict: over-built, missing mid-build enforcement).*

---

## 1. What this is

A per-product information architecture foundation. Every active vibecoded product carries a versioned `IA_CANON.md` at repo root that governs its vocabulary, content types, and structure — created at ignition, enforced through the existing supervisor loop, audited at the QA gate.

**Not** a standalone skill (deferred until post-pilot verdict). **Not** enterprise ontology tooling. It is a foundry feature: one template, one foundry section, one two-line law.

## 2. Components (4)

| # | Component | Lives in | Size |
|---|-----------|----------|------|
| A | `IA_CANON.md` template | Each product repo, root, next to CLAUDE.md | ≤ 1 page (canon-lite) |
| B | Foundry amendment | `vibecode-foundry` SKILL.md, new section "IA Canon" | ~40 lines |
| C | The Law | Command-center CLAUDE.md | 2 lines |
| D | Audit checklist | Inside the foundry amendment (used at QA gate + retrofit) | ~10 lines |

---

## 3. Component A — the artifact: `IA_CANON.md` (canon-lite)

### Header block
- Product name + one-line identity ("what this is, for whom" — anchors every naming ruling)
- Canon version (semver-lite: 1.0, 1.1…)
- Date created / date last amended

### Section 1 — Controlled Vocabulary *(the drift killer)*
Table format:

| Concept | Canonical term | Banned synonyms | Notes |
|---------|---------------|-----------------|-------|
| ex. | `finding` | issue, problem, observation | user-facing + code identifiers |

Rules:
- One canonical term per concept. No exceptions in user-facing strings.
- Bilingual products (EN/FR/RO): one canonical term **per language**, mapped in the same row.
- Executors may **propose** new terms; only ACP **rules**.

### Section 2 — Content Types
List format: `type name — one-line definition — status marker (canonical / draft / deprecated)`.
Every piece of content in the product must fit a declared type. Content that fits none = audit flag.

### Section 3 — Structure Map
- Hierarchy: what belongs to what (parent → child, max 3 levels for canon-lite)
- Top-level navigation items, in order, using canonical terms only
- Dependency notes where one thing must exist for another to make sense

### Optional Annex *(only when the product earns it)*
- Labeling rules: capitalization, button verb conventions, microcopy tone (cross-ref `acp-writing-style`)
- Status conventions: how canonical/draft/deprecated is marked in-product
- Relationships & permissions map — **mandatory before any agentic feature ships** (what an agent may touch)

### Changelog *(mandatory, no exceptions)*
One dated line per amendment. Silent edits are a protocol violation.
`2026-08-02 — v1.1 — added "severity" to vocab (supervisor ruling, sprint review #3)`

### Size cap
Canon-lite fits one page (~60 lines). Past ~150 lines → signal that the product has outgrown lite: split annex or graduate to full canon. The cap exists so the canon gets written, not skipped.

---

## 4. Component B — lifecycle & enforcement (foundry amendment)

Five moments, mapped onto the existing foundry/control-tower loop — **no new ceremony**:

1. **Ignition — Discovery.** Before the first executor brief: ≤10-min interrogation (list the product's concepts → force one canonical term each → type the content → sketch the nav). Output: canon v1.0, committed to repo. *Gate: no ignition-key brief ships without it.*
2. **Brief injection.** Every executor brief embeds the Controlled Vocabulary table verbatim + pointer to the full canon in-repo.
3. **Supervisor canon check** *(the mid-build enforcement — the hole the Tribunal found)*. Canon compliance becomes one line item in the existing supervisor review grade. Executor output introduces an unnamed concept → supervisor surfaces it → ACP rules → dated amendment → next brief carries it. The canon stays *living* between ignition and launch.
4. **QA gate — audit run.** Pre-launch, run the checklist (Component D). **Blocking:** banned-synonym violations in user-facing strings. **Flag-only:** annex-level issues.
5. **Amendment protocol.** Executors propose, ACP decides, changelog dates it. Applies at every moment above.

## 5. Component C — the Law (command-center CLAUDE.md)

> No build session on a product without its `IA_CANON.md` at repo root — if absent, run IA discovery before any brief.
> Every executor brief carries the canon's controlled vocabulary; supervisor reviews grade output against the canon, and new concepts get a dated ruling before the next brief.

## 6. Component D — audit checklist (drift signals)

Literal counts + locations, `ai-tic-audit` style. Flags only — never auto-rewrites; rulings are ACP's.

1. **Synonym drift** — same concept under ≥2 labels across screens/copy
2. **Vocab violation** — banned synonym in a user-facing string *(blocking at QA gate)*
3. **Untyped content** — content fitting no declared type
4. **Orphans** — pages/sections unreachable from the structure map
5. **Nav divergence** — shipped navigation ≠ canon structure map
6. **Label inconsistency** — casing/verb convention breaks *(annex products only)*

## 7. Rollout

- **Step 1 (1 session):** write template + foundry amendment + the Law. Commit to command center.
- **Step 2 — pilot:** retrofit on **AuditLens 2.0**. Audit-first: extract the implicit vocabulary from the live product, surface every conflict, ACP adjudicates each, commit canon v1.0.
- **Step 3:** run the full loop through the AuditLens 2.0 sprint. **Verdict after sprint:** fewer label-drift corrections vs. previous sprints → keep as foundry section, or promote to standalone skill if the section bursts.

## 8. Explicit non-goals (v1)

- Standalone `ia-canon` SKILL.md (deferred to post-pilot verdict)
- Workspace IA — skills folder, memory files, dashboard naming
- Automated drift-detection tooling; automated vocabulary rulings
- Retrofitting portfolio / dashboard / HOTICO before the pilot verdict
- Any quantified effectiveness claim without measurement (no invented percentages)

---
*Origin: Patrick Neeman, "Information architecture is the foundation AI is starving for" (Medium, July 2026) → tribunal run 2026-07-31 (Amber) → this spec.*
