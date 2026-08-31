# IGNITION KEY — Gauntlet setup session, [project]
*Issued [date] by the Tower. Executor: [model], Claude Code, repo `[repo]`. Commander rulings carried: D1 = [bar choice: rulebook (option A) / reference frames (option B)] for run 1, [parked option] parked with a return ticket; D2 = Gate Zero rides along; D3 = freeze manifest as written below.*

MISSION: Install the gauntlet instruments on [project] as `gauntlet:*` npm scripts, run Gate Zero on the repo, commit FREEZE.md, and open ONE PR that passes the harness. Exit condition: every script below runs green on a clean checkout and produces a file under `gauntlet/out/`, Gate Zero table filled with proofs, PR open with harness green, LEDGER entry written. No pixel is polished in this session; that is the next key.

CONTEXT: You were born this morning. [project] is a [tech stack / one-line description], tokens "[token system name]" in `:root` with semantics via [token mechanism], IA_CANON.md at root with a banned-synonym list, a machine-gate harness on main ([lint/test/eval tools], `harness.yml`, ruleset requiring status checks). The gauntlet is a later phase where builder/critic sub-agents loop until a measurable bar is met. This session gives that phase its measuring instruments. Instruments are infrastructure and this session is labelled as such on purpose.

FILES: everything at HEAD of `main` (pull fresh; no snippet in this key is truth). Read first, quote one line each: `CLAUDE.md`, `LEDGER.md` (latest 3 entries), `IA_CANON.md`, `package.json`, `[tokens file, e.g. app/globals.css]`, `.github/workflows/harness.yml`, `[lint config file]`.

GROUND-TRUTH QUESTIONS (answer from files before any edit; an answer may kill parts of this brief):
1. Which routes/pages render the [N] in-scope surfaces ([surface 1], [surface 2], [surface 3])? Exact paths. Does [surface with no live URL, if any] have a URL, or only a download path? If download-only, screenshots need a fixture: say how.
2. Is there already any Playwright, axe, Lighthouse, or stylelint dependency in `package.json`? If yes, reuse; do not duplicate.
3. Where do user-facing strings live (components, a strings file, prompts)? The vocab grep must target user-facing strings, not code identifiers or prompts.
4. Does any route call a paid API without a rate limit? Quote the handler. Is `maxDuration` set? Is there any per-IP or per-session throttle?
5. Do the tokens exist as CSS custom properties readable from `getComputedStyle`, or only as framework theme names? This decides how the computed-style dump compares.
6. Does rendering [primary surface] require a live API call, or can a fixture be rendered from stored data? If no fixture exists, creating one (from an existing run output, scrubbed) is IN scope: the instruments must not burn API money to take a screenshot.

PHYSICS (non-negotiable):
- No screenshot before `document.fonts.ready` resolves. Fixed viewports [mobile viewport, e.g. 390×844] and [desktop viewport, e.g. 1280×800]. Fixed states: top; scrolled to [an anchor]; `prefers-reduced-motion: reduce`; JavaScript disabled.
- Instruments read, never write, app files. They output only to `gauntlet/out/` (gitignored except a `.gitkeep`).
- No new dependency beyond: `@playwright/test`, `pixelmatch` + `pngjs`, `@axe-core/playwright`, `@lhci/cli`. If a fifth is needed, stop and report instead of adding it.
- The harness stays intact. `gauntlet:*` scripts are NOT added to `harness.yml` in this session (they run on demand). One exception below.
- Gate Zero checks may not require reading code to interpret: every proof is a toggle state, an instrument line, or a screenshot.

DO:
1. Branch `gauntlet/setup` from main.
2. Fixture: a stored, scrubbed dataset so [primary surface] and [export/output surface, if any] render offline. Document how it is loaded (env flag or route param), and make sure production behaviour is untouched when the flag is absent.
3. `gauntlet:shots` — Playwright script producing PNGs for each in-scope surface × viewport × state into `gauntlet/out/shots/`, named `<surface>__<viewport>__<state>.png`.
4. `gauntlet:diff` — pixelmatch between `gauntlet/out/shots/` and `gauntlet/baseline/` (same names), per file, writing `gauntlet/out/diff.json` with mismatch % per image and a diff PNG. If baseline is missing, copy current shots to baseline and say so. Support a region-mask JSON (may be empty for now).
5. `gauntlet:styles` — Playwright script dumping computed colour, background-colour, border-colour, font-family, font-size, font-weight, line-height, and the four margins/paddings for every element in the in-scope surfaces; compare each value against the token values resolved from `[tokens file]`; output `gauntlet/out/styles.json` with a list of UNLISTED values (value, selector path, count). Tolerate rounding on sub-pixel line-heights; say what tolerance you used.
6. `gauntlet:a11y` — axe on each surface × viewport; output `gauntlet/out/a11y.json`; also list every text node whose contrast is below 4.5:1 (3:1 for ≥ 24px or bold ≥ 19px), with the computed ratio.
7. `gauntlet:layout` — script flagging horizontal overflow (`scrollWidth > clientWidth` on document and on any element) and overlapping text bounding boxes, per surface × viewport × state; output `gauntlet/out/layout.json`.
8. `gauntlet:vocab` — grep of the banned-synonym list from `IA_CANON.md` against the user-facing string locations found in Q3; output `gauntlet/out/vocab.json` with file, line, term. Zero hits expected on main; if there are hits, list them, do not fix them.
9. `gauntlet:perf` — Lighthouse CI on [primary surface] and [export/output surface, if any], desktop + mobile, JSON to `gauntlet/out/lhci/`. Record the four scores as the baseline in the ledger.
10. `gauntlet:all` — runs 3 to 9 in order and writes `gauntlet/out/SUMMARY.md`: one table, one row per instrument, columns = instrument / files produced / headline number. A non-coder reads this table and nothing else.
11. `gauntlet/README.md` — one page: what each script does, how to read SUMMARY.md, how to set the baseline, how to add a mask region. Plain language, no code snippets beyond the command lines.
12. `gauntlet/baseline/` — commit the cycle-0 baseline shots of main as they are today. This is the "before".
13. FREEZE.md at repo root, verbatim:
    ```
    FREEZE — Gauntlet run [N] (opened [date])
    IN: [surface 1], [surface 2] (all states), [surface 3]. [token system name] only.
    OUT: [engine paths, e.g. lib/, app/api/], prompts, [any other explicitly out-of-scope feature], IA_CANON strings beyond banned-synonym fixes, any new feature.
    DEFECT: any item failing the gauntlet checklist. Fixing broken is always legal.
    THAW: gauntlet report certified by the Tower.
    PARKED: [parked option, e.g. reference frames per surface, pixel-diff vs reference] — return ticket for run [N+1].
    ```
14. GATE ZERO — fill this table in the LEDGER entry, one proof each:
    | # | Check | [project] status | Proof |
    |---|---|---|---|
    | 1 | RLS | [status, e.g. N/A if no database] | one line |
    | 2 | Secrets server-side, secret scanning on | verify GitHub secret scanning setting on the public repo; confirm the key lives only in [hosting platform] env | setting screenshot or API line; `git log -p` grep for the key prefix = 0 |
    | 3 | Wallet guard ([hosting platform] spend limit) | COMMANDER ACTION: this is a billing toggle, the executor cannot flip it. Write the exact path in [hosting platform] settings for ACP to flip it and mark PENDING COMMANDER | path |
    | 4 | Input discipline | name the escaping mechanism for text input and screenshot handling; confirm no `dangerouslySetInnerHTML` outside [the relevant renderer, if any], and if it uses it, name the sanitiser | grep lines |
    | 5 | Paid endpoint metered | if Q4 says no rate limit: add a per-IP limit on [the paid route], and PROVE it with a screenshot of the 429. This is the one engine-adjacent edit allowed, because Gate Zero outranks the freeze. Add ONE test that the limiter returns 429 past the threshold; this test joins the harness. | 429 screenshot + test green |
    | 6 | Server-side auth | [status, e.g. N/A if single operator, no accounts] | one line |
    | 7 | Business-data flag | [status — confirm what, if anything, persists beyond the request] | grep for fs writes / storage calls = 0 |
    Security line: list the security implications of this session's changes and the automated check proving each ("none, instruments are read-only and gitignored" is legal if true; the limiter is not none).
15. Run `gauntlet:all` on the branch. Fix instrument bugs only. Commit each script separately: `gauntlet: add shots`, `gauntlet: add diff`, etc.
16. Open PR "gauntlet setup + Gate Zero". Harness must be green.
17. LEDGER.md entry: session name, commits, instrument table, Gate Zero table, baseline Lighthouse scores, cycle-0 timing (how long `gauntlet:all` took wall-clock, the number the caps will be set from), what is stale for the next worker, and the parked-option return ticket.

DO NOT:
- Polish, restyle, or "improve" any in-scope surface. Zero visual diff on this PR except what the limiter's UI error state requires, if any.
- Touch [the AI/engine config file] or [prompts file], or the model literal rule.
- Add `gauntlet:*` to `harness.yml` (except the limiter test, which is a normal test).
- Commit anything under `gauntlet/out/`.
- Send real user material to the API. Fixtures only.
- Install a dependency not on the list.

VERIFY (per item, receipts in the PR description):
- `npm run gauntlet:all` on a fresh clone of the branch: exits 0, SUMMARY.md exists, every `gauntlet/out/*.json` present, shots count = surfaces × viewports × states.
- `gauntlet:diff` against its own baseline reports 0.00% on every image (self-consistency check; if fonts or animations make it non-zero, mask or wait, and report the residual).
- `gauntlet:vocab` on main: report the count, expected 0.
- 429 screenshot attached; limiter test green in harness.
- Production URL behaviour unchanged with the fixture flag absent (one run on preview, cheapest path).
- Ground-truth Q1 to Q6 answered in the PR description before the first commit.

IF AN ANCHOR DOESN'T HIT EXACTLY ONCE: stop and report. Do not improvise.
IF A FIFTH DEPENDENCY SEEMS NEEDED: stop and report. Do not add it.
IF `gauntlet:all` TAKES OVER [cap, e.g. 20] MINUTES: stop, report the timing per instrument, and ask before optimising. That number is data the Tower needs, not a bug to hide.
