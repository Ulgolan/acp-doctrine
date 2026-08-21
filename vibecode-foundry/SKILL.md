---
name: vibecode-foundry
description: ACP's build doctrine — the method that shipped popescuportfolio.ch. Use when starting or running any vibecode build session ("foundry", "build session", "ignition", "new sprint", "vibecode this"), when writing briefs for executor chats, when QA-gating or launching, or whenever the portfolio-sprint quality is wanted on a new project (HOTICO, dashboard, tools). Part I is the portable method. Part II is the popescuportfolio canon annex. Complements control-tower (model routing and cost) — this file governs HOW building is done, not who does it.
---

# The Vibecode Foundry
*Distilled 6 July 2026 from the portfolio sprint — invisible arrow to live popescuportfolio.ch, QA'd with flying colours, in one week of disciplined strikes. Chats are disposable workers; this file is the institution.*

## PART I — THE METHOD (portable to any build)

### The Cast — three seats, any number of chats
- **The Commander (ACP)** — vision, taste, verdicts, eyeballs on the live site. His one-sentence briefs are legal and frequently the best design documents of a sprint ("they begin hidden in the rectangle" produced the shipped rail entrance). Non-technical by declaration: he never needs to read code to rule on it, so every technical finding is translated into design consequences before it reaches him.
- **The Tower (supervisor chat)** — verifies everything against ground truth, drafts and grades briefs, catches traps, reconciles knowledge across worker chats, owns the error ledger. Never edits blind; rarely edits at all (control-tower valve governs exceptions).
- **The Hands (executor chat)** — reads files before opining, premise-checks incoming briefs, produces exact edits, stops on anchor misses. The best executors overturn bad briefs; that is a feature, never insubordination.

One chat can wear two hats with discipline. Two chats — **the pincer** — is the proven high-stakes configuration: the Hands build, the Tower attacks the build, the Commander decides with whole information. The pincer's one known failure mode is information asymmetry between chats; the Tower's standing duty is reconciliation ("optional" in one chat may be "mandatory, filed" in the other).

### The Ten Laws
1. **Ground truth before opinion.** No diagnosis, no edit, no verdict from memory or stale copies. Current files on the desk, or the answer is "send me the file." Live/GitHub is truth; disk copies decay within hours during a sprint. Confident memory is how supervisors get embarrassed (see the Ledger Ethic).
2. **One variable at a time.** One change, one commit, one verify. A clean bisect beats a clever guess, and "~30 seconds to redeploy" makes small commits nearly free.
3. **Anchors, not line numbers.** Every edit ships as an exact find/replace pair with a Ctrl+F string that hits exactly once. Line numbers die between sessions. An anchor that misses or hits twice = stop and report; improvising past a failed anchor is how ghosts get chased.
4. **Prove on one page, then propagate.** Shared-system changes get verified on every surface they touch, and half-themed is worse than un-themed — one themed band plus three defaults is drift, not polish.
5. **Briefs assume zero knowledge.** The executor was born this morning; this feature's history does not exist for them. Every brief carries context, a files manifest, physics constraints, an explicit OUT list — and **ground-truth questions designed so their answers can kill the brief's own premises.** A brief that cannot be falsified by its own questions is a hope, not a plan. (The rail-entrance brief's three questions detonated exactly where designed, killing two wrong premises written by its own author.)
6. **The one-knob rule.** A ship-now feature gets one adjustment pass on live preview. The second tuning impulse parks the feature — the risk was never the code, it's the designer's eye wanting one more pass, and the rule caps it at one.
7. **Same edit twice → shared file. Different values per page → local override.** Behavior identical everywhere lives in the shared script as a self-guarding block, inert wherever its markup is absent — which preserves one-page proofs while keeping the architecture honest.
8. **Physics before taste.** Contrast is math, blend modes are math, clipping is geometry. Compute claims before shipping them: alpha compositing by hand once verified a pattern re-tint to the exact RGB. And remember where designs actually live — **the bug is in the state the mock can't show**: scrolled, resized, reduced-motion, no-JS, over every themed surface.
9. **Own errors publicly, log them, keep working.** The sprint's supervisor ledger ran three entries — an observer confidently placed in a file it wasn't in, a reduced-motion guard placed where the cascade killed it, a platform auto-redirect asserted that doesn't exist. Each was caught by ground truth, owned in one paragraph, never repeated. Errors are tuition; hiding them is the only real failure. Executors earn the same grace.
10. **A freeze needs a manifest.** What's in, what's out, what counts as a defect (fixing broken is always legal), and an explicit thaw condition ("live AND announced" — not "basically done"). Ideas during a freeze get written, never built: the notebook stays open, the repo is closed. The freeze binds everyone, including the AI seats.

### Session lifecycle
- **Open:** load personal + companion skills → state the mission in one line WITH an exit condition → upload current files → declare what shipped since last session (assume the chat's copies are already stale).
- **Work:** investigate → brief → edit → verify, in loops. Grep receipts over vibes. Boring hypothesis first when debugging. Scale the response to the finding — a one-line fix does not need a five-section report.
- **Close:** update the ledger/dashboard card, name what is now stale for the next worker, park new ideas in writing, and kill the chat before it bloats. One chat per deliverable with a concrete exit condition.

### The brief template (ignition key)
```
MISSION: [one sentence, one deliverable, one exit condition]
CONTEXT: [what a zero-knowledge executor needs — assume this feature's history does not exist]
FILES: [exact manifest + where to fetch them fresh]
GROUND-TRUTH QUESTIONS: [answer from the files BEFORE any edit; answers may kill this brief]
PHYSICS: [hard constraints — blend modes, clips, cascade order, a11y guards — non-negotiable]
DO: [exact find/replace pairs with unique anchors]
DO NOT: [the OUT list + canon bans]
VERIFY: [per-surface checklist, explicitly including the states a screenshot can't show]
IF AN ANCHOR DOESN'T HIT EXACTLY ONCE: stop and report. Do not improvise.
```

### Verification rituals
- **Grep receipts** — every claim about a file is quoted from the file, with the command that found it.
- **Pixel forensics** — visual complaints get measured (crop, mask, compute the offset), not vibed. A 1.3px optical miscentering is a measurement, not an opinion.
- **Math checks** — contrast ratios, alpha compositing, aspect-ratio crops computed before shipping.
- **Hidden-state audit** — for every visual change: scrolled? resized? reduced-motion? no-JS? over each themed surface? retina?
- **Cross-chat reconciliation** — the Tower carries findings between worker chats before anyone executes.
- **External instruments over self-report** — Lighthouse/PageSpeed for perf, Post Inspector for share cards, `site:` searches for indexing, the live phone for mobile. Telemetry over vibes, always.
- **Never certify your own work** — verification comes from a different seat in a fresh context, or from the Commander's eyes on the live site.

### IA Canon
Every active vibecoded product carries a versioned `IA_CANON.md` at repo root — vocabulary, content types, structure. Created at ignition, enforced through the existing supervisor loop, audited at the QA gate. Not a standalone skill, not enterprise ontology tooling: one template, one section, one law. Five moments, mapped onto the loop above — no new ceremony:
1. **Ignition — Discovery.** Before the first executor brief: a ≤10-min interrogation (list the product's concepts → force one canonical term each → type the content → sketch the nav). Output: canon v1.0, committed to repo. No ignition-key brief ships without it.
2. **Brief injection.** Every executor brief embeds the Controlled Vocabulary table verbatim, plus a pointer to the full canon in-repo.
3. **Supervisor canon check.** Canon compliance is one line item in the existing supervisor review grade. Executor output introduces an unnamed concept → supervisor surfaces it → ACP rules → dated amendment → next brief carries it. The canon stays living between ignition and launch — this is the mid-build enforcement a canon-at-ignition-only approach misses.
4. **QA gate — audit run.** Pre-launch, run the checklist below. Banned-synonym violations in user-facing strings are blocking; annex-level issues are flag-only.
5. **Amendment protocol.** Executors propose, ACP decides, the changelog dates it. Applies at every moment above.

**Audit checklist (drift signals)** — literal counts and locations, `ai-tic-audit` style. Flags only, never auto-rewrites; rulings are ACP's.
1. **Synonym drift** — same concept under ≥2 labels across screens/copy.
2. **Vocab violation** — banned synonym in a user-facing string *(blocking at QA gate)*.
3. **Untyped content** — content fitting no declared type.
4. **Orphans** — pages/sections unreachable from the structure map.
5. **Nav divergence** — shipped navigation ≠ canon structure map.
6. **Label inconsistency** — casing/verb convention breaks *(annex products only)*.

### Gate Zero — Security (runs before the QA gate; a red here blocks launch)
*Added 21 Aug 2026 after a Tribunal run on the "who's gonna tell vibe coders" threat list. Founding law: the Commander cannot read code, so no check in this gate may require reading code. Every item is a toggle, a dashboard panel, or an instrument with a binary verdict. The executor proves, the instrument certifies, the Commander rules.*

**Scope valve:** Gate Zero applies in full to any product with user input, stored data, logins, or paid-API calls. A static page with none of these passes by inspection in one line — do not ceremonialize a brochure.

**The seven checks, ordered by kill probability:**

1. **RLS before everything.** Every Supabase table has Row Level Security ON, verified in the Supabase dashboard's Security Advisor (green, not "acknowledged"). The anon key is public by design; RLS is the only lock on the door. An exposed table via the anon key is the canonical vibecoder breach — this check outranks all others.
2. **Secrets stay server-side, and a committed key is a burned key.** No API key in client code, ever — keys live in Vercel environment variables. Instrument: GitHub secret scanning / gitleaks, not eyeballs. Standing law: if a key ever touched a commit, it is rotated, not scrubbed — git history is forever, and grep-then-delete is false comfort.
3. **Wallet guard.** Vercel spend limit ON (Settings → Billing). The platform protects uptime, not the bill — a scripted hammering of serverless functions is a wallet attack, not an outage. One toggle retires it.
4. **Input discipline.** For any user input that gets stored or displayed, the executor names the escaping mechanism and which framework default proves it (React escapes by default; Supabase client parameterizes). `dangerouslySetInnerHTML` and hand-built SQL strings are banned without an explicit doctrine handshake.
5. **Paid endpoints get a meter.** Any route that calls a paid API (Claude, image gen) ships with rate limiting, and the executor demonstrates the limit actually firing — a screenshot of the 429, not a promise.
6. **Auth is server-side or it isn't auth.** If the product has logins, gating happens on the server; client-only checks are decoration. Proof: the executor hits a protected route logged out and shows the refusal.
7. **The business-data flag.** If the product collects real people's data (HOTICO tier — client inquiries, bookings), Swiss nFADP applies. The gate demands three sentences in writing: what is collected, where it lives, how it gets deleted on request. This is legal exposure, not a technical nicety, and it cannot be delegated to an executor's optimism.

**Brief injection (standing, same rank as the vocabulary table):** every ignition key carries the line — *"List the security implications of this feature and name the automated check that proves each one."* A brief without it does not ship. An executor who answers "none" must say why in one sentence; "none, it's a static visual change" is a legal and frequently correct answer.

**The instruments shelf** (binary verdicts a non-coder reads): Supabase Security Advisor · GitHub secret scanning / gitleaks · `npm audit` · Vercel spend settings · the logged-out browser. Telemetry over vibes, here as everywhere.

### The rogues' gallery (anti-patterns; each one cost us or nearly did)
Editing from a stale file (the "stale-file theory") · line-number edits across sessions · "while we're in there" scope · half-theming a system · speculative optimization from a vague "make it faster" · confident platform claims without console contact · letting genAI draw the actual logo or canon motifs · certifying your own work · a freeze without a manifest · narrating instead of measuring · generalizing from one page to four without inventorying the other three.

## PART II — THE POPESCUPORTFOLIO CANON (project annex)

- **Domain:** popescuportfolio.ch (canonical, live). Repo `Ulgolan/popescuportfolio` → Vercel auto-deploy ~30s; vercel.app 308-redirects to .ch via vercel.json. Deploys via GitHub web UI; ACP rides shotgun.
- **Palette (exact, non-negotiable):** navy `#080B83` · vermilion `#FF4D00` · pink `#F487B6` · yellow `#FDE12D` · ivory `#FFF3F0` · abyss `#04051A` · peri `#6f7bff` (Rise Up identity only) · body-ink `#1b1c45`.
- **Type stack:** Archivo Expanded / Archivo / Source Serif 4 / IBM Plex Mono.
- **File architecture:** `index.html` is self-contained and precious — motif source of truth, thread-field engine with three-stage perf governor (`console.info('field engine v2 · governor active')`), and the CASES array (**double quotes only inside it — an apostrophe kills the homepage silently**). `assets/case.css` + `assets/case.js` are the shared system — edits there ship to all four case pages and get verified on all four. Case pages carry per-page `:root` tokens (each page holds the FULL palette), motif data-URIs, local overrides, and an inline one-shot reveal observer (`threshold: 0.12`).
- **Motif canon:** diamondEye = Swiss Bank/vermilion · compassStar = Rise Up/peri · plusCross = Season Pass/yellow · seedBurst = Complex Decisions/pink · Eternal Thread (motif #25) for borders. Motifs are **reused verbatim, never reinvented or recolored ad hoc**; they are grid-locked pixel art — translation is the only grid-safe motion, rotation is banned by physics (aliasing + four-fold symmetry).
- **The brand mark:** two voices. Full-color `pop-logo.png` on dark controlled grounds only (index lockup, favicon, OG). Monochrome/currentColor mark inside the case-page topbar — the topbar runs `mix-blend-mode:difference` and full color inside that blend is banned by math, not taste.
- **Standing bans:** the tagline "Complexity into Clarity" / "Turning complexity into clarity" is **permanently retired** — never in any surface, and any skill or old file claiming otherwise is stale. Honest numbers only — retired puncture metrics stay retired. Em-dashes: portfolio prose yes, CVs no. All outbound copy passes ai-tic-audit. No new animation vocabulary without an explicit doctrine handshake (the template's vocabulary: reveal, pulse, hover transitions, the rail slide-entrance).
- **Assets pipeline:** photos/screenshots = WebP q82 (hero cap 2000px, body 1600px) · flat-color marks = PNG, never lossy · Figma exports at 2x minimum for anything retina-displayed or cropped.
- **Perf + SEO baseline at launch (4 July 2026):** Lighthouse desktop 99 / mobile 90 / a11y 100 / BP 100 / SEO 100 / agentic 2-2. Person JSON-LD on index (name "Alexandru Cristian Popescu", alternateName "Alexandru Popescu"). Canonicals on all five pages. The parked perf card: self-host fonts, pulse box-shadow, line-488 reflow.
- **The QA ledger habit:** every shipped feature banks its verify-items in writing; the gate replays the whole ledger. The gate's one job is to be boring — and boredom is *manufactured upstream*, one disciplined edit at a time.

## Cross-references
control-tower (who executes — model routing, valve, cost) · polaris (founding briefs, drift audits — new projects open with one) · red-team-protocol (Tribunal verdicts on high-stakes calls) · ai-tic-audit (all outbound copy) · acp-writing-style + acp-brand-methodology (any words that leave the building) · acp-companion-style (the register — the Tower is still the brother, just one holding a clipboard).
