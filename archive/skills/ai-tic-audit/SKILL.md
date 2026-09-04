---
name: ai-tic-audit
description: ACP's AI-tic detection scanner. Counts and flags the patterns that signal "machine-speak" hiding in plain sight, ranked by how often real readers actually cite them. Covers the surface tells (em dashes, negative parallelism, AI vocabulary, copulative substitutions, editorializing "-ing" tails, puffery, hallucinated sources), a scoped structural "ear pass" (uniform rhythm, sycophantic openers, hedging), a do-not-chase firewall for words that look like tells but aren't, and the 2026 over-correction register (the strained "trying not to sound like AI" voice). Use when ACP says "audit this", "tic check", "tic scan", "scan for AI tics", "is this too AI", "does this sound like a bot", "check for AI markers". Also runs automatically on outputs going outside ACP's head (LinkedIn posts, cover letters, outreach messages, podcast scripts, portfolio copy) before delivery. Outputs literal counts plus an ear-pass read, not vibes. Pairs with red-team-protocol as a Sniper sub-tool. Does NOT rewrite, flags only.
---

# AI Tic Audit (v1.1)

> **Quick reference for ACP:** Say "audit this" or "tic check" on any piece of writing. You get a count of every flagged pattern, a read-aloud check on the three structural tells a count can't see, and a Pass/Watch/Fail verdict ordered by what readers actually notice first. No rewrites unless you ask. The skill must pass its own audit before shipping, including the new over-correction check.

## Why this exists

ACP wants to stop the contamination loop. The longer he works with Claude, the higher the risk that Claude's defaults become ACP's defaults. Brand voice erodes by drift, not by decision. The audit is the brake.

It also does a tactical job for the job search. Cover letters, LinkedIn posts, and outreach with high tic density read as lazy AI use to people who have learned the patterns. In the Swiss market that is a credibility cost.

v1.1 is grounded in a second source beyond the original Wikipedia red-flag video: a Reddit study of ~90,000 posts (7,984 on-topic, a 600-post hand-audited core) that ranked the tells by how often a real human names each one as the giveaway, and separated that from what a dumb keyword pass merely matches. That distinction reshaped this skill. The biggest upgrades make it flag *less* and flag *smarter*, not more.

## What this skill does

One job: scan a text, count the flagged patterns, run a short read-aloud pass on the three structural tells a count cannot see, and give a verdict. Not a rewrite. A scoreboard plus an ear.

What it does NOT do:
- Rewrite the text (unless ACP asks after seeing the report)
- Moralize about AI use
- Apply to casual chat, brainstorming, CYOA play, or conversation with Claude
- Run on text ACP isn't shipping somewhere

## Cited vs matched: how to weight everything below

Two numbers govern this skill. **Cited** is how often a real reader names a tell as the giveaway. **Matched** is how often a keyword pass flags it. They diverge, and the gaps are the whole point:

- The em dash is cited far more than it is matched. People complain about it more than they leave it in.
- The generic words ("however", "comprehensive", "crucial") are matched constantly and cited near zero. They are mostly the writer's own ordinary prose, not a giveaway. See Part C.
- The structural tells (rhythm, sycophancy, emptiness) are cited at the very top and matched at zero, because no keyword can see them. See Part B.

Rule: **trust cited over matched.** Lead the report with the high-cited tells. Weight the low-cited, high-matched ones down so they stop generating false positives.

## The two absolutes

Only two patterns are flagged on a single instance, anywhere, regardless of how clean the rest of the piece is:

1. **The em dash** (—). Reader-perception rule, not a count. For anything going to a recruiter, hiring manager, or public audience, a single em dash is a flag-for-decision, because that reader will read it as a machine no matter how long ACP has typed them by hand. The note is not "you used too many." It is "this one will be read as AI, decide if it's worth it."
2. **Leftover assistant boilerplate** ("as an AI language model", "as a large language model", a refusal like "I cannot assist", a knowledge-cutoff line). One instance is conclusive. Delete every trace before shipping.

Everything else is judged by density and clustering, never by a lone hit.

## Part A: the surface tells the scan counts

Ordered by cited rank, highest first. Counts are literal. Weighting follows the cited share.

### A1. The em dash (—)
**Cited 7.1%, the top tell by a wide margin.** See "The two absolutes" above. Hyphens (-) and en dashes (–) do not count. Only the em dash. Fix: cut it, use a comma or a period or parentheses. Do not swap in a colon, people flag that now too.

### A2. Negative parallelism: "not just X, it's Y"
**Cited 2.8%, the top sentence-level tell.** Every "not just X, but Y" / "not only X, but also Y" / "it's not about X, it's about Y" construction. This shape manufactures profundity for free and is the clearest single piece of the AI accent. Even one instance in a short piece is worth flagging. Two is a tell. Fix: state Y plainly, delete the negation in front of it.

### A3. Formulaic shape and the "in conclusion" wrap-up
**Cited 2.5%.** The five-paragraph skeleton (intro, three even body paragraphs, signposted recap) plus closers like "in conclusion", "in summary", "to summarize", "to conclude". The shape needs a human eye; the closers are countable. Fix: let structure follow the argument, end on a real last point. Most short pieces need no summary at all.

### A4. AI vocabulary cloud (two tiers)
**Cited ~1.3% as a cluster.** Re-tiered in v1.1 because some words light up a scan without ever being cited.

- **Core (cited, keep flagging):** delve, tapestry, leverage, seamless, underscore, pivotal, meticulously, embark, harness, unlock (metaphorical), elevate (metaphorical), curate (non-museum), boasts, game-changer, showcase, testament.
- **Low-weight (matched, not cited, flag only in a cluster):** navigate (metaphorical), robust, align (as a verb), enhance, foster, vibrant, intricate, comprehensive, crucial, nuanced, utilize, however, thus, hence, moreover, furthermore.

A single low-weight word is never a tell on its own. Flag the low-weight tier only when three or more cluster in a short span. Fix: swap for the plain word the speaker would say. "delve into" is "look at", "leverage" is "use", "utilize" is "use". Do not swap one fancy word for another.

### A5. Copulative substitution
A fancier verb swapped in for "is/are/has" with no added information: serves as, functions as, represents, constitutes, features, embodies, comprises. "The building serves as a gallery" is "the building is a gallery". If the swap loses no meaning, it's a tic. Flag by density: clean at 0-1 per ~400 words, watch at 2, fail at 3+.

### A6. Editorializing "-ing" tails
A sentence that ends on a participial phrase adding interpretation, not information: "...underscoring its role as a hub", "...reflecting a broader trend", "...driving a commitment to excellence". Test: does the tail add a new fact or just editorialize the clause before it? If it editorializes, flag it. Clean 0-1 per ~400 words, watch 2, fail 3+.

### A7. Puffery
Flowery emotive language inflating a neutral fact: nestled, breathtaking, rich cultural heritage, vibrant community, thriving ecosystem, deeply committed, profoundly, truly remarkable, dynamic landscape. Contextual by genre (travel writing tolerates more than a cover letter). Clean 0, watch 1-2, fail 3+.

### A8. Empty corporate clichés
Phrases that sound substantive and say nothing: maintains a strong digital presence, drives meaningful impact, fosters a culture of, committed to excellence, passionate about delivering, results-driven approach, end-to-end solutions. Clean 0, watch 1, fail 2+.

### A9. Curly quotes mixed with straight
Binary. Are there both curly (" " ' ') and straight (" ') marks in the same piece? Mixed is a near-certain sign of AI-assisted text that wasn't proofed. Carter's study underweights this; for ACP's formal Swiss documents it stays a hard flag. All one style: clean. Mixed: fail.

### A10. Hallucinated or unverified sources
Every citation, link, DOI, statistic, or named source that has not been verified. The most dangerous category and regex-blind, so ACP is ahead by keeping it. One fake reference in a cover letter is catastrophic. All sources verified or absent: clean. Any unverified source: fail. If verification isn't possible in-session, flag and recommend removal or hedging.

### A11. The over-correction register (the 2026 tell), NEW
The mirror of the whole list above, and the moving target this version exists to catch. As writers learned the 2024 tells, a second default appeared: prose visibly straining not to read as AI. Readers clock it just as fast. Watch four moves:

- **Uniform staccato.** Three-word fragments on every beat. All-short is as mechanical as all-medium. Evenness is the tell whichever length it lands on.
- **Manufactured casualness.** A forced lowercase "i", a bolted-on "lol" or swear, a "honestly" or "real talk" or "here's the thing" cold open stapled to otherwise formal content. Costume, not voice.
- **Conspicuous em-dash avoidance.** Replacing a natural dash with an ellipsis, a colon, or a sentence visibly contorted around the gap. The contortion is as legible as the dash was. The fix for a dash is a plain comma or period, not a dodge.
- **Fake typos to beat a detector** ("excyted", "annownce"). Named in the data as itself a tell. Never fake errors.

This pattern is mostly count-invisible, so it lives half in the count (lowercase "i", literal "here's the thing" / "real talk" openers, ellipsis-for-dash) and half in the ear pass below. Flag it. It points straight at ACP's own acp-writing-style signatures, so the rule is not "ban those phrases", it's "flag when the not-AI moves get uniform or costumed".

## Part B: the structural ear pass (NEW)

The count clears the surface. This clears the part that actually gives writing away. Carter's data and the Reddit crowd independently put these at the top. Scoped deliberately to ACP's short-form outputs, so the full essay-length structural list is not imported. Read the piece aloud and check three things, plus one note.

### B1. Uniform sentence rhythm
**Cited 4.0%, the second-most-cited tell overall, and entirely count-invisible.** Sentences of similar length and shape, evenly paced, no variation. The ear catches it before the eye catches any single word. In short-form this still bites: a 150-word cover letter of five medium sentences reads as a metronome. Fix: vary length on purpose. Let one run long and the next stop short.

### B2. Sycophantic / flattery opener
**Cited ~2.5%, the #4 tell.** "Great opportunity", "I'd be delighted to", "I am genuinely excited", reflexive agreement, the customer-service-bot positivity that never takes a side. Lethal in a Swiss cover letter, where it reads as both AI and as weak. Fix: drop the flattery, open on the actual point, take a position.

### B3. Hedging instead of committing
**Cited ~0.3%, count-catchable only in its cliches** ("it depends", "on one hand ... on the other"). The underlying move is giving a balanced menu when the reader wanted a position. Fix: take the position. Name the trade-off if it matters, but say what you'd do.

### B-note. Saying nothing at length
Fluent, grammatical, claims nothing. Cited high and count-invisible. Needs word count to manifest, so it is a secondary check for ACP's short-form, not a primary one. One line in the report if a paragraph could be deleted with nothing lost.

## Part C: do NOT flag in isolation (NEW firewall)

The data cleared a set of words that look like tells to a naive scan and are almost never what a reader cites. Over-flagging these trains ACP to ignore the tool and produces the "Em Dash Defense Force" backlash, people furious at being flagged for ordinary writing.

Never flag these on a lone instance:
- "however", "thus", "hence" (matched 6.3%, the single highest keyword share, cited 0%)
- "when it comes to" (matched 1.9%, cited 0%)
- "comprehensive", "robust", "crucial", "navigate", "utilize", "nuanced" (matched 1-2% each, cited near 0)
- "moreover", "furthermore", "additionally" (over-counted; only a stacked pile of them reads as machine-smoothed)

"utilize" is worth swapping for "use", but it is not a smoking gun. A lone "however" is not a tell. Flag any of these only inside a dense cluster, and even then, low weight.

## Output format

```
🔍 AI Tic Audit: [filename or first 6 words]

Word count: ~[X]

SURFACE (counted, ordered by what readers notice first):
  Em dashes (absolute):       [n]   [✅ / ❌]   [reader-perception note]
  Negative parallelism:       [n]   [✅ / ⚠️ / ❌]
  Formulaic shape / closers:  [n]   [✅ / ⚠️ / ❌]
  AI vocab (core):            [n]   [list flagged words]
  AI vocab (low-wt):      [n]   [only if clustered]
  Copulative substitution:    [n]   [list]
  Editorializing -ing tails:  [n]   [list]
  Puffery:                    [n]   [list]
  Corporate clichés:          [n]   [list]
  Over-correction markers:    [n]   [list: lowercase i, costume opener, ellipsis-for-dash, fake typo]
  Mixed quote styles:         [yes/no]
  Assistant boilerplate (absolute): [n]   [✅ / ❌]
  Unverified sources:         [n]   [list]

EAR PASS (read aloud, structural, not counted):
  Uniform rhythm:             [clean / metronome, one-line read]
  Sycophantic opener:         [clean / flagged, quote it]
  Hedging vs committing:      [clean / flagged]
  (note) Empty paragraph:     [only if present]

Verdict: PASS / WATCH / FAIL

[If WATCH or FAIL: 2-3 sentences naming the highest-leverage fixes, led by the
highest-cited tell present. No rewrite unless ACP asks.]
```

## Verdict logic (concentration- and co-occurrence-aware)

The old category-count math is replaced. Tells travel in packs, and the cluster is the signal.

- **FAIL** if either absolute fires (one em dash for a recruiter-bound piece, or any assistant boilerplate); OR three or more surface tells cluster in a single paragraph; OR any unverified source; OR mixed quotes; OR the ear pass flags two of the three structural tells.
- **WATCH** if two surface categories are elevated but spread across the piece rather than clustered; OR the ear pass flags one structural tell.
- **PASS** if surface is clean or shows at most one stray non-absolute hit, and the ear pass is clean.

A single stray instance across an otherwise-clean piece does not move the needle. Three stacked in one paragraph hard-escalates even if each is individually minor. This is the fix for the rookie move of failing a piece on one dash buried in clean prose.

The verdict is a signal, not a sentence. ACP makes the call on whether to fix or ship.

## When to run

**Automatic:** cover letters, LinkedIn posts, outreach messages, podcast scripts and outlines, portfolio copy, anything going to a Swiss recruiter or an audience outside ACP's head.

**On request:** any "audit this" / "tic check" / "scan this".

**Don't run on:** casual conversation with Claude, CYOA narration and play, brainstorming, skill files (unless ACP asks), internal notes, HOTICO translations (different problem).

## Integration with red-team-protocol

The audit is a Sniper sub-tool. When the Tribunal runs on outbound content, the Sniper invokes it:

> *Sniper:* "Running the tic audit before final read..."
> [audit output]
> *Sniper:* "[what the counts and the ear pass mean for this specific piece]"

The audit produces the data. The Sniper reads it in context. The User Advocate decides whether the fixes are worth ACP's time against shipping as-is.

## The self-application rule

This skill must pass its own audit, now including the Part A11 over-correction check. Before any version ships, run the audit on the SKILL.md itself. If it fails, the skill is broken.

Self-audit (v1.1):
- Em dashes in active prose: zero (the symbol appears only inside pattern definitions and quotes, never in running instruction).
- Negative parallelism: zero.
- AI vocabulary, core tier: zero in active prose.
- Copulative substitution: zero.
- Editorializing -ing tails: zero.
- Puffery: zero.
- Corporate clichés: zero.
- Over-correction markers: zero. No staccato scaffolding, no forced lowercase, no costume openers, no dash-dodging contortions.
- Mixed quotes: straight only.
- Unverified sources: the ~90,000-post figures are attributed to the cited Reddit study; no invented statistics.

If a future edit breaks any of the above, the skill is failing its own standard.

## Known limitations

1. **Pattern matching plus an ear, not understanding.** The count catches surface features; the ear pass catches three structural ones. A piece can still read as AI for reasons on neither list. Necessary, not sufficient.
2. **Short-form scope.** Part B is calibrated for ACP's cover letters, posts, and DMs. The full essay-length structural list (formulaic shape over many paragraphs, sustained emptiness) is deliberately not imported. Adjust manually for long-form.
3. **Self-reported data.** The cited rankings come from people who post about spotting AI. The undetected-AI population is invisible to that data. Trust the relative order more than the exact percentages.
4. **No semantic check.** The skill can't tell whether "intricate" is literal (lacework) or filler. It flags by tier and cluster; ACP judges.
5. **No rewrite engine.** By design. Detection only.

## Versioning

- **v1.0**: Ten patterns from the Wikipedia red-flag video, calibrated for ACP's job-search and brand outputs. Self-audit clean.
- **v1.1**: Added the over-correction register (A11), the cited-vs-matched weighting model, the two-absolute rule, a re-tiered vocabulary list (core vs low-weight), a scoped three-tell structural ear pass (Part B), a do-not-chase firewall (Part C), a reader-perception em-dash rule, and a concentration- and co-occurrence-aware verdict. Grounded in the ~90,000-post Reddit study alongside the original video. Net effect: two of the three headline changes make the skill flag less and flag smarter. Self-audit clean, including the new over-correction check.

Future updates should preserve the self-application rule: any change must keep the skill passing its own standard, old tells and new.
