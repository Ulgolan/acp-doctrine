## 2026-07-24 — Setup session
Built the acp-command-center structure in ~/Documents, then moved the whole folder intact into ~/projects/acp-command-center (git repos traveled with it, none re-initialized). Wrote the root CLAUDE.md constitution (Who/Map/Hard rules/Skills). Installed five skills into .claude/skills/ (acp-writing-style, ai-tic-audit, control-tower, polaris, red-team-protocol) and fixed the acp-writing-style title label from v2.1 to v2.2 to match its existing changelog. Copied acp-writing-style into doctrine/ and made doctrine's first commit.

## 2026-07-31 — vibecode-foundry established + IA Canon installed (branch feat/ia-canon)
Step 0 found no on-disk vibecode-foundry anywhere in the workspace (.claude/skills/ or doctrine/); Tower ruled the registry copy (anthropic-skills:vibecode-foundry) is the sole existing instance and authorized the port with a handshake verification (description opener, title/distilled line, Part I/II structure, four spot anchors — all hit exactly once, 75 lines). Ported as-is to doctrine/vibecode-foundry/SKILL.md (commit 1). Installed the IA Canon feature per IA_CANON_SPEC.md v1.0: new "### IA Canon" section in Part I (five lifecycle moments + embedded six-point audit checklist) and the canon-lite template at doctrine/vibecode-foundry/IA_CANON.template.md (commit 2). §5 law lines output to the Commander as a paste-ready snippet (amended with a rollout clause scoping it to canonized products, pilot AuditLens 2.0); root CLAUDE.md not touched. .claude/skills/ installation of vibecode-foundry parked to the skills-recensement mission. Branch not merged — waits on Tower certification and the Commander's eye. No remote configured on doctrine/, so the branch sits locally rather than pushed.

**Interim Tower ruling (same date):** pass-with-conditions on section placement and template naming/location. Ordered IA_CANON_SPEC.md committed rather than left untracked — moved from doctrine/ root to doctrine/vibecode-foundry/IA_CANON_SPEC.md, colocated with the feature it specifies (commit 4). Flagged doctrine/'s missing remote as a priority item, explicitly out of this branch's exit condition.

**Commander's eye (same date):** v1.0 passed as-is. feat/ia-canon merged into main (merge commit d5a697b, `--no-ff`). Feature branch retained, not deleted — holds until the remote exists.

**Closed:** claude.ai copy of vibecode-foundry synced by Commander (2026-07-31) — registry and doctrine/vibecode-foundry/SKILL.md now match.

**Closed:** doctrine/ remote created — origin `https://github.com/Ulgolan/acp-doctrine.git` (2026-07-31). main pushed with upstream tracking (origin/main), feat/ia-canon pushed alongside (branch retained, not merged away).

**Pending:**
- vibecode-foundry installation into .claude/skills/ — parked to the skills-recensement mission.

### 2026-08-06 — Estate walk: quality findings

Read-only review pass. Scope: full repo tree at `~/projects/acp-command-center/doctrine/` (excluding `.git`). Ground truth read: root `CLAUDE.md`, `doctrine/CLAUDE.md`, `doctrine/LEDGER.md` (full history), `doctrine/vibecode-foundry/IA_CANON_SPEC.md`, `doctrine/vibecode-foundry/IA_CANON.template.md`. No `POLARIS.md` at this repo's root (not flagged — POLARIS applies per-project on demand). Reviewed `main` as it stood before this branch.

**Tally:** 5 PASS, 4 MINOR, 0 CRITICAL.

1. **Layer mixing — PASS.** Pure-markdown doctrine repo, no code files, no cross-contamination (popescuportfolio canon annex in `vibecode-foundry/SKILL.md` Part II stays clearly scoped, not bled into Part I).
2. **Sprawl — MINOR.** `doctrine/.DS_Store` present on disk (untracked, no `.gitignore` anywhere in repo) — nothing stops a future `git add -A` from committing it. `IA_CANON_SPEC.md` correctly relocated to `vibecode-foundry/` per the 2026-07-31 interim Tower ruling, no stray copy left at root.
3. **Magic numbers — PASS.** All numeric thresholds present (e.g. IA_CANON size cap "~60 lines / ~150 lines") are named and rationale-commented, not raw literals.
4. **Drift — MINOR.** LEDGER (2026-07-31) states `feat/ia-canon` "holds until the remote exists"; the remote now exists and has for six days, but no cleanup entry followed — a stale precondition, not a contradiction (see item 8). IA Canon Law text in `doctrine/CLAUDE.md` matches root `CLAUDE.md` verbatim; `vibecode-foundry/SKILL.md`'s IA Canon section structurally matches `IA_CANON_SPEC.md` Component B.
5. **The 10-month test — MINOR.** `doctrine/acp-writing-style/SKILL.md:16` cites `ACP_VOICE_FORENSIC_REPORT.md` for every `[§n]` reference; that file does not exist anywhere in the accessible tree. Same file's Part VII (~line 418) cites `Popescu_Alex_CV.docx` as "the fact source" — also absent. Every citation in a 570-line skill file is currently unverifiable on-disk. Recommend a pointer noting where these actually live. All other doctrine files (vibecode-foundry/SKILL.md, IA_CANON.template.md, IA_CANON_SPEC.md, LEDGER.md, CLAUDE.md) pass — self-contained.
6. **Single-source law — PASS.** `doctrine/CLAUDE.md` diffed byte-for-byte against root `CLAUDE.md` (excluding the mirror-note header line unique to the copy) — content identical, no mirror drift yet. Checklist item X (missing per-repo CLAUDE.md): **N/A / PASS** — doctrine/CLAUDE.md now exists (Mission 0, this session). No AUDIENCES/AUDIENCE_LABELS-class duplication found elsewhere; `IA_CANON_SPEC.md` Component C correctly quotes the Law verbatim rather than restating it independently.
7. **Skill-copy integrity.** `acp-writing-style`: **PASS, byte-identical** — `diff doctrine/acp-writing-style/SKILL.md .claude/skills/acp-writing-style/SKILL.md` returns no differences; both declare v2.2. `vibecode-foundry`: **no counterpart exists yet** in `.claude/skills/` (only acp-writing-style, ai-tic-audit, control-tower, polaris, red-team-protocol are installed there) — consistent with the standing "parked to skills-recensement" note above, so no drift check is possible yet. `doctrine/vibecode-foundry/SKILL.md` itself carries no explicit version number (unlike acp-writing-style's `v2.2`) — a minor traceability gap, see item 9.
8. **`feat/ia-canon` remote branch — fully merged, confirmed.** `git merge-base --is-ancestor feat/ia-canon main` returns true; merged via `--no-ff` commit `d5a697b`. Both local and `origin/feat/ia-canon` still exist. LEDGER's stated retention condition ("holds until the remote exists") is now satisfied. **Logged as a cleanup candidate for future deletion — not deleted in this pass.**
9. **`IA_CANON.template.md` + `IA_CANON_SPEC.md` coherence.** Both located at `doctrine/vibecode-foundry/`. **Spec/template coherence: PASS** — template delivers exactly what spec Component A (§3) prescribes (header block, Section 1 Controlled Vocabulary with matching example row, Section 2/3, Optional Annex with identical three bullets, mandatory Changelog, identical size-cap language). **Version check: gap found.** `IA_CANON_SPEC.md` declares itself v1.0 in its title; `vibecode-foundry/SKILL.md`'s IA Canon section never cites the spec version at all — no contradiction today, but no traceability if the spec is ever bumped. Flagged for a future amendment or the skills-recensement mission.

Branch: `review/estate-walk`. Ritual verdict pending Tower synthesis.

### 2026-08-06 — Estate walk (Hands session close)

**Missions completed:**
- M0 — doctrine/CLAUDE.md committed under version control. Branch: main (Tower exemption, doc-only). SHA `081b19d`.
- M2 — auditlens Vercel Analytics. Branch `chore/vercel-analytics`. SHA `66f1e18`.
- M3 — popescuportfolio Vercel Analytics, all 5 pages. Branch `chore/vercel-analytics`. SHA `84364fd`.
- MA — auditlens quality review. Branch `review/estate-walk`. SHA `218576b`.
- MB — popescuportfolio quality review. Branch `review/estate-walk`. SHA `8b3123b`.
- MC — doctrine quality review. Branch `review/estate-walk`. SHA `e1a7d66`.

**Missions stopped, with reason (anchor failures verbatim):**
- M1 — auditlens npm audit fix. Anchor 1 (4 high vulns naming postcss + sharp) matched exactly. STOPPED at the DO-NOT clause: plain `npm audit fix` resolved only `form-data`, leaving 3 of 4 highs (postcss, sharp, transitively via next) fixable only via `npm audit fix --force`, which the fix output stated "Will install next@16.3.0, which is a breaking change" — a semver-major bump, explicitly forbidden. No commit made; partial lockfile change reverted; stopped branch deleted (never pushed, never diverged from main).

**Missions skipped, with reason:**
- M4 (acp-dashboard deployment check) and MD (acp-dashboard quality review) — SKIPPED. Ground Rule 1 anchor failed at session open: `acp-dashboard/` does not exist as a sibling folder under `~/projects/acp-command-center/` (confirmed by directory listing and a recursive filesystem search for any `*dashboard*` path nearby). Per the brief's STOP-and-report instruction, these missions were not attempted.

**Branch SHAs, consolidated:**
| Repo | Branch | SHA | Mission |
|---|---|---|---|
| doctrine | main | `081b19d` | M0 |
| auditlens | chore/vercel-analytics | `66f1e18` | M2 |
| popescuportfolio | chore/vercel-analytics | `84364fd` | M3 |
| auditlens | review/estate-walk | `218576b` | MA |
| popescuportfolio | review/estate-walk | `8b3123b` | MB |
| doctrine | review/estate-walk | `e1a7d66` | MC |

**Repos walked:** doctrine (M0, MC), auditlens (M1 stopped, M2, MA), popescuportfolio (M3, MB).
**Repos not walked:** acp-dashboard (does not exist as a sibling — M4/MD skipped, see above).

**Flags for Commander (from mission reports):**
- Vercel dashboard: toggle Analytics ON for the `auditlens` project (one click). The `auditlens-db1a` twin project stays parked, untouched.
- Vercel dashboard: toggle Analytics ON for the `popescuportfolio` project (one click).

Ritual verdict: PENDING — Tower synthesis + Commander ruling to follow.

2026-08-06 — Estate walk close-out (Tower synthesis, post-Tribunal)
Tower erratum (M1): the estate-walk brief's Mission 1 preamble asserted the auditlens npm vulnerabilities were plainly fixable ("no major bumps flagged"), based on an offline audit under a different npm version. The live resolution governs: with `next` pinned `^15.1.0`, the remaining postcss/sharp highs require a semver-major Next 15→16 bump. The brief's own stop-guardrail caught the error; the Hands executed the stop correctly. Error owned per doctrine — Tower errors are ledgered, not hidden.
Backlog cage (Tribunal-mandated): of the estate walk's findings, only two items are near-term pulls: (1) the portfolio font defect fix (pending the Commander's rendered-eye confirmation on live popescuportfolio.ch), and (2) acp-dashboard resurrection + review (this session). ALL other findings (auditlens README rewrite, GAP-LIST 2.0 execution, portfolio single-source consolidation, Next 15→16 upgrade, hygiene basket) are PARKED BEHIND dashboard-public (Mikko) and AuditLens field-proving (trust batch + text-only live-fire), and require a deliberate Commander pull to activate. No "just quickly" activations.
Ritual verdict: No standing ritual yet — the first walk's yield was largely first-pass debt, a well that empties. Re-run once after the next major shipping cycle; if the second walk yields like the first, amend the constitution then.
Session accounting: valve usage 0/2 across the entire walk (all code via ignition keys). One Tower error (above). Tribunal ran post-certification at Commander's order: AMBER, three amendments (merge-conflict pre-authorization, rendered-eye check on the font finding, this cage).

### 2026-08-06 — Estate walk: SHIPPED, walk closed
M8 font fix merged to popescuportfolio main after Commander's rendered-eye
gate PASSED on preview (live font census confirmed real Archivo 100..900 +
wdth 62..125; ghost "Archivo Expanded" eliminated from all 5 pages; Tower
ruled the 6-rule case.css stretch deviation PASS — all six consumed the
broken token, restoration not addition). acp-dashboard analytics + estate
LEDGER merged to main, Tower-certified. Analytics now live and transmitting
on auditlens, popescuportfolio (xppm), and acp-dashboard. Estate walk fully
closed: all exit conditions met. Parked untouched, by rule: branch cleanup,
db1a twin, popescuportfolio Drop fossil (Jul 1, no domain — deletion
candidate), probe deployments, skills census, dashboard-public vuln bump,
and the backlog cage items. Ritual verdict stands as written above.

### 2026-08-06 — Doctrine v0.3: seams sealed (Tower audit lap)

One lap, doc-only, closing seams F1r, F3, F4, F8, F9, F10, and the
polaris overlay gap surfaced by the 2026-08-06 Tower audit. Committed
straight to main under the new doc-only exemption this lap itself
introduces (Phase W, Rhythm bullet).

**`templates/PROJECT-GENESIS.md` — v0.2 → v0.3, six amendments:**
1. §0 — GENESIS VERSION AT BIRTH bumped to v0.3; added a BIRTH COMMIT SHA
   field recording provenance (canonical home is
   `acp-doctrine/templates/PROJECT-GENESIS.md`).
2. §SCOPE — reworded the governs-line to drop bare "a repo" from the
   trigger list ("anything with a deployment, a client, or external
   stakes"); the airlock's "a repo meant to last" stays untouched as the
   sandbox-graduation trigger.
3. §3 Phase R, deliverable #3 — added the polaris-overlay note: class
   declaration and the ≥3-data-point rule are Genesis requirements the
   brief must satisfy even though the `polaris` skill itself doesn't name
   them.
4. §3 Phase R, deliverable #1 — added a pointer to harvest
   `UNIVERSAL-LAWS.md` from the doctrine repo into each project's
   CLAUDE.md stub.
5. §3 Phase W, Rhythm bullet — added the doc-only exemption: doc-only
   commits to the doctrine repo may go straight to main, certified
   post-hoc via raw pull at the reported SHA.
6. §3 Phase C — retired the separate handoff document. Session close now
   ends the LEDGER entry with a `>> BATON` block (this entry is the
   first instance); session open reads the newest BATON + live git
   state. Added: Integrity Audit Pass 1 (git-state truth alignment) runs
   at every session close.

**Created `UNIVERSAL-LAWS.md`** (repo root) — seven laws, one line + one
reason each: cache-bust on CSS/JS laps, breakpoint band-walk on
composition laps, honest facades, raw-GitHub-pull certification
(SHA-pinned), Commander's-device-only runtime verification, anchors
naming their search domain, `tokens.css` single-source.

**Created `INTEGRITY-AUDIT.md`** (repo root) — the five-pass runbook
(truth alignment; map vs. territory; reference integrity, with dynamic
paths enumerated rather than skipped; canon compliance, gated on a
declared TOKEN CANON line; ledger vs. git log sync). Findings-only,
zero fixes in-review. Manual-runs-first: no automation until two manual
runs on real repos are ledgered — this pass count starts at zero.

**Root `CLAUDE.md`** (outside this repo, not part of this commit — the
enclosing folder isn't a git repo) — one line added to the Map: local
folders drop the `acp-` prefix, 1:1 against their repo (`doctrine/` ↔
`acp-doctrine`).

**Parked, not fixed this lap:** `templates/PROJECT-GENESIS.md` §4's
"Session open ritual" bullet still reads "handoff/LEDGER" — a stale
reference to the document this lap just retired. Out of the six
enumerated amendments, so left as-is and spun off as a separate
follow-up rather than improvised in-lap.

All five anchors (A1–A5) confirmed matching exactly once before edit;
none required a stop-and-report.

>> BATON
Session: 2026-08-06 — Doctrine v0.3 (seams sealed)
Status: CLOSED. One commit to main, doc-only exemption. SHA reported to
  the Commander at session end (see chat, not duplicated here to avoid
  a self-referential hash in the commit that produces it).
Next: Tower certifies via raw pull at the reported SHA before the
  Commander's eye. First live use of the BATON block — next session
  open should confirm this block was actually legible/sufficient
  without a separate handoff doc, and ledger that verdict.
Open: INTEGRITY-AUDIT.md is new and unrun — needs two manual, ledgered
  passes on real repos (this repo is a candidate for pass 1) before
  automation is even discussable. §4 stale "handoff" reference parked
  above, spun off as its own follow-up.

### 2026-08-06 — Doctrine v0.3 patch: §4 handoff reference reconciled

Session opened per the new ritual: read the BATON block above + this
LEDGER, confirmed live git state matched (`main` at `4442594`, clean
tree apart from untracked `.DS_Store`). Picked up the item parked in
that BATON's Open line.

**Fix:** `templates/PROJECT-GENESIS.md` §4 STANDING GUARDRAILS, "Session
open ritual" bullet, reworded "read the latest handoff/LEDGER" → "read
the newest BATON block + LEDGER", matching §3 Phase C's BATON language.
No other content touched, per the follow-up's explicit scope.

**Version:** not bumped. The file's own header ties version bumps to
first field deployment + a Polaris-audit, not to per-edit doc fixes;
the v0.2 → v0.3 bump was an explicit brief override, not a new standing
policy. This one-line consistency fix stays under v0.3, noted here
instead — the more conservative of the two options the follow-up
offered.

>> BATON
Session: 2026-08-06 — §4 handoff reference reconciled (patch)
Status: CLOSED. One commit to main, doc-only exemption. SHA reported to
  the Commander in chat.
Next: nothing outstanding from this fix.
Open: INTEGRITY-AUDIT.md still unrun — 0/2 manual passes ledgered.

## 2026-08-09 — Constitutional amendment: Dispatch Law installed in root
CLAUDE.md (remote-session doctrine). Context: Dispatch paired to
Commander's iPhone 09.08. Standing config locked same day: Code
permissions manual, computer use OFF, no browser connected, run on
startup OFF, keep awake ON. Law defines remote scope (preview-branch
work only, ship actions desk-only), ambiguity rule (vague remote asks
= read-and-report), end-of-watch rule. Amendment drafted by Tower,
red-teamed (Amber, two plies integrated), installed by Sonnet Hands
session (this entry).

2026-08-09 — Drift note: mirror sync revealed root CLAUDE.md carried
a "Naming:" line (Map section) absent from the mirror — root and
mirror were NOT byte-identical despite the 06.08 certification.
Line content verified true (doctrine/ ↔ acp-doctrine confirmed via
origin URL). Ruled benign process miss by Tower; mirror brought
fully current. Lesson parked: mirror sync must be part of any
session that edits root, not a separate errand.

## 2026-08-11 — HOTICO campaign estate audit landed (constitution sync, doc-only)

Full-tribunal estate audit of the HOTICO prototype campaign (`Ulgolan/hotico-proto`
main @ `a0e18cd`), Commander-supplied, landed at
`audits/2026-08-11-hotico-campaign-estate-audit.md` — byte-identical move
from repo root, zero edits to content. Campaign sealed at tag
`hotico-proto-v1`, merge `4b5652f`. Verdict: COMPLIANT, with amendments
on the record (see the audit's own AMENDMENTS block).

**KPI series founded.** `audits/KPI.md` created — the estate's first
append-only KPI table, row #1 seeded from this audit: 0/33 PR-bounce,
~0.26 eye-bounce/PR trending to 0 by R-4, ~0.21 Tower err/lap (9/~43,
lap-denominator corrected per the audit's own A8 amendment), >=2 cert
catches, >=3 Hands STOPs, 33 PRs merged + live deploy, client signal
T2 for changes-shipped with final-state approval UNMEASURED, oldest
open ruling ~3 days (Finding B), 16 doctrine-debt items, cost line
carried as Commander testimony (11d / 8 Tower / 21 Hands / ~80-20
Sonnet-Opus) — hours themselves UNMEASURED, per the audit's F3 finding
that cost is structurally invisible in the primary record.

**Genesis header reconciled.** `templates/PROJECT-GENESIS.md` line 2
bumped `v0.2` → `v0.3` and annotated: the `v0.3` amendment (`4442594`,
2026-08-06) updated the template body without bumping this header line
(the audit's F2(d) finding) — this lap fixes the header-only
contradiction. No other line touched. The `v0.4` bump itself stays
parked, per the audit's own R3 ruling, until the mandated
post-first-deployment Polaris audit fires mid-camp.

**Two laws named for the record, FIELD-TRIAL status.** Proposed by this
audit (F1/F3, ratified in its R3 ruling) but explicitly NOT installed
into any doctrine file this lap — naming them here is the full extent
of this session's action on them, pending the Genesis Polaris audit:
- **certification-emits-artifact** — certification of a build should
  produce a re-runnable artifact (spec, matrix, harness), not just a
  ledger sentence and a pass count.
- **BATON COST line** — every session-close BATON block should carry
  a cost line (sessions, model mix, rough hours) so cost stops being
  invisible between audits.

Doc-only lap per Genesis §3's exemption — all three files committed
straight to main; Tower certifies post-hoc via raw pull at the reported
SHA. The audit itself flips DRAFT-COMPLETE → RECORD-COMPLETE at that
certification.

>> BATON
Session: 2026-08-11 — HOTICO estate audit landed, KPI series founded,
  Genesis header reconciled
Status: CLOSED. Commits to main, doc-only exemption. SHAs reported to
  the Commander in chat.
Next: Tower certifies via raw pull at the reported SHA — audit flips
  DRAFT-COMPLETE → RECORD-COMPLETE on that certification. Genesis
  Polaris audit + formal v0.4 fire mid-camp (per R3), with two field
  deployments (HOTICO + the Design Lab camp project) as its data.
Open: certification-emits-artifact and BATON COST line sit at
  FIELD-TRIAL status, not yet installed into any doctrine file — wait
  on the Polaris audit before codifying. INTEGRITY-AUDIT.md still
  unrun — 0/2 manual passes ledgered.

## 2026-08-12 — Amendment Package A-1 "The Instruments" filed (draft, unsealed)

Amendment Package A-1 "The Instruments" filed as DRAFT (v0.4-rc
target) — Commander override of RED tribunal verdict on timing,
logged in the package's A-0; seal pending (ruling number + A-3 trial
expiry unset); R3 audit will adjudicate against camp field evidence.

Note: initial run stopped on anchor miss — Tower brief error (anchor
transcribed from prose, not bytes), corrected in-flight; stop-and-report
law held.

## 2026-08-15 — A-1 "The Instruments" SEALED (ruling R4)

2026-08-15 — A-1 "The Instruments" SEALED (ruling R4). Genesis v0.3 →
v0.4. A-3 discovery-cadence trial expires 2026-09-12. ⚙ clauses live
on auditlens (first instrumented repo, PR #2 merged 49fc53a, repo
public, ruleset enforced, secret armed).

CORRECTION (2026-08-30, auditlens Gate Zero pass): the "repo public"
claim above was **false** on this date — auditlens did not actually go
public until 30 Aug 12:37 UTC, two weeks later. The "ruleset enforced"
claim was **true**, verified via `/rulesets` (ruleset "main-harness",
id `20875261`, required check "harness" on `main`).

## 2026-08-17 — Genesis v0.4 consolidated into single canonical file

`templates/PROJECT-GENESIS.md` overwritten byte-faithful with the
Commander-supplied consolidated v0.4 file: the A-1 "The Instruments"
amendment body is now merged INLINE, and the file stands as the single
canonical Genesis document. `templates/GENESIS-AMENDMENT-A1-THE-INSTRUMENTS.md`
archived (git mv, history preserved) to `templates/archive/`. MINOR
finding "§0 pre-filled v0.3" cleared by this commit.

Tower anchor imprecision caught by executor stop-and-report, amended
in-flight — per the errors-are-ledgered law: the Tower's initial
ignition key anchored on the header containing "v0.4" exactly once,
but the header legitimately mentions v0.4 twice; the executor stopped
rather than improvise, and the Tower amended the anchor to "sealed
2026-08-15 per Commander ruling R4" (verified exactly once) before
authorizing proceed.

Doc-only lap, straight to main per the Genesis doc-only exemption.
Mirror sync (Claude Project instructions) = Commander manual step —
this session cannot reach that surface.

>> BATON
Session: 2026-08-17 — Genesis v0.4 consolidation (doc-only)
Status: CLOSED. One commit to main, doc-only exemption. SHA reported to
  the Commander in chat.
Next: Commander manual step — sync Claude Project instructions mirror
  to the new consolidated file.
Open: INTEGRITY-AUDIT.md still unrun — 0/2 manual passes ledgered. R3
  Polaris audit + two field deployments still pending mid-camp.

## 2026-08-17 — Amendment Package A-2 "The Ledger's Gravity" SEALED

`templates/PROJECT-GENESIS.md` v0.4 → v0.5 sealed per Commander ruling.
Amendment Package A-2 "The Ledger's Gravity" adopted at the SolJour Lap
2 boundary, applied byte-faithful (four FIND/REPLACE edits, each anchor
verified landing exactly once against the in-repo tip before editing):
**branch-point law** (an ignition key's branch point is always the
current main tip, verified doc-only/ledger-append since the last
certified SHA — never a frozen SHA alone; a SHA quoted inside a ledger
entry is never the tip), **ledger-append law + pre-merge micro-entry
codicil** (session-close LEDGER appends may land directly on main in
any Genesis repo, append-only, post-hoc Tower certification mandatory;
where a merge gate checks commits at push time, certification
micro-entries ride the lap branch as its final commit before the merge),
and **photograph doctrine** (the harness photographs certified current
behavior, not a shrine — a legitimately changed behavior gets the
photograph retaken and certified, never contorted code to keep old
assertions green). All three field-proven in SolJour LEDGER #5–#8
before this adoption (two Tower briefing errors, both caught by
executor stop-and-report law, zero damage); R3 Polaris audit
adjudicates A-2 alongside A-1 against field evidence.
`templates/archive/AMENDMENT-PACKAGE-A2.md` archived (copied, per A-1
precedent) for the provenance chain.

Note: mirror sync (Claude Project instructions) = Commander manual
step — this session cannot reach that surface.

Doc-only lap, straight to main per the Genesis doc-only exemption.

>> BATON
Session: 2026-08-17 — Amendment Package A-2 sealed, Genesis v0.5
  (doc-only)
Status: CLOSED. Single commit to main, doc-only exemption. SHA reported
  to the Commander in chat.
Next: Commander manual step — sync Claude Project instructions mirror
  to v0.5. R3 Polaris audit adjudicates A-1 and A-2 together against
  SolJour + AuditLens field evidence.
Open: INTEGRITY-AUDIT.md still unrun — 0/2 manual passes ledgered.

## 2026-08-17 — A-2 seal ruling number recorded (R5)

A-2 seal = Commander ruling R5, assigned post-seal 2026-08-17;
constitution seal line amended to match. Ruling sequence: R4 = A-1,
R5 = A-2.

## 2026-08-17 — Integrity Audit manual pass 1/2

*This report certifies file integrity, not product behavior. The
Commander's device remains the only runtime truth.*

Five-pass runbook (`INTEGRITY-AUDIT.md` v1.0) executed manually against
`acp-doctrine` at HEAD `b7502d1` (origin not yet updated at pass time —
see Pass 1). Findings-only: zero fixes applied in-review; every item
below is backlog, caged behind declared priorities.

**Pass 1 — Truth alignment: PASS, with one flagged transient (T1).**
Working tree clean except pre-existing untracked `.DS_Store` (see Pass
2). `git log` and local `git status` agree with each other. At the
moment this pass ran, local `HEAD` (`b7502d1`, the R5 seal commit) sat
one commit ahead of `origin/main` (`03aab38`) — flagged per protocol
("any local commit not yet pushed"), but neither LEDGER.md nor
CLAUDE.md asserts that commit as already shipped, so no claim
contradicts git state. Resolves at this same session's push (below).

**Pass 2 — Map vs. territory: 2 MINOR.**
- MINOR (T2): `CLAUDE.md`'s Map section documents the surrounding
  acp-command-center ecosystem (sibling repos `doctrine/`, `auditlens/`,
  `.claude/skills/`) — it is a mirror of the root constitution, not a
  map of `acp-doctrine`'s own tree. No section anywhere in this repo
  maps its own tracked files (`INTEGRITY-AUDIT.md`, `UNIVERSAL-LAWS.md`,
  `templates/`, `vibecode-foundry/`, `acp-writing-style/`, `audits/`).
  Not necessarily broken — these are cross-referenced via LEDGER — but
  Pass 2's map-vs-territory premise has no internal map to diff against
  in this repo as currently scoped.
- MINOR (T1, recurring): `.DS_Store` untracked at repo root, no
  `.gitignore` anywhere in the repo. First flagged in the 2026-08-06
  estate walk (item 2); still present and unresolved 12 days later. A
  future broad `git add -A`/`git add .` would sweep it in.

**Pass 3 — Reference integrity: 1 MINOR, 1 dynamic set enumerated.**
- MINOR (T1, recurring): `ACP_VOICE_FORENSIC_REPORT.md`, referenced by
  `acp-writing-style/SKILL.md:16` and this ledger's 2026-08-06 entry,
  confirmed still absent from the repo (`find` returns nothing). First
  flagged 2026-08-06 (item 5); still unresolved.
- Dynamic, enumerated per protocol (not a finding): `IA_CANON.md`,
  referenced from `CLAUDE.md`, `vibecode-foundry/IA_CANON_SPEC.md`, and
  `vibecode-foundry/SKILL.md` — a per-project template filename each
  shipping project instantiates at its own repo root, not expected to
  exist inside `acp-doctrine` itself.
- All other static same-repo references checked (`UNIVERSAL-LAWS.md`,
  `INTEGRITY-AUDIT.md`, `CLAUDE.md`, `LEDGER.md`,
  `templates/PROJECT-GENESIS.md`, both `templates/archive/` files,
  `vibecode-foundry/SKILL.md`, `vibecode-foundry/IA_CANON_SPEC.md`,
  `audits/KPI.md`, `audits/2026-08-11-hotico-campaign-estate-audit.md`)
  resolve. PASS. The hotico estate-audit report's internal references
  (`PRODUCTION-HANDOFF.md`, `STATE-MAP.md`, `docs/POLARIS.md`,
  `README.md`) point into the external `hotico-proto` repo the report
  describes — out of scope for this repo's reference walk, noted rather
  than silently skipped.

**Pass 4 — Canon compliance: 1 CRITICAL.**
- CRITICAL (T2): `CLAUDE.md` carries no TOKEN CANON declaration. Per
  protocol this is an automatic CRITICAL and the pass stops there —
  vocabulary-drift checking against a canon that was never declared is
  not performed this pass.

**Pass 5 — Ledger vs. git log sync: PASS (T2, sampled).**
All 28 `acp-doctrine` commits trace to one of 13 LEDGER.md session
entries, 2026-07-24 → 2026-08-17. Every SHA this ledger cites as an
`acp-doctrine` commit exists in `git log` (`081b19d`, `4442594`,
`d5a697b`, `e1a7d66`, plus this session's `03aab38`/`b7502d1`). Every
SHA cited but absent from this repo's log (`218576b`, `49fc53a`,
`4b5652f`, `66f1e18`, `84364fd`, `8b3123b`, `a0e18cd`) is explicitly
attributed in its own sentence to a different named repo (`auditlens`,
`popescuportfolio`, `hotico-proto`) — no orphaned or ambiguous claim
found.

**Tally: 1 CRITICAL, 4 MINOR, 2 PASS (Pass 1 transient self-resolves
this session).** All findings caged to backlog per the project's
declared priorities — zero fixes applied in this review.

>> BATON
Session: 2026-08-17 — Integrity Audit manual pass 1/2 (doc-only)
Status: CLOSED. Pass 1/2 ledgered. Mirror sync (Claude Project
  instructions) still Commander-manual. R3 Polaris audit adjudicates
  A-1 + A-2 together against SolJour + AuditLens field evidence.
Next: manual pass 2/2 — required before any automation of
  INTEGRITY-AUDIT.md per its own manual-runs-first rule. Backlog carries
  this pass's 1 CRITICAL (no TOKEN CANON declaration) + 4 MINOR (map
  scope gap, `.DS_Store`/no `.gitignore`, dead `ACP_VOICE_FORENSIC_REPORT.md`
  reference, this session's transient unpushed commit — resolved by
  this session's own push).
Open: R3 Polaris audit + two field deployments still pending mid-camp.
HARNESS: n/a tests (no test suite this repo) · last full eval n/a ·
  signals n/a.

## 2026-08-19 — Campagne FORMULAIRE scar tissue codified (doc-only)

Four laws appended to `UNIVERSAL-LAWS.md`, each cited against verified
case studies rather than asserted from memory: **The Key Pre-Flight
Law**, **Consumer lists are enumerated, never remembered**,
**Manifests derive from the DOs**, and **The pulse marks the
boundary**. Case studies drawn from Campagne FORMULAIRE
(2026-08-19, `hotico-proto`): a key that ordered "keep the existing
prototype note" on a page that had none (`hotico-proto` LEDGER entry
#51, DEVIATION FLAGGED) and the phrase "both consumer pointers"
letting a third consumer drift three versions stale before a
Tribunal enumerated (entry #54). This closes the estate audit's
outstanding **A1** and **pulse-habit** amendments as codified
doctrine — both now CLOSED.

**F-3 manifest-vs-DO contradiction — ledgered here for the first
time.** The F-3 WhatsApp-handoff key's manifest declared five files
while its own DOs required six files. Caught and resolved in-session
by the executor on 2026-08-19; the deviation was never ledgered in
`hotico-proto` itself. This entry is that contradiction's ledger of
record, and the case study **The Key Pre-Flight Law** cites for its
third example.

**BATON field spec landed.** `templates/PROJECT-GENESIS.md` gains a
sibling bullet directly before "The BATON carries the instrument
panel": the six-field spec (`STATE` · `CERTIFIED` · `OPEN` · `NEXT`
· `TRAPS` · the HARNESS panel line, in that order). This entry's
closing block is the spec's first compliant instance.

**`.gitignore` created.** Two entries, `.DS_Store` and `._*`,
closing the estate audit's recurring MINOR finding (first flagged
2026-08-06, still open as of the 2026-08-17 Integrity Audit pass).

Doc-only lap per Genesis §3's exemption — all four files (
`UNIVERSAL-LAWS.md`, `templates/PROJECT-GENESIS.md`, `.gitignore`,
this entry) committed straight to main.

>> BATON
STATE: Four laws codified in `UNIVERSAL-LAWS.md`; BATON field spec
  installed in `PROJECT-GENESIS.md`; `.gitignore` created; F-3
  contradiction ledgered as its record of first mention.
CERTIFIED: pending Tower — commit pushed straight to origin/main
  this lap per the doc-only exemption; starting and ending SHAs
  reported to the Commander in chat; certify via raw pull at the
  ending SHA per the Raw GitHub Pulls law.
OPEN: none from this lap. Carried forward unchanged: R3 Polaris
  audit + two field deployments pending mid-camp; INTEGRITY-AUDIT.md
  manual pass 2/2 still unrun.
NEXT: Tower certifies via raw pull at the reported ending SHA.
TRAPS: none known.
HARNESS: n/a tests (no test suite this repo) · last full eval n/a ·
  signals n/a.

## 2026-08-21 — Gate Zero security section inserted into vibecode-foundry

**Gate Zero — Security** inserted into `vibecode-foundry/SKILL.md`,
immediately before `### The rogues' gallery`, per an ignition key
drafted by the Tower off a Tribunal run (verdict Amber, six plies
integrated). Seven checks (RLS, secrets, wallet guard, input
discipline, paid-endpoint rate limits, server-side auth, nFADP
business-data flag), a scope valve for static pages, and a standing
brief-injection line for every future ignition key. Ground-truth
questions (branch, HEAD SHA, anchor uniqueness, no prior Gate Zero
section, clean tree) re-verified from local disk before the edit,
per the key's own physics.

**Staleness note:** the repo copy (`doctrine/vibecode-foundry/SKILL.md`)
is now canonical-and-current. The read-only anthropic-skills registry
copy and the claude.ai skill editor copy are both STALE as of this
commit — ACP pastes the same Gate Zero block into the claude.ai skill
editor by hand, above the rogues' gallery, same anchor. That paste
cannot be delegated.

>> BATON
STATE: Gate Zero section landed in `vibecode-foundry/SKILL.md`,
  verified by grep receipt (single occurrence, above the anchor;
  anchor still occurs exactly once).
CERTIFIED: pending Tower — this session was executor only, per the
  no-self-certification rule.
OPEN: claude.ai skill registry copy is stale until ACP pastes Gate
  Zero into it by hand. Cross-reference edit to the estate-audit line
  (Cross-references, file bottom) not yet applied — separate commit,
  pending push confirmation.
NEXT: Tower certifies via raw pull at the reported ending SHA. ACP
  manually updates the claude.ai registry copy.
TRAPS: none known.
HARNESS: n/a tests (no test suite this repo) · last full eval n/a ·
  signals n/a.

## 2026-08-24 — THE SCAR LEDGER FOUNDED

Canonical catalogue SCAR-LEDGER.md lands at repo root; mantra-layer
skill archived at skills/the-scar-ledger/SKILL.md and installed
working at command-center .claude/skills/. Founded from a Commander
insight (a list of learnings grants independence and self-reflection);
harvested cold same-day from four LEDGERs and eight sessions (~35
self-owned Tower errors, Jul-Aug 2026); distilled to seven failure
modes; draft survived its own Tribunal (AMBER, three amendments,
including an evidence overclaim caught inside the document about
evidence overclaims). Append ritual per the skill: closing Tower
proposes in BATON, next Tower cold-reviews, Commander ratifies in one
word, Hands commit. Thesis line inherited verbatim from the
hotico-proto ledger: keys are theories; every fired error traced to an
unverified assumption, every catch to a pull of ground truth.
Doc-only lap, straight to main per exemption; Tower certifies via raw
pull post-merge.
