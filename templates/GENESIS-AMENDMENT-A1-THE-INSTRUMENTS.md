# GENESIS AMENDMENT PACKAGE A-1 — "THE INSTRUMENTS"
*(Drafted 2026-08-12. Target: v0.3 → v0.4-rc. Tribunal verdict on drafting
timing: RED — Commander override, honored and logged per §1. The R3 Polaris
audit remains scheduled mid-camp and adjudicates this package against field
evidence from the first deployment. Canonical home:
`acp-doctrine/templates/` beside PROJECT-GENESIS.md. Nothing below is
ratified until the Commander seals it. Upon seal, apply the 2026-08-11
lesson atomically: amend → sync mirror → ledger → commit → push.)*

---

## A-0 — PROVENANCE & OVERRIDE LOG

- **Source chain:** 2026-08-12 — full read of the Designlab camp deck →
  personal capability audit (excel / good / lacking / nothing) → harvest of
  the professional-practice map against Genesis v0.3 → tribunal run.
- **Tribunal verdict:** RED on vehicle and timing (nine amendments proposed
  against an undeployed constitution; harness clauses drafted before any
  harness exists; the scheduled R3 audit is the constitutional vehicle).
  Content largely upheld with corrections. Corrections are incorporated
  below.
- **Commander override:** draft and adopt now rather than park as R3-INPUT.
  Logged here as the record. R3 will adjudicate this package with field
  data instead of replacing it.
- **First field deployment:** the Designlab camp homework app (name and
  intent to be produced by Phase R — "an app for something" is exactly
  what Phase R exists to destroy).
- **Activation law** *(resolves the tribunal's sequence-inversion finding)*:
  clauses marked ⚙ are **instrument-dependent** — live as written, but
  no-op in any repo that has no test suite or eval harness. The Activation
  Lap (§A-6) is the switch. A ⚙ clause never blocks work in an
  uninstrumented repo; it starts counting the moment the instrument exists.

---

## A-1 — §3 PHASE C, FULL REPLACEMENT TEXT (v2)

> Replaces the entire "PHASE C — CLOSE & AUDIT" block of Genesis. Diff
> summary: evidence tiers on findings; ⚙ behavior alignment at close;
> ⚙ instrument panel in the BATON; signal-check hook; widened incident
> trigger; AAR gains the Doctrine Delta (the retro §4 references, finally
> housed). Pass 1 unchanged.

**PHASE C — CLOSE & AUDIT**

Triggers (any of): a Polaris milestone ships, the Commander declares a
boundary, or a session retires mid-arc. Not calendar-driven.

- **Findings-only quality review** (read-only; fixes are backlog; zero
  fixes applied in-review). Every finding carries a severity
  (CRITICAL / MINOR / PASS) **and an evidence tier**:
  - **T1 — machine evidence:** failing test, failed eval, analytics
    signal, reproducible error.
  - **T2 — direct inspection:** Tower read the raw pull and can cite
    lines.
  - **T3 — inference:** pattern-match, smell, untested hypothesis.
  A finding is never graded above what its tier warrants. *(Imported from
  the estate-audit evidence law — founded on a ledgered failure of exactly
  this kind. One law, two homes; this clause is the reconciliation, not a
  second law.)*

- ⚙ **Integrity Audit Pass 2 — behavior alignment.** At any close where
  code changed since the previous close: run the repo's test suite (and
  the smoke eval, where the Eval Law applies) against the closing state,
  and record the result in the LEDGER. A **red close is legal but must be
  declared** — `closed red: [what fails]` — never silent. Doc-only and
  ruling-only closes are exempt (mirrors the Phase W doc-only exemption).
  Pass 1 audits whether the *story* is true; Pass 2 audits whether the
  *product still behaves*.

- ⚙ **The BATON carries the instrument panel.** The closing `>> BATON`
  block ends with one line:
  `HARNESS: [n] tests [green|red] · last full eval [date|n/a] · signals [checked|n/a]`
  Session open = read the newest BATON **including the panel** + pull live
  git state before issuing any ruling. The handover now transfers health,
  not just history.

- **Signal check** *(deployed projects under the analytics law)*: the
  close review reads the signals since the last close and answers one
  question — is user behavior tracking the Polaris? Findings to LEDGER,
  caged in backlog like all findings. *(Reconciliation: the Loi des
  signaux lives in the workspace constitution; this is its Phase C hook,
  not a duplicate.)*

- **Incident law, widened:** any production surprise → incident entry
  ≤20 lines within 48h: timeline, root cause, contributing factors, ONE
  change. ⚙ **A red harness discovered on main is an incident** — with or
  without a user report. Silent failure counts; that is the entire lesson
  of the truncation night.

- **Mission close → AAR:** strategy, achieved, sustain, improve —
  ledgered. Every AAR ends with the **Doctrine Delta: at most ONE
  proposed change** to any governing file (add, amend, or kill a rule),
  or the explicit line `no change`. Adjudicated by the Commander at the
  close. *(This is the retro that §4's rituals clause references — it now
  exists: calendar-free, evidence-fed, capped at one so ranking is forced
  and amendment sprawl is structurally impossible. The cap binds this
  package's own descendants.)*

- Session close → no separate handoff document; the BATON block is the
  handoff (see panel clause above).

- **Integrity Audit Pass 1** (git-state truth alignment: local working
  tree vs. `git log` vs. `origin`) runs at every session close.
  Unchanged.

---

## A-2 — §3 PHASE W ADDITION: THE FLAG LAW *(dormant)*

> Insert into Phase W after the eval law. Class-scoped: EXTERNAL-USER
> projects only. Dormant until the moment a user who isn't ACP can reach
> production; from that moment, active without further ceremony.

- **Deploy ≠ release.** Deploying code to production and releasing
  behavior to users are separate acts. Risky user-facing changes ship
  **dark, behind a feature flag**, then release by decision — staged,
  reversible, evidenced.
- **Kill switch beats redeploy.** Rolling back a flagged feature is a
  toggle, not a git operation at midnight.
- **Operator tools are exempt.** Flags on a single-user tool are ceremony;
  the class declaration in the Polaris decides which regime applies.

*(Delivery-side twin of the Database Laws: written before first contact
with external users, active on it.)*

---

## A-3 — §3 PHASE W ADDITION: DISCOVERY CADENCE *(enters as a §4 trial)*

> Class-scoped: EXTERNAL-USER projects. Enters per the rituals law as a
> **4-week trial** — expiry date set at seal, adjudicated at the first
> AAR after expiry.

- EXTERNAL-USER projects in Phase W carry a standing line: **one real
  user contact per [cadence declared in the Polaris], logged to LEDGER.**
  A contact is a conversation, an observed session, or a hard external
  signal. "Would you use this?" is not a contact; "show me how you do
  this today" is.
- **Phase C refuses to close a milestone** on an EXTERNAL-USER project
  without user-contact evidence since the last close.
- Written into the law, from the source map, with eyes open: *this is the
  one clause with no cheaper substitute.* Every other instrument in this
  package is a harness; this one is oxygen. It has now evaporated from
  two consecutive strategy discussions — the trial exists to make the
  third evaporation impossible.

---

## A-4 — §4 ADDITION: CRITIQUE PROTOCOL *(arms the DESIGN GATE)*

> Insert into §4 Standing Guardrails, adjacent to the DESIGN GATE
> reference.

Any commissioned critique — independent instance, external reviewer, or
the Commander's own structured pass — runs **three strictly separated
movements, never mixed**:

1. **DESCRIBE** — what is actually on the screen / in the artifact. No
   judgment permitted in this movement.
2. **EVALUATE** — against the stated goals of the brief or Polaris. Not
   against taste, not against what the reviewer would have built.
3. **PRESCRIBE** — proposals, ranked, each traceable to a specific
   evaluation finding.

Critique output that skips or blends a movement is returned, not argued
with. *(Kills taste ping-pong; gives commissioned critiques — HOTICO
class — a permanent format; the Commander's taste verdict at the DESIGN
GATE remains sovereign and is now legible.)*

---

## A-5 — PARKING REGISTER

- **DORA instrumentation — permanently parked while solo.** The four
  metrics (deployment frequency, lead time for change, change failure
  rate, time to restore) are **mandatory vocabulary** — interviews,
  engineering-leadership conversations — and forbidden infrastructure: a
  solo operator instrumenting them is a rabbit wearing a metrics costume.
  Named per §4, parked with dignity, stops haunting the backlog.

---

## A-6 — THE ACTIVATION LAP *(the switch for every ⚙ clause)*

One Hands session. One repo: `auditlens`. One variable: a minimal
harness. Sonnet-tier, one evening.

- **3–5 tests** asserting current known-good behavior — candidates: the
  audit route responds; a completed report contains all 4 frameworks; the
  response carries no silent-truncation signature; the model string is
  read from config, not hardcoded *(the March 404, converted into a
  permanent tripwire)*.
- **1 smoke eval input** per the Eval Law: one fixed screenshot with
  known expected properties, scored on every merge.
- **GitHub Action:** the suite runs on every PR; red blocks merge. This
  is the harness — a test that runs when someone remembers protects
  nothing; a test that blocks the merge button protects the Commander at
  01:00 on the worst night of a campaign.
- **LEDGER entry + first BATON instrument panel line** inaugurated.
- Separation law applies: the tests are certified by a session that did
  not author the code under test. Nobody grades their own homework.

Until this lap ships, every ⚙ clause is a written law waiting for its
instrument — by design, not by accident.

---

## A-7 — COSTING NOTE *(per the Eval Law's own rule: cost it before briefing it)*

| Clause | Cost |
|---|---|
| Evidence tiers (A-1) | Zero marginal — changes grading, not workload |
| Pass 2 (A-1, ⚙) | Minutes per code-touching close; zero when exempt |
| BATON panel (A-1, ⚙) | One line per close |
| Incident widening (A-1, ⚙) | ≤20 lines, only when triggered |
| Doctrine Delta (A-1) | Already inside the AAR; the cap *reduces* cost |
| Flag Law (A-2) | Zero until first external user |
| Discovery cadence (A-3) | ~30 min/week when live — the only clause that costs real time, and the only one buying reality |
| Critique protocol (A-4) | Zero — reformats existing critiques |
| Activation Lap (A-6) | One evening, once per repo |

---

## A-8 — SEAL BLOCK

- [ ] Commander read in full
- [ ] Trial expiry date set for A-3: `____-__-__`
- [ ] Ruling number assigned to the override: `R__`
- [ ] Sealed as v0.4-rc → Genesis header bumped, changelog line added
- [ ] Mirror synced, ledgered, committed, pushed — atomically
- [ ] R3 audit scope updated: adjudicate A-1…A-6 against camp field
      evidence

*Chats are disposable. The files are the institution. Ship laws that
last.*
