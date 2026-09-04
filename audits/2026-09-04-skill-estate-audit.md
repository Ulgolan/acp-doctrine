# ESTATE AUDIT — Skill estate (census, conflict-map refresh, rightsizing)

Scope: all skills in the claude.ai registry (`/mnt/skills/user/`, `/mnt/skills/plugins/`) and their repo copies in `Ulgolan/acp-doctrine` | Standard: estate-audit SKILL.md (founded 2026-08-10, text as mounted 2026-09-04), root CLAUDE.md as mirrored at `acp-doctrine@bd3c88b`, BATON of 2026-09-04 | As of: 2026-09-04, `acp-doctrine` main @ `bd3c88b850d176b23a9a2a73538a464a48f2c221` (committed 2026-09-02 12:57)
Budget: STANDARD (full gates, full KPI row; red-team-protocol applied to the precedence-rule draft only, not to the whole audit)
Out of this audit's scope: the Code-side `.claude/skills/` folder (not reachable from a claude.ai session — measured by a Hands key, see slate 3); the AgentShield findings themselves (input to a future gate 3, not rulings here); any skill edit; any CLAUDE.md install; Live-fire #1, the gauntlet template, the Supabase laws; Polaris audits of any product; the interior prose of the 14 skills not fully read (listed under coverage in G1).
Status: DRAFT-COMPLETE at G5. RECORD-COMPLETE when this file, its KPI row and the LEDGER entry land on `acp-doctrine` main via a Hands doc-only lap.

---

## G1 PULLS

| # | Source | Method | Anchor | Result |
|---|---|---|---|---|
| 1 | claude.ai registry, 18 user skills + 1 plugin skill | `ls` / `wc -c` / `wc -l` on `/mnt/skills/user/*/SKILL.md` and `/mnt/skills/plugins/vibecode-foundry/SKILL.md` | mount as of 2026-09-04 | OK — 18 user skills, 292,324 B; foundry 22,697 B in `plugins/` |
| 2 | `acp-doctrine` main | codeload tarball `refs/heads/main`; SHA pinned via `git ls-remote` and the tarball pax `comment` header (both agree) | `bd3c88b`, 2026-09-02 12:57 | OK. `api.github.com` DEGRADED (rate-limited on shared IP, documented rake) — not relied on |
| 3 | `acp-doctrine` LEDGER.md tail + heading index | full read of the last 120 lines; grep of all `## ` headings | `bd3c88b` | OK |
| 4 | `acp-doctrine/audits/` directory listing + KPI.md | `ls`, `cat` | `bd3c88b` | OK — one report (2026-08-11), one KPI row |
| 5 | `acp-doctrine/SCAR-LEDGER.md` vs project-knowledge copy | `diff` | `bd3c88b` vs `/mnt/project/SCAR-LEDGER.md` | OK |
| 6 | Repo skill copies vs registry copies (writing-style, foundry, scar-ledger) | `diff`, marker `grep -c` (AUTONOMY, Gate Zero, THE SPINE, Station 9) | `bd3c88b` vs mount | OK |
| 7 | F2/F3 hotfix status | `grep -n` for `does NOT code` family and `here's the thing`/`fondue` across all 19 skills | mount, 2026-09-04 | OK |
| 8 | 21.08 audit record | `conversation_search` ×3 into the hostile-validation chat of 2026-08-21 | chat `809c8fb1…`, updated 2026-08-21 10:36 | OK but **T3** — digests only. The authoring session's full F1–F6 list was not recoverable; F1 and F5 of the 21.08 report are unknown to this audit |
| 9 | Byte reconciliation 21.08 census → today | arithmetic on pull 1 against the census figures in pull 8 | see F1 | OK — byte-exact |
| 10 | Staleness markers across all 19 skills | `grep -ciE` on dates Mar–Aug 2026, "bridge-era", "intro pricing", "pending", "parked", model names | mount, 2026-09-04 | OK |
| 11 | Heading census of all 19 skills | `grep -E '^#{1,3} '` | mount, 2026-09-04 | OK |
| 12 | Full reads | acp-personal-context, acp-companion-style, the-scar-ledger, estate-audit, control-tower; `acp-doctrine` CLAUDE.md (mirror), INTEGRITY-AUDIT.md, KPI.md | mount / `bd3c88b` | OK — **5 of 19 skills fully read** |
| — | *Discarded:* a skill-name cross-reference regex that tokenised "red-team-protocol" into "team-protocol" and reported its own artefacts as dead links | — | — | Binned before any claim rested on it; nothing below cites it |

**Counting method (declared, per the 21.08 hygiene note):** byte counts are `wc -c`; line counts `wc -l`; phrase counts `grep -c -i` on the exact strings named; staleness counts `grep -ciE` on the pattern stated in pull 10. Reproducible by anyone with the mount.

**Coverage statement:** five skills fully read. The other fourteen were judged on heading census, byte size, staleness-marker greps, and targeted line pulls. Per-skill verdicts below name their coverage; no KEEP below claims the interior is clean where the interior was not read.

---

## THE FIVE GROUND-TRUTH QUESTIONS (from the BATON)

**Q1 — Did the 21.08 hotfix Hands session run? Is the report RECORD-COMPLETE?**
NOT FILED, NOT RUN on the registry. `audits/` at `bd3c88b` holds only `2026-08-11-hotico-campaign-estate-audit.md`; KPI.md has one row (2026-08-11); no LEDGER heading between 2026-08-21 (Gate Zero) and 2026-08-24 (scar ledger) mentions a census, conflict map, or hotfix (T2, `bd3c88b`). The registry still carries every F2/F3 line the 21.08 validation cited — and pull 9 supports it: the registry's byte SUM reconciles exactly to the 21.08 census once the three named changes are removed (T1 today, T3 census figures); per-file identity is verified for the five largest unchanged skills whose 21.08 sizes are on record (writing-style, brand-methodology, tic-audit, cyoa, red-team), and the F2/F3 lines were grepped directly — a cancelling pair among the remaining twelve is arithmetically possible and not excluded. Commit SHA: none exists. Whether a Hands session ran locally and never pushed: UNMEASURED (slate 3 asks the disk).

**Q2 — Registry duplication in Code; which copy wins?**
UNMEASURED from this seat. What is measurable: `acp-doctrine` holds three skill copies — `acp-writing-style/SKILL.md` (repo root), `skills/the-scar-ledger/SKILL.md`, `vibecode-foundry/SKILL.md` (repo root); two locations, one convention short of a rule (T1, `bd3c88b`). Repo↔registry parity today: scar-ledger IDENTICAL; foundry identical except a trailing newline (all four content markers present in both); writing-style identical except the title line (repo `v2.2`, registry `v2.1`; both bodies carry the v2.2 changelog) (T1). Code-side `.claude/skills/` — count, versions, load precedence — needs a Hands measurement (slate 3).

**Q3 — estate-audit's two parked amendments?**
STILL PARKED. Neither "counts declare their method in G1" nor "praise is scoped to read coverage" appears in the mounted estate-audit text; the skill carries no version line or changelog by which a ruling could be recorded; no LEDGER entry rules on them (T1 + T2). This audit applies both voluntarily (see G1 counting method, and the coverage statement).

**Q4 — control-tower's bridge-era text?**
CONFIRMED STALE, verbatim at the mount: line 40 `*(Routing reflects bridge-era pricing. Re-audit via Polaris when Fable returns to subscriptions.)*`; line 92 `**This doctrine is bridge-era.** The Fable paywall is officially temporary. When Fable returns to standard subscriptions, re-audit this skill via Polaris — the routing matrix may loosen, the role definition should not.`; line 93 `Sonnet 5 intro pricing ends August 31, 2026; executor economics shift then.` (T1). Both dated triggers have fired: 31 August has passed; this Tower session runs on Fable 5.1 (T1, system-declared) under ACP's subscription (T3, BATON). The skill's own re-audit condition is met. See F4 and the routing verdict.

**Q5 — the "does NOT code" pair?**
NOT AMENDED. Verbatim: personal-context line 24 `- Does NOT code - finds it intimidating and incomprehensible`; line 25 `- Brain not wired for programming`; line 27 `- Avoid suggesting coding solutions unless explicitly requested`; line 70 `- Suggesting coding solutions unprompted` (under "What to AVOID"); line 108 `- You remember his non-technical background`. companion-style line 73 `- Non-technical UX designer (avoid suggesting coding unless explicitly asked)`; line 116 `- Suggest coding solutions unprompted` (under "Don't Do These") (T1). Against them: root CLAUDE.md mirror line 5 `Vibecoder — directs AI to build; not a code expert at all.` (T1, `bd3c88b`), and "vibecod" appears in seven sibling skills today — brand-methodology, dashboard-export, project-pulse, control-tower, polaris, the-letter-on-the-table, vibecode-foundry (T1; the 21.08 list had six — the letter is the seventh, presence-grade only, not semantically read here).

---

## FINDINGS

**F1 — The 21.08 skill audit died between DRAFT-COMPLETE and RECORD-COMPLETE, and the hotfix it ratified never fired.** T1 (F2/F3 lines grepped live; byte-sum reconciliation as corroboration) + T2 (LEDGER, audits/, KPI at `bd3c88b`) | **HIGH** — "will produce a wasted lap if left unaddressed": the lap is already being wasted — this session re-derived part of the conflict map from digests, and two of the six 21.08 findings (F1, F5) were not recovered in four conversation searches — the authoring chat did not surface; they may still exist there. The skill's own words: "only silence between them is not [legitimate]" — fourteen days of it. | as of 2026-09-04, `bd3c88b`.
Hindsight check: n/a — this judges present state, not a past decision. The BATON author flagged it; the state was knowable.

**F2 — The two always-on skills still forbid what the constitution says ACP does.** T1 (lines quoted under Q5) | **MEDIUM** — friction that compounds: every session opens under a self-contradiction the Tower must silently resolve; no near-term harm because the Tour project instructions override with "he's a vibecoder". Confirmation of record (21.08 F2), stronger by one sibling. | as of 2026-09-04.

**F3 — The struck phrase lives in brand-methodology on the portfolio-copy path.** T1: line 81 `"Here's the thing about UX research in traditional environments: not everyone gets it right away."` (Portfolio / Case Studies voice row); line 243 `In ACP voice — "Here's the thing..."`. writing-style §VII strikes `Here's the thing...` under the verbatim Commander ruling. Fondue anchors at 82, 197, 438, 448, 466 are references to a real post, not the struck phrase — the 21.08 hotfix scope included 82/197 for a reason this audit could not recover (T3 gap). | **MEDIUM** — drift that compounds on a path with no mandated tic-audit auto-trigger. Confirmation of record (21.08 F3 + the validator's line-81 escalation). | as of 2026-09-04.

**F4 — control-tower's routing matrix is governed by conditions that no longer hold, and the skill itself demands re-audit.** T1 (lines 40, 92, 93 quoted under Q4) | **MEDIUM** — a routing matrix built around a Fable premium that ACP no longer pays produces mis-routed laps (cost, not defect). The role definition and the four functions show no staleness. | as of 2026-09-04.
Hindsight check: the 31 August date was written into the skill by its author as the trigger — it was knowable by construction; not a miss, a due maintenance.

**F5 — project-pulse's search-term registry is dated "as of March 2026".** T1: line 33 `These are ACP's known active workstreams as of March 2026.`; the table lists Brand Engine, Dashboard (Cursor-era terms), Division 2 UX, Podcast — and no doctrine, brand-kit, scar ledger, estate audit, gauntlet, or hotico-proto vocabulary. CLAUDE.md mirror line 24: `Not ported (chat-only, pending rewrite): project-pulse, dashboard-export.` | **MEDIUM** — a pulse run on stale terms misses the fronts that actually moved; rising cost, no near-term harm. | as of 2026-09-04, `bd3c88b`.

**F6 — Sixteen of nineteen skills exist in no version-controlled location this audit can see.** T1 (three repo copies at `bd3c88b`) + T2-INFERRED (LEDGER 2026-09-02: `Root CLAUDE.md (outside this repo) edited but not committed here — not in git`; the 2026-08-06 backlog question "whether acp-command-center root deserves its own repo" has no closing entry) | **MEDIUM** — debt that compounds: a corrupted or mis-pasted registry skill would be rebuilt from chat archaeology. Not HIGH: no loss is on the record. The constitution's map says `doctrine/ → skill-forge`; the forge holds 3/19. | as of 2026-09-04.
Hindsight check: partial — the port was consciously parked ("skills-recensement mission", LEDGER 2026-07-31); this is a confirmation that the parked item is still parked, not a miss.

**F7 — acp-writing-style: registry title says v2.1, body and repo say v2.2.** T1 (diff, one line) | **MINOR** — hygiene. | as of 2026-09-04.

**F8 — LEDGER entry `## 2026-08-31 — scar filed (Tower ground-truth, gauntlet arc); station 8 merge rule made explicit` has no body.** T1, LEDGER line 601 at `bd3c88b`; the scars themselves did land in SCAR-LEDGER.md (three 2026-08-31 paragraphs present). | **MINOR** — hygiene; the append-only record has a heading pointing at nothing. | as of `bd3c88b`.

**F9 — The project-knowledge copy of SCAR-LEDGER.md is stale against the repo.** T1: `/mnt/project/SCAR-LEDGER.md` lacks the three 2026-08-31 paragraphs (diff: 34 lines). The mantra skill (registry) is byte-identical to `skills/the-scar-ledger/SKILL.md` in the repo, so the recited creed is current; only the long catalogue loaded into Tour sessions is behind. | **MINOR** — hygiene; the repo is canonical and reachable. | as of 2026-09-04.

**F10 — estate-audit's two parked amendments remain unruled** (Q3). T1 | **MINOR** — both are one-line additions; this audit already practises them. | as of 2026-09-04.

**F11 — SUSPECTED — UNVERIFIED (T1 headings only): acp-brand-methodology (40,662 B, 48 headings) carries Parts 6 (Podcast), 7 (Landing Page), 8 (5-Year Maintenance) that no active front in memory or LEDGER exercises.** Interior not read this session; a dead-section ruling needs a full read against the live fronts. Ships as a lead, not a finding — no severity above MINOR on this evidence.

**F12 — Skill-copy geography in `acp-doctrine` has no rule.** T1: writing-style and foundry sit at repo root, scar-ledger under `skills/`. | **MINOR** — hygiene until the port lap (F6) makes it matter. | as of `bd3c88b`.

### CONFIRMATIONS OF RECORD (already ledgered, verified live)
- vibecode-foundry registry copy synced to the repo (Gate Zero + AUTONOMY + spine present in both) — closes the OPEN of the 2026-08-21 and 2026-09-02 LEDGER BATONs (T1).
- the-scar-ledger skill: repo and registry byte-identical (T1).
- 21.08 F6 (linkedin-engine's cross-reference mandate loads four monoliths, ~121 KB): the four files are unchanged in size since the census (T1 by reconciliation); the mandate itself not re-read.
- Foundry's own parked items (tokens-as-truth law; dashboard-export station field) still parked — no closing entry (T2).

---

## CONFLICT-MAP REFRESH (21.08 → 04.09)

| 21.08 item | Status today | Evidence |
|---|---|---|
| F2 stale identity (always-on pair) | PERSISTS, +1 sibling | Q5, T1 |
| F3 struck phrase (brand-methodology 81/243) | PERSISTS | F3, T1 |
| F4 writing-style ↔ tic-audit "conflict-managed" | UNCHANGED (both files byte-identical to census) | pull 9, T1 |
| F6 four-monolith load | UNCHANGED | pull 9, T1 |
| F1, F5 | UNKNOWN — report never filed | pull 8 gap |
| Registry copy of foundry stale | CLOSED | T1 |
| **New since 21.08:** Gate Zero, spine, station 9, AUTONOMY, "Edit surgically" — all landed in foundry/CLAUDE.md and are in the registry copy | NO NEW CONFLICT FOUND against the five fully-read skills; the other fourteen not re-read for it | T1, coverage-limited |
| **New since 21.08:** control-tower's dated triggers fired | NEW (F4) | T1 |
| **New since 21.08:** scar-ledger skill added (19th) | NEW, clean | T1 |

---

## VERDICT TABLE — per skill

Coverage key: FULL = read end to end this session; STRUCT = headings + size + greps + targeted lines.

| # | Skill | Bytes | Repo copy | Coverage | Verdict | Grounds (T1 unless noted) |
|---|---|---|---|---|---|---|
| 1 | acp-personal-context | 3,794 | none | FULL | **AMEND** | lines 24, 25, 27, 70, 108 contradict CLAUDE.md line 5 (F2). Merge with #2 is a Commander question, parked. |
| 2 | acp-companion-style | 6,208 | none | FULL | **AMEND** | lines 73, 116 (F2). "Topics & Context" (70–79) duplicates #1's identity block — merge candidate, parked. |
| 3 | acp-brand-methodology | 40,662 | none | STRUCT | **AMEND** | lines 81, 243 (F3). Parts 6–8 SUSPECTED dead (F11), unread. |
| 4 | acp-writing-style | 41,272 | root | STRUCT + repo diff | **KEEP** | body identical repo↔registry; title line only (F7). |
| 5 | ai-tic-audit | 27,886 | none | STRUCT | **KEEP** | self-versioned v1.2 with dated changelog; zero staleness markers; interior unread. |
| 6 | acp-linkedin-engine | 11,162 | none | STRUCT | **KEEP** | zero staleness markers; load-cost note stands (21.08 F6); interior unread. |
| 7 | company-outreach-engine | 16,918 | none | STRUCT | **KEEP** | zero staleness markers; job search active per BATON (T3); interior unread. |
| 8 | acp-project-pulse | 8,894 | none | STRUCT | **AMEND** | line 33 "as of March 2026" registry (F5); CLAUDE.md says "pending rewrite". |
| 9 | acp-dashboard-export | 8,435 | none | STRUCT | **KEEP** | v2, parser contract dated July 2026 (line 42); station-field schema change parked in LEDGER 2026-08-31 — not this audit's variable. |
| 10 | control-tower | 8,478 | none | FULL | **AMEND** | lines 40, 92, 93 (F4). Routing re-audit due by the skill's own trigger; role definition sound. |
| 11 | estate-audit | 15,395 | none | FULL | **AMEND** | two parked one-liners (F10); no version line to record rulings against. |
| 12 | polaris | 9,829 | none | STRUCT | **KEEP** | zero staleness markers; interior unread. |
| 13 | red-team-protocol | 19,170 | none | STRUCT | **KEEP** | v3.1.1, self-audited 2026-07-24 (line 10); Cold Sniper parked by its own rule; interior unread. |
| 14 | meta-prompt-architect | 11,421 | none | STRUCT | **KEEP** | v3; zero staleness markers; interior unread. |
| 15 | cyoa-conversion-engine | 20,209 | none | STRUCT | **KEEP** | dormant domain, zero staleness; usage UNMEASURED — RETIRE not proposable on this evidence. |
| 16 | solo-rpg-digitization | 7,142 | none | STRUCT | **KEEP** | same as #15. |
| 17 | the-letter-on-the-table | 30,621 | none | STRUCT | **KEEP** | living document; +4,734 B since census (Archaeology entry, Aug 2026); dated entries are its design, not staleness. |
| 18 | the-scar-ledger | 4,828 | `skills/` | FULL + repo diff | **KEEP** | byte-identical to repo; one scar pending append (below). |
| 19 | vibecode-foundry | 22,697 | root | STRUCT + repo diff + marker greps | **KEEP** | synced (trailing newline only); lives under `plugins/`, not `user/` — location noted, not graded. |

**RETIRE:** none. No skill could be retired on this evidence — usage data is UNMEASURED and two dormant-domain skills (15, 16) show no defect. **MERGE:** none ruled; one candidate (#1+#2) parked for the Commander.

---

## G3 COUNTER-PASS

- **Hindsight bias:** F4 and F6 checked; both reclassify as due maintenance / parked-still-parked, not misses. F1 judges present state.
- **Absence-of-evidence:** Q1's "not run" rests on T1 (registry unchanged) for the registry and on T2 LEDGER silence for the Hands side — the second half is exactly the rake the rule names. Downgraded in place: "not run on the registry (T1); locally unknown (UNMEASURED)". Q2 stays UNMEASURED rather than inferred.
- **Flattery gradient:** every KEEP on a STRUCT-coverage skill is labelled "interior unread". The 21.08 validator convicted the prior report of praising unread files; this table does not repeat it. The scar-ledger and foundry "synced" claims are diff-grade, earned.
- **Selection bias:** the staleness grep favours skills that carry dates and model names — it structurally cannot see a stale *rule* written without a date. Fourteen interiors could hide one. Stated in coverage; not cured.
- **Rabbit check on the slate:** slate 1 is filing (shipping the record); slate 2 is the ratified hotfix (shipping a fix); slate 3 is a read-only measurement the precedence rule cannot be written without. The control-tower re-audit, the pulse rewrite, and the merge question are parked — meta-work is named, not smuggled.
- **Self-conviction, owned:** the auditor ran a cross-reference regex that generated its own false positives; caught on read, binned before any claim. Not a ledgered error (nothing was stated), but the shape is Lesson I — a smooth-looking output that was residue of a bad tokeniser.

## G4 OUTCOMES & COST

- **Outcomes:** shipped state on this front since 21.08 — 0 skill edits, 0 audit reports filed, 1 registry sync (foundry). Client/user signal: n/a. Career pipeline: UNMEASURED here (BATON says no live pipeline, T3).
- **Cost:** 1 Tower session, 15 tool laps, 0 Hands laps, 0 Commander hours beyond reading — at DRAFT-COMPLETE. The 21.08 arc cost: 1 authoring session + 1 hostile-validation session + 1 tribunal, and produced 0 committed bytes — that ratio is finding F1 in cost form.

---

## VERDICT

The estate is structurally healthy and operationally unfiled: nineteen skills, zero broken ones found where read, three of them under version control, one ratified fix and one confirmed audit sitting unfiled for fourteen days, and the two skills every session loads first still describing a man who does not exist.

## ACTION SLATE (max 3)

1. **File the record** — the 21.08 report (from disk if the Hands key ever ran; else from the authoring chat, Commander-exported), this report, two KPI rows, one LEDGER entry, and the ratified scar (below) — owner: **Hands**, doc-only lap on `acp-doctrine` main — trigger: Commander's word on this slate. (KEY-A.)
2. **Fire the 21.08 hotfix** (F2 identity lines in #1 and #2; F3 lines 81/243 in #3) on the repo/Code copies, then Commander pastes to the registry — owner: **Hands**, then **Commander** — trigger: after slate 1 confirms whether the key exists on disk; if not, the Tower re-authors it from F2/F3 above.
3. **Measure the Code side** — census of `.claude/skills/` (names, sizes, `sha256sum` against the registry figures above, load precedence observed in a live `/skills` listing), and the AgentShield scan on a COPY — owner: **Hands** — trigger: same session as slate 1 or the next Code session, read-only. (KEY-B.)

**PARKED (named):** control-tower routing re-audit via Polaris (F4 — Tower session, its own brief) · project-pulse registry rewrite (F5) · skills port to `acp-doctrine` + geography rule (F6, F12) · precedence line for root CLAUDE.md (drafted in the session, red-teamed, install blocked on slate 3) · #1+#2 merge question (Commander) · estate-audit two amendments + a version line (F10) · writing-style title sync (F7) · LEDGER 2026-08-31 empty body (F8) · project-knowledge SCAR-LEDGER refresh (F9) · brand-methodology Parts 6–8 read (F11) · dashboard-export station field (foundry parked item).

## KPI ROW (drafted)

`| 2026-09-04 | Skill estate (standard) | UNMEASURED (no PRs in scope; doctrine is doc-only-to-main) | n/a | 1 self-owned (G0 budget declared after pulls began) + 1 self-caught unstated / 16 laps | 0 | 0 | 19 skills, 3 in git, 1 registry sync since 21.08, 0 edits | n/a | root-as-repo question (LEDGER 2026-08-06 backlog), 29d, T2; 21.08 hotfix key, 14d | 11 (this audit's parked list; estate-wide UNMEASURED) | 1 Tower session, 16 laps, 0 Hands, Fable 5.1 |`
— status: DRAFT-COMPLETE, awaiting Hands commit for RECORD-COMPLETE.

**SELF-APPLICATION:** G0 passed — scope inherited from the sealed BATON, budget declared before findings were drafted (STANDARD), but declared *after* pulls 1–7 had begun: a sequencing defect, owned. G1 passed with one declared degradation (api.github.com) and one T3 dependency (the 21.08 record). G2 passed — every finding carries tier, cited severity, anchor; one SUSPECTED withheld. G3 passed (above). G4 passed with two UNMEASURED. G5 this document. **Weakest gate: G1 — coverage.** Five of nineteen interiors read; fourteen KEEPs are structural, not textual, and a stale rule with no date on it would have walked straight past pull 10. The next Tower that opens a STRUCT-coverage skill in full may downgrade a KEEP, and that would be this audit working, not failing.

**TRIBUNAL (Commander-ordered, post-delivery — red-team-protocol, full):** AMBER. Amendments applied in this file: (a) byte-reconciliation downgraded from "every file identical" to "sum identical; per-file for five" — the sum cannot exclude a cancelling pair; (b) "unrecoverable" downgraded to "not recovered in four searches"; (c) KPI oldest-open-ruling corrected to the 29-day root-as-repo question (T2), debt count relabelled as this audit's parked list, Tower error count made consistent with the self-application statement; (d) KEY-A step 7 rewritten without process substitution (the auditor's own shell threw `"(" unexpected` on that construct this session); (e) KEY-B given an explicit maintainer command. Lesson I again, in a smaller costume: the reconciliation *felt* like per-file proof because the arithmetic was clean.

=== END AUDIT ===

---

## APPENDIX A — Scar proposed in the BATON, cold-reviewed

Proposal: *"04.09 — Tower sequenced two sessions ('prep run 2', 'draft key v1.2') from a week-old ledger without pulling main; run 2 had already run under v1.2 and merged. Clade: unpulled ground. Caught by the Hands' ground-truth answers, not by the Tower."*

Cold review (this Tower did not author the error or the proposal): shape matches Lesson I exactly — stated from a stale record before pulling; caught by the Hands, the layer Lesson VII says catches premise errors. No new clade. Qualifies under the append ritual (self-owned in a BATON, contradicted by evidence in-session). **Recommend RATIFY**, filed under clade I as a fourth 2026-09 paragraph in SCAR-LEDGER.md; mantra unchanged.

## APPENDIX B — Precedence rule for root CLAUDE.md (draft; NOT installed)

Draft line for the `## Skills` section:
> A skill's canonical text is its copy in `acp-doctrine`. The Code folder `.claude/skills/` and the claude.ai registry are deployments: when copies disagree, the repo wins and the deployment is re-synced, never edited in place. A skill with no repo copy is not yet canonical — port it before amending it.

Tribunal on the draft (red-team-protocol, three lenses):
- **Architect:** the rule is the brand-kit pattern applied to skills — tokens-as-truth, deployments copied in. Structurally sound and consistent with the 2026-08-21 LEDGER precedent ("the repo copy is now canonical-and-current"). It creates a sync obligation with no mechanism beyond the Commander's paste; the rule should say so rather than imply automation. **AMBER.**
- **Sniper:** as written, the rule is unenforceable for 16 of 19 skills today (F6) — the last sentence turns every amendment into a port-first lap, which is correct but is a *policy change* the Commander has not ruled, and it front-loads the port the 2026-07-31 LEDGER parked. Also: "the repo wins" presumes Code loads the local folder over the registry — Q2 is UNMEASURED; if Code loads the registry copy, "re-sync the deployment" has no target the Commander can reach from Code. **RED until slate 3 reports.**
- **User Advocate:** ACP wants one sentence he can obey at 23:00 with a paste in hand. Three sentences with a port precondition is a rule he'll route around. Split it: install sentence one now (canonical = repo), make the port precondition a Commander ruling, not a rule. **AMBER.**
- **Synthesis:** do not install this session (per scope). Re-present after slate 3 with sentence two conditioned on the measured load order, and sentence three as a separate ruling.
