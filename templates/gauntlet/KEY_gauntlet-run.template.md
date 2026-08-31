# IGNITION KEY — Gauntlet RUN [N], [project] — v[version]
*Issued [date] by the Tower. v[version] fixes: [changelog since prior version, if any]. Orchestrator: [model, e.g. Opus], Claude Code, repo `[repo]`, sub-agents via the Task tool. Builders: [model, e.g. Sonnet]. Critics: [model], fresh spawn each cycle. Under GAUNTLET_KEY v[instrument version] and FREEZE.md (run [N]). Bar = [rulebook (option A) | reference frames (option B)]; [the other option] parked for run [N+1].*

MISSION: On branch `gauntlet/run-[N]`, drive the lanes below from their cycle-0 baseline to PASS on every critic row, or to the cap, and deliver `GAUNTLET_REPORT.md` plus a preview URL. Exit condition: report written, branch pushed, PR opened as DRAFT, no merge. Nothing else counts as done.

YOU ARE THE FOREMAN. You read, decompose, spawn, relay verdicts verbatim, compile. You do not edit app files and you do not grade screenshots. If you catch yourself doing either, stop: that is a sub-agent's seat.

READ FIRST, quote one line from each: `CLAUDE.md`, `LEDGER.md` (entry [prior setup-session date] and any later), `FREEZE.md`, `IA_CANON.md` (banned-synonym table), `gauntlet/README.md` (all of it, especially "before trusting a 0"), `[tokens file]` (token block).

PRE-FLIGHT (all [count], quoted, or stop with "PRE-FLIGHT FAIL: <which>"):
1. Reference exists: for this run the reference is [the rulebook (rows below) | reference frames] + tokens in `[tokens file]`. State this explicitly.
2. FREEZE.md present and unchanged since merge [sha].
3. `git branch --show-current` = `gauntlet/run-[N]`, created from `main` at HEAD.
4. Caps written into the report header before cycle 1 (see CAPS).
5. Gate Zero: PASS as of [PR reference]; this run is [scope description] only; confirm no file under [engine paths] will be touched.
6. ROUTING PROOF: spawn one trivial sub-agent instructed to report its own model name. If you can spawn [builder model], builders and critics run on it. If every spawn inherits [orchestrator model], say so in the report header and proceed; the usage line at the end becomes the routing finding for the ledger. Do not silently run [cap] [orchestrator-model] spawns.
7. SERVER GROUND TRUTH: quote from gauntlet/README.md how the instruments obtain a running app (dev server command, port, fixture URL) and confirm one manual `npm run gauntlet:shots` succeeds before cycle 0.

CYCLE 0 (mandatory, no edits): run `npm run gauntlet:all`, copy the SUMMARY table into the report as BASELINE, record wall-clock. Copy `gauntlet/out/shots/` to `gauntlet/lane-baseline/` (gitignored, local only): this is the LANE BASELINE. `gauntlet/baseline/` (the committed original) is never overwritten during this run; it serves only the report's before/after grid.

LANE BASELINE RULE: at the START of each lane, the previous lane's final shots and layout.json replace the lane baseline. Every critic diff row in a lane is measured against the lane baseline, never against the original, so a lane is only ever judged on its own changes. Expected to match: [baseline counts from cycle 0, e.g. N vocab / N contrast / N axe / N overflow / N overlap / 0 unlisted / LH ≥ N]. If it does not match, stop and report the drift before any spawn.

CAPS (from cycle-0 timing [seconds] per capture):
- Max cycles per lane: [N]. Max lanes: [N]. Max builder+critic spawns: [N]. Max wall-clock: [N] min from cycle 1. Expectation, stated so it is not misread: at roughly [N] min per cycle, the last lane may cap on wall-clock rather than on quality. A CAPPED lane with a reported delta is a legitimate outcome, not a failure.
- Any cap hit = lane CAPPED, record the delta, move on. Never "one more".

LANES, run SEQUENTIALLY in this order (all lanes may touch `[tokens file]`; one variable at a time — Law 2):

LANE 1 — [lane name, e.g. VOCABULARY]
  Baseline: [N] hits in `gauntlet/out/[instrument].json`.
  Scope: [what's in scope]. Hits inside [out-of-scope paths] are OUT by FREEZE.md: builder lists them under "Parked (gauntlet)" and does not touch them.
  Builder DO: [the fix pattern for this lane]; exact find/replace, anchor hits once.
  Critic rows: R1 [row definition]. R8 scope (diff --stat ⊆ [lane manifest]).

LANE 2 — [lane name, e.g. CONTRAST & A11Y]
  Baseline: [N] contrast failures, [N] axe violations in `gauntlet/out/a11y.json`.
  Physics: [the pairing/field laws for this project's tokens]. Fixes are token swaps only: change which token a rule uses, or add a darker step to an EXISTING ramp in `[tokens file]` if no current step passes. Never a raw hex in a component. Never a new hue.
  Builder DO: for each failing pair, pick the nearest passing token; if the only fix is a new token step, add it to the ramp with a comment "gauntlet run-[N], ratio X.XX" and use it. Resolve axe violations if they are markup-level (labels, roles, alt); if any requires a new component, park it.
  If a passing fix would visibly change the brand feel of a hero element, STOP that item, mark it "TASTE: Commander", and continue with the rest. Taste is not the builder's call.
  EXEMPTIONS: a flagged item may be marked EXEMPT only for disabled controls, placeholder text, or purely decorative text, and only with the WCAG 2.2 clause quoted. Exemptions are listed in the report. No quote, no exemption.
  Critic rows: R4 contrast failures = 0 after quoted exemptions (a11y.json). R4b axe violations = 0 or each remaining one listed with a "parked, needs component" reason. R2/R3 unlisted style values = 0 (styles.json). R9-LANE2: layout.json overflows and overlaps unchanged vs lane baseline (colour changes move pixels everywhere by design, so pixel-diff is NOT a row for this lane; it is reported only). R8 scope.

LANE 3 — [lane name, e.g. LAYOUT at [mobile viewport]]
  Baseline: [N] horizontal overflows, [N] text overlaps in `gauntlet/out/layout.json`; known culprits: [specific culprits].
  Physics: [the spacing/breakpoint laws for this project]. No `overflow: hidden` as a fix for text (that hides, it does not solve). Reduced-motion and no-JS states must survive.
  Builder DO: [the fix pattern for this lane]; re-run `gauntlet:layout` locally before commit.
  Critic rows: R5a horizontal overflows = 0 at [mobile viewport] and [desktop viewport], all states (layout.json). R5b text overlaps = 0. R5c layout.json at [desktop viewport] unchanged vs lane baseline (a mobile fix must not create desktop layout changes); desktop pixel-diff vs lane baseline REPORTED per shot, not thresholded, for the Commander's eye. R2/R3 unlisted = 0. R8 scope.

STANDING ROWS FOR EVERY LANE AND CYCLE:
  R7 Lighthouse: no score below baseline (report the four scores per surface). R2/R3 styles unlisted = 0. R8 scope ⊆ lane manifest. R9 (lanes touching pixels): pixel-diff vs LANE baseline = 0.00% for shots the lane declared it would not change; the builder declares expected-to-move shots in its commit message, the foreman passes that list to the critic. A lane with no fixed pixel target uses its own row (e.g. R9-LANE2) instead.

THE LOOP (per lane): builder edits and commits `gauntlet/<lane> c<N>: <one line>` → you run `npm run gauntlet:all` → spawn a FRESH critic with: SUMMARY.md, the relevant JSON files, the shots and diff PNGs, the lane's rows. Nothing else. → critic returns the table → all PASS = DONE; cap = CAPPED; else FAIL rows go to the next builder spawn VERBATIM as its DO list. You add no commentary.

BUILDER BRIEF (spawn text, per lane, fill the lane block in):
  "Born this morning. Lane <name> on branch gauntlet/run-[N]. Tokens in `[tokens file]` are truth; IA_CANON.md is law for strings. FILES: <lane manifest>. Read them fully. GROUND-TRUTH: quote the failing entries from <json> before editing. PHYSICS: <lane physics>. DO: <cycle 1: lane DO / later: critic FAIL rows verbatim>. DO NOT: touch anything outside FILES; new hue, hex, breakpoint, dependency, animation; anything under [engine paths], `gauntlet/`. 'While we're in there' goes to LEDGER.md under Parked (gauntlet). Anchors hit once or you stop. Before commit: build passes, `npm run gauntlet:<instrument for this lane>` locally, `git diff --stat` ⊆ FILES. Commit and stop. Do not grade your work."

CRITIC BRIEF (spawn text, fresh every cycle):
  "You are a blind critic. You receive SUMMARY.md, <json files>, <png paths>, and the rows below. You do not read source, commit messages, or builder output. Every row is PASS or FAIL with a number or a quoted instrument line. Banned words: wowed, looks good, matches, feels, close enough, mostly. No fixes proposed; name the gap and its size. Zero FAIL rows is a legal output. Output exactly: LANE / CYCLE / table / SUMMARY line with largest remaining gap."

REPORT (`GAUNTLET_REPORT.md` at repo root, on the branch): header (branch, preview URL, pre-flight quotes, caps, wall-clock used) · BASELINE table · per-lane cycle count and DONE/CAPPED · before/after shot pairs per lane at both viewports · every critic table verbatim in order · CAPPED deltas · TASTE: Commander items · Parked (gauntlet) · Deviations from this key · instrument versions · actual model usage per spawn.

THEN: push, open PR "gauntlet run [N]" as DRAFT, paste the BASELINE→FINAL table in the PR description with the preview URL. Stop. Do not merge, do not request review, do not summarise in chat beyond "report at <path>, preview at <url>".

STOP CONDITIONS: cycle-0 drift · instrument missing or erroring twice in a row · anchor miss · a builder proposing a new hue, hex, or dependency · wall-clock cap · anything requiring a file under [engine paths]. On stop: write what you have to the report, push, and end.
