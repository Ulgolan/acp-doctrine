# ESTATE AUDIT — HOTICO PROTOTYPE CAMPAIGN (FULL TRIBUNAL)

Scope: the full HOTICO prototype campaign — operational process, repo state, doctrine compliance, external-audit cross-examination
Standard: control-tower + vibecode-foundry doctrine (in force campaign-long) + PROJECT-GENESIS Part C (§3 Phase C, in force from ~2026-08-09 per LEDGER #40's own citation)
As of: 2026-08-11 · `Ulgolan/hotico-proto` main @ `a0e18cd` · `Ulgolan/acp-doctrine` main @ `6769278`
Budget: **FULL TRIBUNAL** (Commander-ruled)
Out of this audit's scope: design taste (Commander's gate), Alexa-side business outcomes beyond reported signal, production implementation, the Tower-chat contents themselves (unreachable — see G1 degradation)

---

## G1 — GROUND-TRUTH PULLS

| # | Source | Anchor | Status |
|---|--------|--------|--------|
| 1 | `hotico-proto` full clone | `a0e18cd`, 2026-08-11 | OK — T1. Identical to ChatGPT's audited SHA: same universe |
| 2 | `LEDGER.md` (48 entries, 210 KB, BATON block) | `a0e18cd` | OK — T2 |
| 3 | `CLAUDE.md`, `POLARIS.md` (root + docs/), `README.md`, `STATE-MAP.md` | `a0e18cd` | OK — T1/T2 |
| 4 | Git history: 188 commits, 33 PRs, 37 merges, span 2026-08-02 → 2026-08-10, zero tags | `a0e18cd` | OK — T1 |
| 5 | `acp-doctrine` full clone; canonical Genesis template | `6769278` / template last moved `fa2a111` (2026-08-06) | OK — T1. `audits/KPI.md` confirmed **absent** |
| 6 | Live proto fetch (`hotico-proto.vercel.app`) | 2026-08-11 | OK with declared caveat — fetcher caches aggressively; content spot-check consistent with head (R-4 FR texts, R-5 pill assets `?v=1`/areole `?v=2`, 6× Marina, `tel:+40`) but "deployment ≡ head" is inference, not certification |
| 7 | This Project's chat archive (conversation_search + recent_chats) | 2026-08-11 | **DEGRADED — EMPTY.** The 8 TOWER chats live in the Tower Project; per-project scoping makes them structurally unreachable. All chat-side claims capped at what the LEDGER recorded |
| 8 | Commander testimony: 11 days · 8 Tower chats · 21 Hands chats · ~80% Sonnet-high / ~20% Opus-mid · Alexa saw it, approved, requested changes now live | 2026-08-11, this session | Received — Commander-supplied. Client *changes-executed* corroborated at T2 by LEDGER #46 ("Alexandra's redesign, sealed"); sentiment and cost figures are testimony, unledgered |
| 9 | ChatGPT external audit (17 sections) | supplied 2026-08-11, targets `a0e18cd` | Input under cross-examination — treated as claims, not evidence |

---

## G2 — FINDINGS

### Positive findings (praise graded under the Evidence Law)

**P1 — The memory law held under live fire.** T1 | as of `a0e18cd`.
A fresh Tower instance, in an empty Project, with zero chat inheritance, reconstructed the entire 9-day campaign — laps, bounces, errors, rulings, open items — from the repo alone. Trinity present (CLAUDE.md / LEDGER.md / POLARIS.md), 48 entries, BATON block, integrity passes recorded. "The files are the institution" is no longer doctrine-on-paper; this audit is its existence proof.

**P2 — The self-correction machinery ran both directions.** T2 | LEDGER #29–#48.
Nine numbered Tower errors self-ledgered (#1–#9), each with root cause ("every fired error traced to an unverified assumption, every catch to a pull of ground truth"). Hands catches ledgered with equal weight: anchor-table STOP, staged-aréole hash stop at gate zero, dial-B refusal-to-improvise, self-caught scope violation. Harness defects ledgered as first-class findings (the false-passing matrix set, the non-blinking compositor). No blame asymmetry anywhere in the record.

**P3 — The client loop closed inside the campaign, with chain of custody.** T2 | #46, corroborating Commander testimony.
Alexandra annotated a redesign; it shipped as R-4 with SHA-256-verified copy from her master xlsx, programmatically generated keys, byte-exact round-trip, zero unilateral fixes, and a side-list of her own inconsistencies traveling back to her rather than being silently "fixed." This is the strongest client-facing process artifact in the estate.

**P4 — Independent certification caught what two Tribunals and the author missed.** T2 | #46.
The `doClose()` stale-height defect passed both Hands Tribunal chairs and the key's author; the Tower caught it at tarball certification — and then ledgered the error on *its own* side of the board because its key under-specified the release. The certification tier is earning its cost.

**P5 — The pre-mortem converted bounces into pre-fire catches.** T2 | #39 vs #46.
The hero chapter ate 2 architecture bounces + 3 in-lap bounces; by R-4, two Tribunals on the Tower's own brief killed both traps before the Hands fired — "zero bounces; the pre-mortem did the bouncing." Measurable discipline maturation inside one campaign.

### Findings — issues

**F1 — Certified behavior lives in prose; the spec artifacts were never emitted.** T1/T2 | **HIGH** (per scale: will produce a wasted lap — a production developer inventing design decisions — if left on current trajectory) | as of `a0e18cd`.
The 240-cell gesture matrix — the campaign's single most valuable verification asset — exists as one LEDGER sentence plus a pass count; nothing can be re-run or diffed (C3). `docs/STATE-MAP.md` last moved 2026-08-02, pre-dating the entire kintsugi hero (C2). `PRODUCTION-HANDOFF.md` does not exist. POLARIS success criterion 3 ("spec-grade… a future Hands builds without inventing a design decision") is unmet at seal-time.
*Hindsight check:* PASS — knowable at the time; criterion 3 was sealed 2026-08-04 and the campaign's own AAR (#40) named this "the largest hole the chapter leaves." **Confirmation of record, still open — competes for the slate by right.**

**F2 — Constitution drift: the law lags its own rulings, in four places.** T1 | **MEDIUM** (compounding drift; a literal reader lands on wrong law) | as of `a0e18cd` / `6769278`.
(a) `CLAUDE.md` still declares `body{max-width:480px}` as standing law while `main.css:1602` lawfully removes it above 768px under the ratified desktop POLARIS — the constitution was never amended (new facet). (b) `docs/POLARIS.md` is still the superseded 2026-08-01 brief the constitution literally points at (C1 — confirmation, unresolved). (c) `docs/STATE-MAP.md` two+ eras stale (C2 — confirmation). (d) The canonical Genesis template in acp-doctrine carries header "v0.2" against §0's "VERSION AT BIRTH: v0.3" — the v0.3 amendment (`4442594`, 2026-08-06) updated the body and never bumped the header. Same disease the AAR convicted three times in code: *the law outlives its jurisdiction* — now proven in the documents too.

**F3 — Cost is structurally invisible.** T1 (empty archive) + T4 (recall) | **MEDIUM** (rising cost: every future post-mortem and KPI row depends on Commander memory) | as of 2026-08-11.
Session counts, model mix, and hours exist nowhere in the primary record — the 11-day / 8-Tower / 21-Hands / 80-20 figures in G4 are testimony. The doctrine ledgers *what happened* superbly and *what it cost* not at all. Per the absence-of-evidence rule this audit also cannot rule on anything that happened in chats and was never ledgered — that blindness is permanent and by design; the fix is a cost line at session close, not chat preservation.

**F4 — The campaign is unsealed: no tag, no campaign-close AAR.** T1 | **MEDIUM** (drift risk: an unsealed frozen artifact invites "one more lap") | as of `a0e18cd`.
`git tag` is empty; Entry #48 explicitly defers the AAR "to campaign close." The record's own final move — tidy → document → tag → stop — has not fired. This audit supplies the AAR content; the seal remains undone.

**F5 — This Project's Genesis §0 is unfilled.** T1 (visible in project instructions) | **MINOR** | as of 2026-08-11.
Blanks throughout §0, no birth SHA. The provenance law Genesis §0 installs is unexercised by the very project running it. Hygiene; ledger and move on.

### Confirmations of record (verified live at `a0e18cd`, already ledgered)

- `form.js?v=3` vs `?v=2b` stale pointer (#47/#48 tidy queue) — confirmed T1
- Dead selector families `.pill__arrow` / `.pill.is-open*` / `.panel*` / `.ba-*` (#48) — confirmed T1: zero HTML usage
- Orphan assets incl. `temp-1x/lips-*.png`, `services/strip-01..06.png` (#40 M7, #48) — confirmed present
- Pill WebP 1.55× density at the 480px band (#48, Hands-corroborated) — on record
- `tel:+40` vs `wa.me/+41` — M9, **CLIENT QUESTION, never edit unilaterally** — confirmed on all three pages
- 6× Marina testimonial — ledgered as designed demo filler since Entry #1 (DOSSIER D15)
- CSS/JS hero constant coupling (M4 + BATON TRAP 6) — confirmed T1 (`TOTAL_VH` 478 in JS; 478/378vh hand-restated in CSS)
- C4 script-failure fallback gap, C5 colour-law rgba breaches, M1/M2 unexercised invariants — all carried in BATON OPEN, unresolved at head

---

## ANNEX — CROSS-EXAMINATION OF THE EXTERNAL (ChatGPT) AUDIT

Method per the external auditor's own instruction: every finding compared against the tree at `a0e18cd`; no automatic execution.

| § | Finding | Ruling | Evidence |
|---|---------|--------|----------|
| 1 | Hero freeze; reuse-candidate classification | **AGREE** | T1: 81,076 bytes / 1,499 lines confirmed; freeze matches BATON traps + Phase C doctrine |
| 2 | Doc authority contradiction; PRODUCTION-HANDOFF as new authority; CLAUDE.md 480px drift | **AGREE — half ALREADY ON RECORD** | C1/C2 ledgered #40; the CLAUDE.md 480px facet is new and T1-verified (`tokens.css:46` + `main.css:1602`); PRODUCTION-HANDOFF.md confirmed absent |
| 3 | Form PROTOTYPE ONLY | **AGREE — ALREADY ON RECORD** | Demo-grade since Entry #5; `outline:none` confirmed `main.css:1170` |
| 4 | "Fake success / account goblin" | **PARTIAL DISAGREE** | "Créer un compte" → wa.me is **Commander-ratified** (LEDGER correction #10, "wa.me href kept exactly") — a ruling, not a goblin. Fake success is known demo-grade. The prototype-disclosure line is a legitimate *new suggestion*, but it is a Commander/client-comms call, never a silent fix |
| 5 | Découvrez resize edge case (`closedPx` cached at init) | **AGREE — NEW, VERIFIED** | T1: `main.js:226` captures once, `:243` animates to it post-resize; release then snaps to CSS truth. MINOR, animation-cosmetic, final state correct. Recommendation (record as production debt, don't touch) aligns with freeze doctrine. The external audit's best contribution |
| 6 | Carousel inactive slides not inert/aria-hidden | **AGREE — NEW (production-side)** | T1: zero `inert`/`aria-hidden` handling in `main.js` |
| 7 | Tabs click-only; keyboard/roving-tabindex missing | **AGREE — NEW (production-side)** | T1: ARIA tab roles present in `areola.html:75-80`, no keydown machinery |
| 8 | Dead code / orphans | **ALREADY ON RECORD** | Identical to the R-5/#48 tidy queue, item for item |
| 9 | Stale comments (`DUR = 340 // .panel / .walk`) | **AGREE with nuance — NEW** | T1 `main.js:18`: `.panel` reference stale (retired R-5), `.walk` still live — half-stale, correct the half |
| 10 | Cache pointer sync | **ALREADY ON RECORD** | #47/#48; confirmed T1 |
| 11 | Pill density 1.55× | **ALREADY ON RECORD** | #48, independently corroborated by Hands in-session |
| 12 | Content debt (Marina, RO strings, `5 din 5`, +40 tel) + content-status table | **MOSTLY ON RECORD; table proposal NEW and adopted** | Marina = DOSSIER D15 by design; M9 client question; `5 din 5` ×4 confirmed T1 in `areola.html`. The FINAL/APPROVED/PLACEHOLDER status table is a genuinely good addition to the handoff doc |
| 13 | Focus visibility | **AGREE — NEW minor** | T1 confirmed; form is PROTOTYPE ONLY so scope small |
| 14 | CSS/JS constant coupling — document, don't refactor | **ALREADY ON RECORD** | M4 + BATON TRAP 6, verbatim same ruling |
| 15 | Reuse map | **AGREE** | Sound synthesis; consistent with FATE CLAUSE + the nuanced reuse policy F1's handoff doc will formalize |
| 16 | Tidy lap list | **AGREE with one edit** | Item 5 (fix Créer un compte) requires a Commander *re-ruling*, not a fix — it is ratified canon. Everything else matches or extends the ledgered queue |
| 17 | Seal tag + SHA in handoff | **AGREE — NEEDED** | T1: zero tags exist |

**Scorecard:** 17 sections · 0 factually wrong · 1 partial disagreement (mistook a ratified ruling for an accident) · ~7 rediscoveries of already-ledgered items presented as findings · ~5 genuinely new minors (best: §5) · 2 structural adoptions (handoff authority doc, content-status table).
**The lesson is not about ChatGPT — it is about us:** an external auditor with repo access rediscovered ~40% of the record because the record's index (LEDGER) wasn't handed to it as the entry point, and because certified knowledge lives in prose (F1). External audits should be briefed with the LEDGER and BATON first; what they then still find is the true delta.

---

## G3 — COUNTER-PASS (FULL TRIBUNAL: Architect · Sniper · User Advocate)

**Architect** — Does the instrument fit the goal (methodology architecture)? Risk named: blending the audit spine with the lessons synthesis would let enthusiasm grade the evidence. Held separate: audit rules on what happened; the methodology section derives from ruled findings only. Second risk: this audit sits at the edge of its own scope law (client deliverable adjacency). Resolved at G0 by Commander override, logged; the repo *qua* estate object is in scope, the design *qua* product is not, and no design ruling appears above.

**Sniper** — weakest claims, attacked:
- *"Alexa loved it"* — sentiment is Commander testimony. Downgraded in G4: changes-executed = T2 (#46); approval sentiment = Commander-reported, so annotated. Survives at its correct tier.
- *Cost figures* — pure recall (T4). Not laundered into findings; reported as testimony, and F3 exists precisely because the record cannot do better.
- *Live proto ≡ head* — cache-degraded inference, declared in G1; no finding rests on it.
- *F1's HIGH* — hindsight-checked and it holds: the standard (criterion 3) predates the failure, and the campaign's own AAR named it. Not hindsight; a known, standing, unpaid debt.
- *Selection bias* — the LEDGER is the audited system's own account; omissions are invisible (absence-of-evidence rule). Mitigations: T1 tree verification of every claim used, plus a fully external auditor as cross-check. Residual blindness acknowledged in F3 and not papered over.
- *Flattery gradient* — P1–P5 each carry a T1/T2 anchor; no praise rests on digest or vibe.

**User Advocate** — what does ACP actually need? A slate he can fire, not ten observations; and the methodology synthesis un-buried. Rabbit check on the slate: action 1 is shipping (seal the deliverable), action 2 is the deliverable's missing half (spec/handoff — also shipping), action 3 is the only doctrine item and it is triggered, capped, and rides doc-only keys. The slate is not meta-work wearing a hard hat. One nudge the Advocate insists on: the Commander owes *himself* the ruling queue (M9 tel, M10 Finding B, compte disclosure) — items only his clipboard can close.

**Downgrades made at this gate:** none required — the Evidence Law was applied at G2, where it belongs. One finding was *withheld* here: a suspected "lap-per-session drift" pattern (21 Hands chats vs 33 PRs) could not be verified above T4 and would grade MINOR at best; per the law it does not ship.

---

## G4 — OUTCOMES & COST

**Outcomes (moved):**
- **Shipped state:** 33/33 PRs merged; 188 commits; live deployment serving head-consistent content; hero v25 frozen SHA-verified campaign-long; zero open branches/stashes at last integrity pass.
- **Client signal:** the strongest kind — Alexandra reviewed the artifact, requested changes, and the changes shipped as certified laps (R-4 sealed from her annotated document, T2). Commander reports approval; recorded as testimony. The POLARIS trust-test bonus ("Alexa at full width saying that's it") is functionally met per testimony — UNMEASURED at T1.
- **Career pipeline:** out of scope for this campaign — UNMEASURED.

**Cost (spent):**
- Commander-supplied, unledgered (F3): **11 days · 8 Tower chats · 21 Hands chats · ~80% Sonnet-high / ~20% Opus-mid** (Opus concentrated on animation III's finish). Hours: UNMEASURED.
- **Discipline vs. error economics, from the record:** the discipline tier (2 read-only Phase C sessions, ≥5 full Tribunal runs in R-4/R-5 alone, independent certification on every merge) demonstrably caught: 1 shipped-defect-at-cert (#46), ≥2 pre-fire trap kills (R-4), ≥3 Tower key errors pre-fire (#7, #9 via Tribunal/Hands), 1 harness that passed a build it was written to indict. Verdict on the question the gate exists to ask: **the discipline is cheaper than the errors it caught.** The one place discipline over-spent: certifying behavior twice (matrix run + prose claim) while never once emitting the artifact — paying for verification and discarding the receipt.

---

## VERDICT

**A disciplined, self-correcting campaign that shipped a client-approved artifact and left an institution-grade record — its one systemic failure is that certified knowledge lives in prose instead of artifacts, and its constitutions (repo and doctrine alike) lag their own rulings.**

---

## ACTION SLATE (max 3)

1. **THE SEAL LAP** — one Hands ignition key: execute the ledgered tidy queue (cache pointer sync, dead selector families, proven orphans → Trash, half-stale `DUR` comment), add the prototype no-submission disclosure *as ruled by the Commander*, record the Découvrez resize edge as production debt, then tag **`hotico-proto-v1`** at the resulting SHA. Optional-if-masters-available: pill re-export at B-geometry density. Explicitly excluded: `Créer un compte` (ratified canon — re-rule or leave), `tel:+40` (client question), any hero touch.
   *Owner:* Hands (key authored by Tower) — *Trigger:* Commander greenlight + his ruling on the disclosure line.

2. **THE HANDOFF LAP** — author `PRODUCTION-HANDOFF.md` as the authoritative reuse policy (reuse map, content-status table FINAL/APPROVED/PLACEHOLDER/…, geometry-coupling contract, seal tag + SHA at top); retire `docs/POLARIS.md` to Trash; rewrite `STATE-MAP.md` to the shipped hero; recover or re-derive the gesture-matrix artifact into `docs/qa/`. This closes F1/C1/C2/C3 and pays POLARIS criterion 3.
   *Owner:* Tower authors, Hands commits — *Trigger:* after the seal tag exists (the doc cites it).

3. **CONSTITUTION SYNC** — one doc-only key to acp-doctrine: bump the Genesis header to v0.4 reconciling the v0.2/v0.3 contradiction and folding in this audit's two new laws (certification-emits-artifact; cost line in every BATON); create `audits/KPI.md` with this audit's row; land this report at `audits/2026-08-11-hotico-campaign-estate-audit.md`. Amend hotico `CLAUDE.md`'s 480px line to name its desktop supersession.
   *Owner:* Hands via doc-only key, Commander ratifies — *Trigger:* immediately; rides the next doc lap.

**PARKED (named, not smuggled):** focus-visible pass · carousel inert/aria-hidden · tabs keyboard behavior (all three → production developer via the handoff doc) · R-2g device pass (I6/I8) · I2 options A–D · Finding B (M10, **oldest open ruling**) · M9 tel question + Alexa side-list (Commander's clipboard) · vous-conversion lap · C4 script-failure fallback · C5 rgb tokens · Genesis §0 fill-in for this Project.

---

## KPI ROW (drafted — series row #1)

| KPI | Value | Tier |
|-----|-------|------|
| PR bounce rate | 0/33 PRs dead; ~8–9 Commander-eye bounces across 33 merged PRs (≈0.26/PR), trending to zero by R-4 via pre-mortem | T2 (LEDGER) |
| Tower error rate | 9 self-ledgered / 48 laps ≈ 0.19 per lap | T2 |
| Certification catch rate | ≥2 real catches by independent cert (doClose #46; false-passing harness #39) | T2 |
| Correct Hands STOPs | ≥3 ledgered (anchor table; aréole hash gate-zero; dial-B refusal) — rising, which is good | T2 |
| Shipped state | 33 PRs merged; live deploy; 0 tags (→ seal lap) | T1 |
| Client signal | changes-requested-and-shipped (T2, #46); approval sentiment Commander-reported | T2 / testimony |
| Career pipeline | UNMEASURED (out of campaign scope) | — |
| Oldest open ruling | Finding B (M10), since 2026-08-08 ≈ 3 days | T2 |
| Oldest frozen front | hero, frozen by declaration 2026-08-09 (healthy freeze, not neglect) | T2 |
| Doctrine debt count | 16 open ledgered items (C1–C5, M1–M12 net of resolved, minus client-side) | T2 |
| Campaign cost | 11 d · 8 Tower · 21 Hands · ~80/20 Sonnet/Opus — **testimony; hours UNMEASURED** (→ F3 cost-line law) | T4 |

**Status: DRAFT-COMPLETE.** RECORD-COMPLETE when the row + this report land in `acp-doctrine/audits/` via the slate-3 key. `KPI.md` does not yet exist; this row founds the series.

---

## SELF-APPLICATION

Gates passed: G0 (declared pre-pull, Commander-ruled budget) · G1 (pull list on record, **one declared degradation:** Tower-chat archive unreachable) · G2 (five-part findings, redundancy-checked against #40/#48) · G3 (full Tribunal run; one suspected finding withheld under the Evidence Law) · G4 (**degraded:** cost dimension rests on Commander recall — the audit cannot exceed its record, which is itself finding F3) · G5 (this document).
Compliance: **COMPLIANT, with declared degradations.**
**Weakest gate: G4 (cost).** Every cost number in this audit is testimony because the campaign never ledgered spend — the audit inherits the exact blindness it convicts in F3, and no amount of pulling can cure it retroactively.

*=== END AUDIT ===*

---

# TRIBUNAL AMENDMENTS — 2026-08-11 (Commander-ordered red team, post-delivery)

*Append-only per LEDGER discipline. The audit above ships unedited; these amendments supersede it where they conflict. The in-audit G3 counter-pass was authored in the same breath as the findings; this pass ran after delivery, on Commander order, and caught what the author's own counter-pass did not — that asymmetry is itself recorded as lesson L7 below.*

**A1 — F1's HIGH is conditioned, not absolute.** HIGH requires harm on the *current trajectory*; that trajectory assumes a production handoff is near. POLARIS carries "webdev status + engine ownership" as an open question — if production is distant or internal (ACP + Hands build it), F1 regrades MEDIUM (compounding debt) and the handoff doc changes shape entirely. **Blocking question to the Commander: who builds production, and when?**

**A2 — Slate action 2's "recover the gesture matrix" has unverified feasibility — and one cheap path unexplored.** The matrix was declared unrecoverable outside the executor session. But Claude Code sessions persist locally on the Commander's machine. **Question: does the Hands session that authored the matrix still exist in local history?** If yes, recovery is nearly free; if no, "re-derive" is the only path and must be costed before briefing.

**A3 — Slate action 3 queue-jumped the Commander's own ritual.** Genesis's header mandates a Polaris audit after its first field deployment before bumping the version. HOTICO's Part-C usage *was* that deployment. Corrected sequence: **Polaris-audit Genesis against the HOTICO record (this audit is the evidence base) → then v0.4.** The Tower proposing to skip the Commander's own gate was enthusiasm dressed as routing — caught, owned.

**A4 — P2/P5 praise re-scoped.** The self-correction and pre-mortem findings hold only *as recorded*: a Tower that erred 20 times and ledgered 9 is indistinguishable in this record from one that erred 9 and ledgered 9. The LEDGER's granularity and against-interest admissions make honest reporting the likelier read — but that is judgment, not evidence. Both findings now read "on everything that reached the record."

**A5 — F2 reframed: present-state defect, not retroactive blame.** No standing law required amending CLAUDE.md when the desktop POLARIS superseded the 480px rule — that law is *proposed by this audit* (new law #3), so past laps cannot have violated it. F2 stands at MEDIUM as a state defect; the "same disease the AAR convicted" line describes the pattern, not culpability. Hindsight check now applied to F2 explicitly: FAIL on blame, PASS on state.

**A6 — Annex verification scope tightened.** The cross-examination table verified each section's *headline* claim at T1; sub-claims were not all pulled at ruling time. Post-tribunal pulls closed the two flagged gaps: §6's window-level listeners CONFIRMED (`main.js:162–175`), §7's aria-expanded tracking CONFIRMED (`main.js:231–349`). Rulings unchanged; the annex's implied full-coverage was an overclaim and is hereby scoped.

**A7 — G4 client signal re-scoped.** Alexandra's approval is T2-corroborated for the *intermediate* state she annotated (pre-R-4). Her approval of the final sealed state is UNMEASURED. The trust-test bonus is not "functionally met" — it is *reported met for a prior state*.

**A8 — KPI row corrections (series row #1 must found a comparable series).** (a) Lap denominator was sloppy: 48 entries ≠ 48 laps; ~5 entries are non-lap (audits, relocation, intake) → **~43 laps, Tower error rate ≈0.21/lap, marked approximate**. (b) The bounce KPI conflated two definitions; the series pins both, separately: **PR-bounce rate** (PRs rejected/abandoned: 0/33) and **eye-bounce rate** (in-lap preview rejections per PR: ≈0.26, trending to 0 by R-4). (c) Live-deployment claim rests on index.html only; areola/in-curand unfetched — deployment consistency for those two pages: UNMEASURED.

**A9 — Protocol miss, owned: the session-open ritual was skipped.** Genesis §4 requires asking the Commander for standing priorities before ruling. The slate was ruled without that ask. **Standing question, now asked: what is the current top priority — job search, HOTICO production, or estate work?** The slate's *urgency* (not content) is provisional until answered; only the seal lap and the Commander's ruling queue are urgency-independent.

**L7 (new lesson, for the methodology synthesis):** the in-authorship counter-pass caught less than the post-delivery, Commander-ordered Tribunal — the author cannot fully adversary itself in the same breath. Candidate practice: high-stakes audits get a *separated* Tribunal pass (next turn or fresh instance) before RECORD-COMPLETE. Noted as manual trial #1; per red-team-protocol's own parking rule, not codified until 2–3 real trials.

**Amended self-application:** weakest gate remains G4, now joined by a named G3 weakness — the counter-pass was structurally soft. Compliance: COMPLIANT, with amendments on the record. Verdict: **unchanged.** Slate: content unchanged, sequencing amended per A3, urgency provisional per A9.

*=== END AMENDMENTS ===*

---

# COMMANDER RULINGS — 2026-08-11 (blocking questions answered; audit closes)

**R1 (production ownership):** Internal — ACP + a fresh Genesis-born Claude Project (Fable-high Tower), timeline after discussion, post-camp. **F1 regrades HIGH → MEDIUM** with escalation trigger: reverts to HIGH the day the production project's Phase R opens without the spec artifacts (handoff doc, STATE-MAP, matrix). HANDOFF lap parks behind that trigger.

**R2 (Hands session survival):** Confirmed — all 21 sessions persist in Claude Code local history. **A2 resolved: matrix recovery is FEASIBLE and cheap** (`claude --resume` → R-2f session → emit matrix + harness to `docs/qa/` on a branch). Folded into the SEAL lap. Standing practice ruled: sessions are cold storage — harvest artifacts on demand, never hoard raw transcripts in repos.

**R3 (standing priority):** 4-week Design Lab vibecode camp begins 2026-08-12 (Figma / Claude / ChatGPT / git / Vercel / Supabase). Slate urgency finalized: SEAL lap + constitution sync ride camp week 1 (cheap); camp project itself is **Genesis field deployment #2** — §0 filled at birth (per F5), the two new laws applied informally from day one, KPI row #2's home. Genesis Polaris audit + formal v0.4 fire mid-camp with two deployments of field data.

**Final status: DRAFT-COMPLETE, rulings integrated.** RECORD-COMPLETE upon the constitution-sync key landing this file at `acp-doctrine/audits/2026-08-11-hotico-campaign-estate-audit.md` + KPI.md row #1.

*=== AUDIT CLOSED — 2026-08-11 ===*
