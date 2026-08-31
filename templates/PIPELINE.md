# PIPELINE — [project]
Opened: [date] · DS slot: [own canon | client system: name | client PDF → tokenised on date] · Brief: [POLARIS.md link]

NOW:  [station number — name — one line on what is in flight]
NEXT: [station number — name — one line]

| # | Station | Status | Evidence | Date |
|---|---|---|---|---|
| 0 | Research | TODO / DONE / SKIPPED: reason | [link/sha] | |
| 1 | Found the repo | | | |
| 2 | POLARIS brief | | | |
| 3 | IA canon | | | |
| 4 | Design-system slot | | | |
| 5 | Forge (Claude Design) | | | |
| 6 | Studio (Figma) — conditional | | | |
| 7 | Propagate tokens | | | |
| 8 | Build in sprints | | sprint list in LEDGER | |
| 9 | Gauntlet — conditional | | GAUNTLET_REPORT.md | |
| 10 | DESIGN GATE | | | |
| 11 | Gate Zero → ship | | production URL | |
| 12 | Polaris audit — conditional | | | |

Rules: a station is DONE only with evidence in the Evidence column. Mandatory stations (0,1,2,3,4,7,8,10,11) may not be SKIPPED. Conditional stations skipped carry a one-line reason. The Tower reads this file at session open and rules on NOW only. The Hands updates NOW/NEXT at session close, in the same commit as the LEDGER entry.
