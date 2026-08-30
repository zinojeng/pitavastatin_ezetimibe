# Cross-session log — post-Gate-2 checkpoint: citation #35 (Huang PH 2022) — 2026-08-31

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Logged by: Research Director (`pit-eze-research-director`)

```text
[PROJECT]        pitavastatin-ezetimibe-evidence
[RUN]             2026-08-31-v1
[FROM]           Research Director
[TO]             90_CROSS-SESSION-LOG (control-plane record; PI-facing)
[TYPE]           STATUS_REPORT
[FINDING]        guideline-risk-intelligence's commits d5e5131 and 31ddebc (branch
                 worktree-pit-eze-guideline-risk-wave1) complete citation #35 (Huang PH et al.,
                 "2022 Taiwan lipid guidelines for primary prevention," J Formos Med Assoc, DOI
                 10.1016/j.jfma.2022.05.010, PMID 35715290) — full text obtained lawfully from the
                 Taiwan Society of Lipids and Atherosclerosis's own tas.org.tw mirror (no PMC
                 deposit; same successful pattern as #30/#32), CC BY 4.0 license confirmed verbatim
                 in the parsed text (not merely asserted), SHA-256 recorded and independently
                 recomputed-and-matched by the second commit. Exact COR/LOE-graded text extracted:
                 four risk-stratified primary-prevention LDL-C targets (<100 mg/dL DM/CKD/LDL-C≥190,
                 <115 mg/dL ≥2 risk factors, <130 mg/dL 1 risk factor, <160 mg/dL 0 risk factors).
                 `02_SOURCE-INVENTORY.md` row #35 already correctly reflects this (folded in by the
                 Director's Gate-2-declaration commit 8543960 from the specialist's report) — no
                 correction needed there. `04_OPEN-QUESTIONS.md` and `05_STATUS.md`, however, were
                 stale (still described #35 as "not yet attempted"/"queued next") — corrected this
                 checkpoint (Decision 2026-08-31-28). Separately noted: the specialist's own
                 supporting evidence files this rests on (wave2-item6-extraction.md §D,
                 fulltext-manifest.md's Huang entry) live only on
                 worktree-pit-eze-guideline-risk-wave1 (not an ancestor of this integration branch
                 past the Wave 1 consolidation point) — a provenance-location gap, not a content
                 error; no merge performed by this checkpoint, flagged for the ordinary consolidation
                 process.
[IMPACT]         Item 6 (numeric-threshold confirmation) now 3/5 complete, 2/5 confirmed blocked
                 (T-006, #34), no target left unattempted. No change to any of the six existing
                 BLOCKED_FOR_SOURCE items (#35 was never one of them). No change to Gate 2 status
                 (READY_WITH_PENDING_ITEMS stands). Wave 3 not opened by this checkpoint.
[ACTION]         04_OPEN-QUESTIONS.md: #35 bullet moved Open -> Resolved. 05_STATUS.md: stale
                 "1/5 (#35) queued next" line corrected to "3/5 complete." Decision 2026-08-31-28
                 logged in 03_DECISION-LOG.md. Diff/secret/tracked-PDF checks run clean (see below).
                 Branch-consolidation gap (worktree-pit-eze-guideline-risk-wave1 commits past Wave 1
                 not yet merged into this branch) recorded for the PI/Director's ordinary
                 consolidation process — not actioned here (out of scope for this checkpoint).
[OUTPUT_PATHS]   04_OPEN-QUESTIONS.md, 05_STATUS.md, 03_DECISION-LOG.md (Decision 2026-08-31-28),
                 this file.
[CONFIDENCE]     HIGH
[STATUS]         READY_FOR_INTEGRATION
```

## Verification checks run this checkpoint

- **Diff review**: `git show d5e5131` and `git show 31ddebc` read in full — both touch only
  guideline-risk-owned paths (`20_EVIDENCE/guideline-risk/`, `30_METHODS/guideline-risk/`,
  `90_CROSS-SESSION-LOG/`), consistent with the File Ownership Matrix (`CLAUDE.md` §3). No edits to
  any Director-owned or other-specialist-owned file.
- **Secret scan**: `git grep` for API-key/secret/bearer-token/password patterns across both commits'
  diffs, and across all tracked files in this branch — no matches (only `.gitignore`'s own pattern
  entries, which is expected).
- **Tracked-PDF/fulltext check**: `git ls-files` for `*.pdf`/`*.parsed.md`/`fulltext/` paths across
  this branch — none tracked. The two new local files
  (`Huang_2022_Taiwan-primary-prevention-guideline.pdf` and `...parsed.md`) confirmed gitignored via
  `git check-ignore -v` (matched by `.gitignore:16`, `**/20_EVIDENCE/**/fulltext/`) and untracked.
  `redistribution_ok`/`license` fields correctly **not** set in `02_SOURCE-INVENTORY.md` for #35,
  consistent with `CLAUDE.md` §11 (full text stays local-only unless/until the Director explicitly
  records `verified: true`/`license:`/`redistribution_ok: true` and commits it — not done, and not
  required, since the PDF itself is not being committed).
- **Governance consistency**: DOI/PMID (10.1016/j.jfma.2022.05.010 / 35715290) match across
  `wave2-item6-extraction.md`, `fulltext-manifest.md`, and `02_SOURCE-INVENTORY.md` row #35. CC BY
  4.0 license claim traced to a verbatim quote from the parsed text (not an inference) per both
  commits. Evidence Hierarchy tag (`GUIDELINE / CONSENSUS`) correctly applied, and the extraction
  correctly warns against conflating these primary-prevention thresholds with #29/TSC-CCS(#30)/
  ADA-2025(#32)/ACC-AHA(#28)'s secondary-prevention/high-risk numbers — consistent with this
  project's known evidence-strength traps (`CLAUDE.md` §7). No change made to any of the six
  `BLOCKED_FOR_SOURCE` items, Gate 2 status, or Wave-3 opening — all confirmed still correctly
  reflected as of this checkpoint.

## Not actioned (out of scope for this checkpoint)

The branch-consolidation gap noted above (`worktree-pit-eze-guideline-risk-wave1` commits after the
Wave 1 consolidation point, including this #35 work, not yet merged into `worktree-wave0-init`) is
recorded here as a finding, not resolved. This session will not merge branches (consistent with the
Director's own prior commitment in Decision 2026-08-31-12 item 4). Raise with the PI/environment
owner if durable single-branch provenance for the specialist's own extraction files is wanted before
Wave 3/Wave 4.
