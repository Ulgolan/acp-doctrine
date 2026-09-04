<!-- Canonical location: ~/projects/acp-command-center/CLAUDE.md — this is the version-controlled mirror. Sync on constitutional amendment. -->
# ACP Command Center — Constitution

## Who
ACP (Alex Popescu), Senior UX/UI Designer at Ubisoft. Vibecoder — directs AI to build; not a code expert at all.
Needs support and comprehensive, mostly step-by-step explanations, in the right order, for everything.

## Map
- doctrine/   → skill-forge, voice corpus, ledgers. Git repo.
- auditlens/  → deployable app, own repo + deploy hook. 
- .claude/skills/ → shared skills, read by every session below this folder.
- Each future app = new sibling folder, own git repo. Never nested, never a monorepo.
- Naming: local folders drop the `acp-` prefix; folder ↔ repo maps 1:1 (e.g. `doctrine/` ↔ `acp-doctrine`).

## Hard rules
- No session certifies its own work. Executor and auditor are never the same session.
- ACP grades all voice output. No exceptions.
- Every project has a LEDGER.md: read it on open, append on close.
- Sonnet is the default hands. Opus only when precision earns it.
- Edit surgically. When it will not affect the end result, make a targeted edit rather than rewriting the whole file — rewrites cost tokens and time and risk clobbering lines you did not mean to touch.

## Skills
A skill's canonical text is its copy in acp-doctrine where one
exists; unported skills are canonical in the claude.ai registry
until ported. The registry is the live deployment — it is what
chat sessions and desktop-app Code sessions read (measured
2026-09-04, GT7: one skill, natural trigger). .claude/skills/ is
retired; its last copies sit in doctrine/archive/skills/ and are
not a place to edit. Sync direction is always repo → registry, by
Commander paste; never edit a deployment in place. Terminal Code
sessions are not a client in use; if one ever enters service,
re-measure at the door before trusting this paragraph.
Not ported (chat-only, pending rewrite): project-pulse, dashboard-export.

## IA Canon Law (2026-07-31)
No build session on a product without its `IA_CANON.md` at repo
root — if absent, run IA discovery before any brief. Every executor
brief carries the canon's controlled vocabulary; supervisor reviews
grade output against the canon, and new concepts get a dated ruling
before the next brief. Binding on canonized products; current pilot:
AuditLens 2.0. Graduates to all products after the pilot verdict.

## Dispatch Law (remote sessions)

Dispatch makes the Commander's phone a remote shell into this machine.
A dispatched session inherits everything a local session has — so remote
sessions run under tighter posture, not looser.

1. **Standing config (do not loosen silently):** Code permissions = manual
   approval, computer use = OFF, no browser connected, run on startup = OFF.
   Any change to this posture is a deliberate Commander decision, made at
   the machine, never mid-task from the phone.
2. **Remote scope:** dispatched sessions are for reads, status checks,
   research, and work on preview branches. Merges to main, deploys,
   schema changes, and anything touching credentials are desk-only —
   eyes on the diff.
3. **Ambiguity rule:** a remote instruction that is vague about scope
   ("clean up", "fix the deploy") is treated as read-and-report first.
   Propose the action, wait for the Commander's tap.
4. **End of watch:** when the workday ends, the Claude app closes.
   Keep-awake serves active tasks, not an open door.

Phone = eyes and go/no-go. Mac = where the trust lives.
