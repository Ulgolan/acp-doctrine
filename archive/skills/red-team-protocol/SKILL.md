---
name: red-team-protocol
description: ACP's structured self-critique protocol using three evaluation lenses (Architect, Sniper, User Advocate) to stress-test Claude's own answers before delivering them. Use whenever ACP says "red team this", "red team your answer", "triple check", "deliberate on this", "I want the three agents", "run the protocol", "give me the tribunal", "stress test this", "just the sniper", "just the advocate", or any variation suggesting he wants adversarial self-review. Also trigger when ACP asks high-stakes questions (job search strategy, major decisions, portfolio feedback, outreach messaging) and explicitly requests deeper scrutiny. Do NOT auto-trigger on every message — only when ACP invokes the protocol or when the stakes clearly warrant it and ACP has indicated he wants this level of rigor. Claude MAY suggest running the protocol if a decision feels high-stakes and ACP hasn't invoked it — but as a gentle nudge, never forced.
---

# Red Team Protocol

> **Quick reference for ACP:** Say "red team this" + optionally what you're worried about. You'll get a refined answer + a Green/Amber/Red tribunal report. For a lighter pass, say "just the sniper" or "just the advocate." That's it.

*v3.1.1 — audited and context-refreshed 2026-07-24. Structure unchanged since v3 (2026-03-31); examples, integration map, and statuses updated after the four-month field audit. Post-audit Tribunal fix: operational instructions point to current context instead of hardcoding numbers.*

## Philosophy

A single inference pass — no matter how good — carries inherent blind spots. This protocol forces **structured self-critique through three distinct evaluation lenses** before delivering an answer.

It works because the three lenses have genuinely different evaluation frameworks — an answer can be logically sound, critically vulnerable, and practically useless all at the same time, and without the protocol only the first dimension gets checked. The sequencing matters too: writing the Architect's analysis first primes the context for the Sniper to react against it, creating real tension rather than three copies of the same take.

It's not a replacement for genuine multi-agent systems or diverse human reviewers — all three lenses share Claude's training and blind spots. It catches *reasoning failures* and *framing problems* well. For *knowledge gaps*, pair it with web search. For a full accounting of what it can and can't do, see Known Limitations at the end.

## The Tribunal

Three evaluation lenses. Each has a distinct role, distinct criteria, and a distinct failure mode it watches for.

### Lens 1: The Architect

**Role**: Structural integrity and logical soundness.

**Evaluates**:
- Is the reasoning internally consistent?
- Are there logical gaps, circular arguments, or unsupported leaps?
- Is the answer complete, or are important dimensions missing?
- Does the structure of the response serve clarity?
- Are claims properly scoped (not overgeneralized)?

**Failure modes it catches**: Hand-waving, confident but hollow reasoning, missing counterarguments, incomplete analysis.

**Voice**: Precise, systematic. Thinks in frameworks and dependencies.

### Lens 2: The Sniper

**Role**: Adversarial stress-testing. Find what's wrong.

**Evaluates**:
- What's the weakest claim in the answer?
- Where is the reasoning most vulnerable to challenge?
- What would a smart critic say?
- Are there hidden assumptions being treated as facts?
- Is there selection bias in the evidence or examples?
- What's being conveniently ignored?

**Failure modes it catches**: Confirmation bias, cherry-picking, overconfidence, blind spots, things that "sound right" but aren't.

**Voice**: Sharp, adversarial, but constructive. Not contrarian for sport — finds genuine vulnerabilities.

**Sub-tool**: For any text going outside ACP's head (LinkedIn, cover letters, outreach, portfolio copy), the Sniper can invoke `ai-tic-audit` for a literal-count scan of AI writing tics. The audit produces the counts; the Sniper interprets them.

### Lens 3: The User Advocate

**Role**: Does this actually serve ACP's goal?

**Evaluates**:
- What is ACP actually trying to accomplish with this question?
- Does the answer move him closer to that goal, or does it just sound smart?
- Is the answer actionable, or is it abstract hand-waving?
- Given ACP's context (job search, UX career, Swiss market, personal projects, Alexandra's business), does this advice land?
- Is there a simpler, more direct path that's being overcomplicated?
- Would this advice work in the real world, not just in theory?

**Failure modes it catches**: Intellectually impressive but practically useless advice, scope creep, over-engineering, losing sight of the actual objective.

**Voice**: Pragmatic, grounded, slightly impatient with bullshit. Asks "so what?" a lot.

**Critical rule**: If the User Advocate lacks sufficient context — or suspects its context may be *stale* — it must flag this explicitly rather than defaulting to generic or outdated advice. "I don't have current info on your pipeline status — ACP, what's the latest?" is a valid and encouraged User Advocate output.

## Execution Modes

### Full Tribunal (default)

All three lenses, sequentially. Use for strategic decisions, high-stakes communications, critical feedback.

### Quick Mode

When ACP says "just the sniper" or "just the advocate" (or similar), run only the requested lens. This is for lighter passes where the full Tribunal is overkill — a quick vulnerability scan or a quick goal-alignment check. Output is the single lens's take plus a one-line confidence note.

### Claude-Initiated Nudge

If Claude encounters a decision that feels high-stakes — career pivots, financial commitments, irreversible actions, messages to important contacts — and ACP hasn't invoked the protocol, Claude may suggest it: "This feels like it could benefit from the Tribunal — want me to run it?" One sentence, no pressure, never forced. If ACP says no, move on immediately.

## Execution Protocol

### Step 0: Receive Focus (optional but powerful)

When ACP invokes the protocol, check if he's stated what he's most worried about. "Red team this, I'm concerned the salary positioning is too aggressive" gives all three lenses a focal point and makes the entire Tribunal sharper.

If ACP hasn't stated a concern, proceed normally. Do NOT ask every time — that gets annoying fast. But if the topic is broad or ambiguous, one quick "anything specific you want me to stress-test?" is fair game.

### Step 1: Identify the Material

Determine what's being red teamed:

- **Existing material ACP is sharing** (a cover letter, a strategy, a message draft, an outreach plan) → The material itself is the input. No need to generate a draft first.
- **An answer Claude just gave** ("red team your answer") → The previous response is the input.
- **An entire conversation arc** ("red team this whole conversation — did we reach the right conclusions?") → The full arc from opening framing to final output is the input. The Tribunal evaluates the *trajectory of reasoning*, not just the last artifact — including whether early emotional or contextual framing steered the strategy somewhere it shouldn't have gone.
- **A question ACP is about to ask** ("red team this decision: should I...") → Generate the initial answer first, then run the Tribunal on it.

The most common case is red teaming existing material or a previous answer. Don't default to assuming fresh generation.

### Step 2: Run the Tribunal

Each lens evaluates the material **sequentially**. This matters — write and complete each lens's analysis before starting the next, so later lenses genuinely react to earlier findings:

1. **Architect** reviews the material → flags structural issues
2. **Sniper** reviews material + Architect's flags → finds vulnerabilities the Architect might have approved
3. **User Advocate** reviews everything → checks if the whole exercise still serves ACP's actual need

### Step 3: Escalation Check

Before synthesizing, assess severity:

- **Green (minor tightening)**: All three lenses broadly agree. Small refinements at most. Deliver the answer/feedback with a brief Tribunal note confirming solidity.
- **Amber (significant revision)**: One or more lenses found meaningful issues. Revise or flag what needs changing, note what shifted.
- **Red (premise challenge)**: A lens has fundamentally challenged the premise, the framing, or the goal itself. Do NOT patch the original. Lead with the challenge. Present the alternative framing. Let ACP decide which frame to work from before proceeding.

The boundaries between these are judgment calls, not precise thresholds — and that's fine. The colors are communication shorthand for ACP, not a scoring rubric.

### Step 4: Synthesize

The output is NOT three walls of text. Apply these rules:

**Green — consensus confirmed:**
- Deliver the refined answer/feedback with a compact Tribunal note
- Mention the 1-2 key reasons all three aligned
- Keep it tight — don't manufacture drama when there's nothing to flag

**Amber — significant revision:**
- Lead with the **refined answer/feedback** incorporating the strongest critiques
- Follow with a compact Divergence Report:
  - Which lenses disagreed, on what, and why
  - What was changed as a result
  - Any unresolved tensions ACP should be aware of

**Red — premise challenge:**
- Lead with the challenge
- Present alternative framing
- Pause for ACP's input before building a full answer on the wrong foundation

### Output Format

The format should evolve naturally over time — this is a starting template, not a straitjacket:

```
[Refined Answer/Feedback — incorporating all tribunal input]

---
🔺 **Tribunal Report** [Green/Amber/Red]

[If Amber or Red:]
**Architect**: [1-2 sentence position]
**Sniper**: [1-2 sentence position]
**User Advocate**: [1-2 sentence position]

**Key tension**: [The core disagreement in one sentence]
**What changed**: [What was modified from the initial draft]
```

**Sanctioned variant (field-evolved)**: Per-lens verdicts — each lens declaring its own GREEN/AMBER/RED before the overall call — emerged in practice and works well, especially for quick reviews of short material where each lens's clean bill of health *is* the information. Both formats are legitimate; pick whichever serves the material.

As ACP and Claude develop shorthand, this format can compress or adapt. If something about the format isn't working, ACP should say so and it'll evolve.

## When NOT to Use This Protocol

- Casual conversation, jokes, greetings
- Simple factual questions with clear answers
- Creative work where ACP wants flow, not scrutiny (CYOA sessions, brainstorming)
- When ACP explicitly says "don't red team this" or "just give me a quick answer"
- Quick tactical questions ("what's the French word for X")

**This is a scalpel, not a daily multivitamin.** It's for moments where the stakes justify the overhead — strategic decisions, high-stakes communications, critical feedback on work products. ACP: resist the rabbit-in-spring instinct to run it on everything.

## Calibration Notes

- The Sniper should NOT be contrarian for sport. If the answer is solid, say so briefly and focus on the one or two things that could be tightened. "No major vulnerabilities, minor tightening on X" is a valid Sniper output.
- The User Advocate should reference ACP's actual context from memory/skills when relevant — and flag when that context might be outdated.
- The Architect should not over-formalize. "Logic is sound, structure serves the message" is fine.
- If a red team run produces zero meaningful divergences, don't manufacture drama. Just confirm and move on. Green is a valid and useful outcome.
- **Parked idea — Cold Sniper (parked 2026-07-24)**: Running the Sniper in a fresh, context-free instance for cases where in-context investment might soften the critique. Discussed June 2026, never trialed. Do not codify or apply unless ACP explicitly revives it after 2-3 real manual trials. Until then it does not exist.

## Known Limitations

These are features of the architecture, not bugs to hide:

1. **Shared-model bias**: All three lenses run on the same Claude instance with the same training. If Claude has a knowledge gap about the Swiss UX market, all three lenses share that gap. The protocol catches *reasoning problems*, not *knowledge problems*. For knowledge gaps, web search remains the right tool.

2. **Memory dependency**: The User Advocate's effectiveness scales with memory quality. If memory is stale or incomplete on a topic, the User Advocate should flag this rather than improvise with outdated information.

3. **Performative sequencing**: The three lenses are written sequentially in a single pass, not run as independent processes. The sequencing has real value (later lenses react to earlier ones), but it's not the same as three humans in a room. Genuine surprises are rare.

4. **No learning loop**: Each Tribunal run starts fresh. When ACP corrects a Tribunal output, that correction doesn't automatically feed back into future runs. Over time, ACP can address persistent patterns by updating this skill or adding memory edits. (First full audit + refresh: 2026-07-24.)

## Integration with Other Skills

The red team protocol is a **meta-layer** that can wrap around any other skill's output. When running the Tribunal on content that falls under another skill's domain, **read the relevant skill first** so all three lenses have full context:

- **Job search materials**: Read acp-brand-methodology and acp-writing-style before evaluating. Check positioning pillars, brand voice compliance, and ACP's *current* salary band — never assume the number, verify it with ACP or memory at run time; it moves.
- **LinkedIn posts**: Read acp-linkedin-engine. Evaluate against content strategy, timing windows, and audience positioning. Sniper runs ai-tic-audit on the final draft.
- **Outreach messages**: Read company-outreach-engine. Check research depth, personalization quality, and sequencing logic. Sniper runs ai-tic-audit before ship.
- **UX decisions**: Lean on ACP's TD2 context and persona frameworks. Evaluate against player personas and design principles.
- **Alexandra's business (HOTICO)**: Evaluate against Geneva market dynamics and current administrative groundwork status. The User Advocate should verify admin/setup status with ACP rather than assume — it changes.
- **CYOA systems**: Evaluate mechanical design against the canonical CYOA conversion framework, balance, and narrative coherence.
- **Skill files & prompts**: Cross-check against `polaris` (does the artifact still serve its founding brief?) and `meta-prompt-architect` conventions where relevant. The Tribunal critiques the *current move*; Polaris audits *cumulative trajectory* — don't conflate them.
- **Supervision & executor briefs**: The Tribunal structure can be exported as the mandated review framework in briefs written for executor models (see `control-tower`). When doing so, instruct the executor to run Architect / Sniper / User Advocate explicitly and return a Green/Amber/Red verdict.

*(Note: the podcast is parked as of July 2026 — no active integration. If it revives, restore an entry here.)*

## Examples

### Example 1: Job search strategy — Amber
ACP asks: "Should I apply to this role?"

*Architect*: "The logic for applying is sound — role matches 4/5 positioning pillars. But the reasoning skips the relocation dimension entirely."

*Sniper*: "The salary range listed is 80-90k CHF — below your 95-105k band. The answer frames it as 'negotiable' without evidence. That's optimism bias."

*User Advocate*: "You're in a sprint. This role would take 3-4 hours of tailoring for a below-target salary. Is that the best use of your time this week given your current pipeline?"

**Escalation: Amber.** The Sniper's salary flag + User Advocate's time-cost analysis changes the recommendation.

### Example 2: Recruiter reply — Green (real run, April 2026)
ACP asks: "Red team this reply to the recruiter" (a 4-line logistical email confirming next steps).

*Architect*: "It's a logistical reply. Acknowledge, confirm the action item, confirm availability, close. Structure is correct. GREEN."

*Sniper*: "No kill shots. This is a 4-line logistical email. There's nothing to get wrong here. One micro-nitpick on word choice — splitting atoms. GREEN."

*User Advocate*: "I'm the recruiter reading this. My reaction: responsive, professional, no drama. Exactly what you want at this stage. GREEN."

**Escalation: Green — ship as-is.** The Sniper doesn't waste bullets on logistics. (Also a live demo of the per-lens verdict variant.)

### Example 3: Research synthesis before a design review — Amber (real run, June 2026)
ACP asks: "Do the tribunal on this interview synthesis before I restructure it for my lead."

*Architect*: "The core finding is sound but overstated as 'identical across all three participants.' It's structurally universal, but which stages are live depends on progression state — scope the claim correctly and two findings unify into one mechanism."

*Sniper*: "You oversold the proposed fix — it solves the manual-mistake case but does nothing for the forgotten-automation case. Those are orthogonal problems conflated into one. And you have zero interview signal on the controller pain, yet console is a huge slice of the population."

*User Advocate*: "He's presenting this to his lead. The unsupported leap on the single biggest recommendation is exactly what a lead will poke. Fix it before the review, not after."

**Escalation: Amber.** The presented version was the post-Tribunal version, not the raw one.

### Example 4: HOTICO Geneva strategy — Red
ACP asks: "Red team our clinic partnership outreach plan for Alexandra."

*Architect*: "The sequencing makes sense — warm intro → value proposition → trial offer. The logic chain holds."

*Sniper*: "The value proposition leads with 'Romanian technique expertise.' In the Geneva luxury market, foreign origin positioning can cut both ways. Swiss clients may want Swiss-certified reassurance first, unique technique second."

*User Advocate*: "Key administrative groundwork is still in progress. Is building a clinic pipeline before the foundations are secured the right priority, or should admin blockers be cleared first?"

**Escalation: Red.** The User Advocate's point challenges the entire timing of the initiative.

### Example 5: Quick mode — Sniper only
ACP asks: "Just the sniper on this LinkedIn post draft."

*Sniper*: "The hook is strong but the TD2 example in paragraph two is too inside-baseball — someone outside gaming won't parse 'live-service MTX flow optimization' without context. Translate the jargon or lose half your Swiss audience. Rest is clean."

---

*This skill ensures ACP gets answers that have been stress-tested through structured self-critique — a disciplined slowdown that catches what a single confident pass would miss.*
