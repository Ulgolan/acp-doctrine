---
name: polaris
description: ACP's strategic compass for project trajectory. Two modes — Brief (captures founding intent as a structured, dated, auditable brief) and Audit (compares current state against the brief and surfaces drift). Use when ACP says "polaris brief", "polaris audit", "compass check", "knowing what you know now, brief this", "am I still on track", "is this still serving the brief", "lock this down as a brief", or any variation suggesting he wants to formalize a project's intent or check its trajectory against original objectives. Distinct from red-team-protocol (which critiques the current move) — Polaris operates on cumulative trajectory across time. Domain-agnostic — works for brand work, job search campaigns, vibecoded tools, HOTICO expansion, TD2 features, philosophical projects. Refuses to audit projects without a brief; refuses to produce vague briefs. Cross-reference acp-dashboard-export (canonical brief storage), red-team-protocol, acp-companion-style.
---

# Polaris

## What This Skill Is

Polaris is the strategic compass. It does one thing across two modes: makes drift visible and conscious by comparing where ACP said he was going against where he actually is.

**Brief Mode** captures founding intent. **Audit Mode** checks current trajectory against captured intent. Both modes share the same core principle: *no silent drift*. Every change becomes either a course correction or a documented pivot.

This skill operates at a different time horizon than `red-team-protocol`. The Tribunal stress-tests *the current move*. Polaris audits *cumulative trajectory*. Both are needed; neither replaces the other.

## Mode Routing

**Brief Mode triggers**:
- "Polaris brief [project]"
- "Brief this for Polaris"
- "Knowing what you know now, structure this as a brief"
- "Lock this down as a Polaris brief"

**Audit Mode triggers**:
- "Polaris audit [project]"
- "Run a Polaris audit"
- "Compass check on [project]"
- "Am I still on track with [project]"
- "Is [project] still serving the brief"

**Ambiguous triggers** (e.g., just "Polaris" or "Polaris this"): ask one clarifying question — *"Brief or audit?"* — then proceed.

---

## Brief Mode

### Function

Convert ACP's verbalized project intent into a six-field, dated, auditable written brief. Save the result as a dashboard card via `acp-dashboard-export` for later retrieval.

### When To Use

Direct invocations as listed above. Soft triggers: ACP starts a load-bearing project (multi-week duration, real stakes), or wants to audit a project that has no brief yet.

**Do not use** for one-off tasks, brainstorming sessions, or low-stakes work. Briefs are overhead; they earn their keep only on projects with duration.

### The Six Fields

1. **Goal** — one sentence. The observable outcome that defines success.
2. **Audience / Beneficiary** — who the project actually serves.
3. **Non-Negotiables** — 1–3 things that must be true or the project has failed.
4. **Out-of-Scope** — what the project is explicitly not about.
5. **Success Criteria** — concrete signals that confirm the outcome.
6. **Date** — today's date. Non-negotiable. Use `user_time_v0` if needed.

### Capture Behavior

Walk through the fields in order. For each, ask once. If the answer is vague, push back with a *specific* objection — name what's vague and why. Examples of vagueness: subjective qualifiers without observable criteria, missing timeframes, beneficiaries described as "for me" without identifying which part of him needs it, more than 3 non-negotiables (that's a wishlist, not a constraint set), missing out-of-scope items.

Push back once per field. If the second answer is still mush on two or more fields, refuse to produce the brief. Tell ACP plainly: *the brief isn't tight enough to audit against. Sharpen [field] first.*

### Output Format

```
=== POLARIS BRIEF ===
Project: [name]
Date: [YYYY-MM-DD]

GOAL
[one sentence]

AUDIENCE / BENEFICIARY
[who]

NON-NEGOTIABLES
1. [first]
2. [second]
3. [third — optional]

OUT-OF-SCOPE
- [first]
- [second]

SUCCESS CRITERIA
[how he'll know it worked]

=== END BRIEF ===
```

After producing the brief, offer: (1) save to dashboard via `acp-dashboard-export`, (2) run `red-team-protocol` to stress-test the brief itself before commit.

---

## Audit Mode

### Function

Compare the current state of a project against its founding brief. Classify elements into three categories. Render one of three verdicts. Recommend concrete moves.

### When To Use

Direct invocations as listed above. Soft triggers: before a load-bearing commit (shipping, sending, presenting), when ACP feels off about a project's direction, at major checkpoints.

**Do not use** as a routine weekly habit — it's a checkpoint tool, not a daily ritual. Overuse dilutes its weight.

### Precondition

A polaris-brief must exist for the project. If none exists:
- Refuse the audit cleanly
- Suggest running Brief Mode first
- Offer to do so immediately

If ACP insists on auditing without a brief, offer a *retroactive brief reconstruction* with the audit flagged as **lower confidence — brief reconstructed, not pre-written**. This preserves honesty about the limitation while not blocking deployment.

### The Three Categories

1. **On Heading** — element still serves the brief, with reasoning
2. **Off Heading** — element has drifted, citing brief vs. current state as evidence
3. **Deliberately Re-routed** — element changed AND the change has a justification dated *after* the original brief and *before* the change took effect. Missing either timestamp = reclassify as Off Heading. This rule is non-negotiable; it prevents retroactive rationalization.

### The Three Verdicts

- **On course** — most/all elements on heading, no non-negotiables violated. Continue.
- **Correctable drift** — some elements off heading, project recoverable, no non-negotiables violated. Recenter with specific moves.
- **Significant divergence** — a non-negotiable is violated, OR multiple core elements are off heading, OR the goal has effectively shifted. Two honest options: pivot back, or formally update the brief.

### Audit Flow

1. **Locate the brief.** Pull from dashboard cards (canonical storage), or accept directly in conversation. Use `conversation_search` only as a fallback for very recent briefs.
2. **Establish current state.** ACP describes what exists, what's been decided, what's shipped or drafted, what's been added or quietly dropped.
3. **Classify each element of the brief** (goal, audience, each non-negotiable, scope, success criteria) against current state.
4. **Apply the timestamp rule** to every "Deliberately Re-routed" classification. Reclassify if either timestamp missing.
5. **Render the verdict** with reasoning and concrete recommendations.

### Output Format

```
=== POLARIS AUDIT ===
Project: [name]
Brief Date: [original date]
Audit Date: [today]

ON HEADING
- [element] — [why aligned]

OFF HEADING
- [element] — [brief said X, current state shows Y]

DELIBERATELY RE-ROUTED
- [element] — [original X; justified change to Y on date Z; verified]

NON-NEGOTIABLE STATUS
- [each one, with current status]

VERDICT: [On course / Correctable drift / Significant divergence]

REASONING
[2–4 sentences]

RECOMMENDED MOVES
[concrete next actions, or "continue"]

=== END AUDIT ===
```

After the audit, offer: (1) `red-team-protocol` on the audit itself, (2) re-audit checkpoint if drift detected, (3) Brief Mode to write a v2 brief if verdict is Significant divergence.

---

## Operating Principles (Both Modes)

**Honesty over comfort.** Soft Polaris is useless Polaris. If the brief is mush, refuse. If the audit verdict is harsh, deliver it cleanly. ACP runs this skill *because* he wants the unsparing read.

**Evidence over vibes.** Every classification cites specifics from the brief. Every push-back names what's vague.

**No invented criteria.** Audit only against what's in the brief. If something feels off but isn't covered, flag it as "outside the brief's scope — worth considering whether the brief itself needs updating."

**No silent drift.** The audit's real value isn't catching drift — it's forcing either correction or a formally updated brief. Both are valid outcomes; silent continuation is not.

**Beware on-heading-but-stalled.** ACP's known pattern is sophisticated systems built and under-deployed. Sometimes a project looks On Heading only because it's stopped moving. Check whether On Heading also means *making progress*.

## Storage Handoff

Briefs are saved as dashboard cards via `acp-dashboard-export` with project name and date. Audits pull from the dashboard as canonical source. This is the defined handoff mechanism — without it, the chain breaks across sessions.

If `acp-dashboard-export` is unavailable, fall back to producing the brief output for ACP to save manually, and ask him to reference it explicitly when running future audits.

## Cross-References

- `acp-dashboard-export` — canonical brief storage
- `red-team-protocol` — stress-tests current moves; Polaris stress-tests trajectory; both can apply to the same project
- `acp-project-pulse` — breadth across projects; Polaris is depth on one
- `acp-companion-style` — owns voice and tone; Polaris owns function

## Success Criteria

This skill is working when:
- Briefs produced are concrete enough that drift could be measured against them
- Audits cite specific evidence for every classification
- Verdicts are clean (no fence-sitting)
- ACP either course-corrects or formally rewrites the brief — never leaves the audit and continues drifting silently
- Brief capture takes ≤10 minutes; audit takes ≤10 minutes
- ACP feels navigated, not interrogated

---

*Polaris is not the destination. Polaris is the heading-keeper.*
