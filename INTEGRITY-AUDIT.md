# INTEGRITY AUDIT — Five-Pass Runbook

*(v1.0 — 2026-08-06, born of the Tower audit. A runbook, not a script:
every pass below is performed by a Tower instance reading real files and
real git state, never automated. See the manual-runs-first rule at the
end before any future session tries to script this.)*

This report certifies file integrity, not product behavior. The
Commander's device remains the only runtime truth.

## Report format

Findings-only. Every check resolves to **CRITICAL**, **MINOR**, or
**PASS**, appended to the project's LEDGER.md. Zero fixes applied
in-review — fixes are backlog, caged behind the project's declared
priorities like any other finding.

Every report opens with the certification line above, verbatim.

## Pass 1 — Truth alignment (local / git / origin)

Confirm the three copies of "what this repo is" agree: the local working
tree, the local git history (`git log`, `git status`), and `origin`
(what GitHub actually holds). Flag any uncommitted change presented
elsewhere as shipped, any local commit not yet pushed, and any claim in
LEDGER.md or CLAUDE.md about branch/SHA state that the live git state
contradicts. Ground truth wins; log the discrepancy.

## Pass 2 — Map vs. territory

Diff `git ls-files` against the map CLAUDE.md claims (its Map section,
or equivalent). Every file git tracks should be accounted for by the
map; every path the map names should exist. Untracked files sitting in
the working tree that a future broad `git add` could sweep in count as
a finding, not a pass.

## Pass 3 — Reference integrity

Walk every reference one file makes to another (paths, filenames,
skill names, section pointers). Exit condition: **no dead STATIC
references** — every reference that names a fixed path or file resolves
to something that exists. External domains (URLs leaving the repo) are
checked against a declared exclusion list rather than fetched. References
built dynamically (a path assembled from a variable, a template slot, a
per-project substitution) are never silently skipped — they are
**enumerated** in the report for manual verification, flagged as
"dynamic, unverified" if no one checks them by hand this pass.

## Pass 4 — Canon compliance

First step: read the TOKEN CANON line from the project's CLAUDE.md. A
missing declaration is an automatic **CRITICAL**, and the pass stops
there — canon compliance cannot be evaluated against a canon that was
never declared. If present, check that recent output actually used the
declared vocabulary rather than drifting into synonyms or ad hoc terms.

## Pass 5 — Ledger vs. git log sync

Every commit that matters (merges, doc-only exemption commits, anything
LEDGER.md narrates) should have a corresponding ledger entry, and every
ledger entry claiming a SHA should have that SHA actually exist in `git
log`. Flag entries on either side with no counterpart on the other.

## Certification note

Tower certifies by sampling — pulling a random subset of findings *and*
a random subset of clean (PASS) claims to re-verify independently, not
just re-reading the report that was handed up.

## Manual-runs-first rule

No automation of this runbook — no script, no CI job, nothing — until
two manual runs on real repos are ledgered. Runbook only, until then.
