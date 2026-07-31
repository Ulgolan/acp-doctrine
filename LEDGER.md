## 2026-07-24 — Setup session
Built the acp-command-center structure in ~/Documents, then moved the whole folder intact into ~/projects/acp-command-center (git repos traveled with it, none re-initialized). Wrote the root CLAUDE.md constitution (Who/Map/Hard rules/Skills). Installed five skills into .claude/skills/ (acp-writing-style, ai-tic-audit, control-tower, polaris, red-team-protocol) and fixed the acp-writing-style title label from v2.1 to v2.2 to match its existing changelog. Copied acp-writing-style into doctrine/ and made doctrine's first commit.

## 2026-07-31 — vibecode-foundry established + IA Canon installed (branch feat/ia-canon)
Step 0 found no on-disk vibecode-foundry anywhere in the workspace (.claude/skills/ or doctrine/); Tower ruled the registry copy (anthropic-skills:vibecode-foundry) is the sole existing instance and authorized the port with a handshake verification (description opener, title/distilled line, Part I/II structure, four spot anchors — all hit exactly once, 75 lines). Ported as-is to doctrine/vibecode-foundry/SKILL.md (commit 1). Installed the IA Canon feature per IA_CANON_SPEC.md v1.0: new "### IA Canon" section in Part I (five lifecycle moments + embedded six-point audit checklist) and the canon-lite template at doctrine/vibecode-foundry/IA_CANON.template.md (commit 2). §5 law lines output to the Commander as a paste-ready snippet (amended with a rollout clause scoping it to canonized products, pilot AuditLens 2.0); root CLAUDE.md not touched. .claude/skills/ installation of vibecode-foundry parked to the skills-recensement mission. Branch not merged — waits on Tower certification and the Commander's eye. No remote configured on doctrine/, so the branch sits locally rather than pushed.

**Interim Tower ruling (same date):** pass-with-conditions on section placement and template naming/location. Ordered IA_CANON_SPEC.md committed rather than left untracked — moved from doctrine/ root to doctrine/vibecode-foundry/IA_CANON_SPEC.md, colocated with the feature it specifies (commit 4). Flagged doctrine/'s missing remote as a priority item, explicitly out of this branch's exit condition.

**Commander's eye (same date):** v1.0 passed as-is. feat/ia-canon merged into main (merge commit d5a697b, `--no-ff`). Feature branch retained, not deleted — holds until the remote exists.

**Closed:** claude.ai copy of vibecode-foundry synced by Commander (2026-07-31) — registry and doctrine/vibecode-foundry/SKILL.md now match.

**Pending:**
- vibecode-foundry installation into .claude/skills/ — parked to the skills-recensement mission.
- **Priority:** doctrine/ has no remote. Create a private GitHub remote and push before more canon accumulates on this repo. Not part of this branch's exit condition — a standing action item.
