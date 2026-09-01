# 00_RUN-MANIFEST — pitavastatin-ezetimibe-evidence / 2026-09-01-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence`
RUN_ID: `2026-09-01-v1`
Date initialized: 2026-09-01 (Wave 0, Research Director)
Previous run: `2026-08-31-v1` — **COMPLETE and CLOSED** (Final Gate `PASS_WITH_MINOR_ISSUES`,
consolidated onto `main` at commit `3b6cd01`). This run is additive. `2026-08-31-v1/` is not
modified, overwritten, or reopened by this run (Golden Rule 9 / `CLAUDE.md` "Additive versioning").

## PI authorization

Explicit new-run authorization received 2026-09-01 (interactive session, shared checkout) —
"explicit new PI authorization for an additive update." Authorizes, beyond the prior run's scope:
manuscript/presentation-ready output in `50_MANUSCRIPT/` (contingent on Wave/Gate order, not a Wave 0
deliverable), and incorporation of a new Google Drive intake at `inbox/2026-acc-aha-drive/`. All
roles use model **sonnet**. Constraints carried forward and restated: no Sci-Hub, no
`mcp__research_hub__download_paper` (CLAUDE.md §10, Decision 2026-08-31-08, permanent); no push to
GitHub this run unless the PI explicitly requests it later; local commits only once governance/QA
rules are satisfied; every intake file treated as derivative/unverified secondary material until
clinically material claims are independently checked against a primary source — never call the
intake bundle "the official guideline PDF."

## Git

- Repo root: `/Users/ander/Documents/medical/hyperlipidemia/pitavastatin`
- This session works in an isolated git worktree (`.claude/worktrees/pit-eze-run-2026-09-01/`,
  branch `worktree-pit-eze-run-2026-09-01`), per this environment's background-job isolation
  requirement; merges/consolidates back to `main` the same way prior-run specialist branches did.
  `inbox/2026-acc-aha-drive/` is untracked and therefore not present inside the worktree checkout —
  it is read directly from the main checkout's absolute path
  (`/Users/ander/Documents/medical/hyperlipidemia/pitavastatin/inbox/2026-acc-aha-drive/`); reads
  across the worktree boundary are fine, only writes are isolated.
- `main` HEAD at Wave 0 init: `3b6cd01` ("Governance housekeeping: PR #1 closed as superseded
  (Decision 40)") — the fully consolidated, closed state of `2026-08-31-v1`.

## Duplicate-Director incident (resolved before any write action)

At Wave 0 start, `ListAgents` revealed a second live session named
`pit-eze-research-director [853c1a]` (status `busy`), concurrent with fresh restarts of all three
specialist peers — indicating the same PI directive had been dispatched through two channels. Per
Golden Rule 1 (never silently substitute/duplicate), this Director held all writes and sent a
`CONFLICT` message before creating any file. `[853c1a]` replied with full disclosure: it had been
working in an isolated git worktree (`.claude/worktrees/wave0-init/`, branch `worktree-wave0-init`),
had created only draft `00_RUN-MANIFEST.md`/`01_RESEARCH-CHARTER.md` files (uncommitted, unpushed),
and — critically — had **not** contacted any specialist. It stood down in favor of this session (the
interactive one, in the checkout the PI can see) and confirmed it would not push its branch, edit
further, or contact specialists. A follow-up `ListAgents` check showed `[853c1a]` no longer listed
(session ended). This run's manifest/charter are therefore written fresh by this session, not pulled
from the other draft, to keep a single unambiguous authorship trail for Director-owned governance
files. Logged in full in `03_DECISION-LOG.md` (Decision 2026-09-01-01) and `90_CROSS-SESSION-LOG/`.

## New intake: Google Drive bundle (`inbox/2026-acc-aha-drive/`)

Transferred and checksum-verified per the PI. Contents as inventoried by this Director at Wave 0:

- `MANIFEST.md` (SHA-256 `c662d526...ff88328`) — documents 34 Drive file IDs (title/timestamp/size/
  matched-query), revealing 8 duplicated "topic slot" families (2–4 timestamped versions each:
  `00_master_comparison`, `00_quick_reference_card`, `01_risk_targets`, `02_pharmacotherapy`,
  `03_special_populations`, `04_evidence_key_trials`, `05_monitoring_lifestyle`,
  `differences_summary`, plus 2 versions each of `confidence_map` and `adjudication_log_v2`) and 5
  unique `draft_11_12`/`draft_13_14`/`draft_15_16`/`draft_17_18`/`draft_19_20.md` files.
- Full-bundle SHA-256 inventory taken at Wave 0 (35 files incl. MANIFEST.md); **finding**: the two
  `adjudication_log_v2.md` copies (file IDs `1iZ5z7JpSPKYGtCgXqb3pMBXDw0SmwCuu` and
  `1kSqP4HeCkQa8gy1aJqravEKSKReepv-T`) are byte-identical (SHA-256
  `0cc50981a9683f15aa407a2f86a645c84ccc31b82ac621af548515fb4b48d3aa`) — a true duplicate, not just a
  same-slot revision.
- This entire bundle is **derivative/unverified secondary material** (AI-assisted "2018 vs 2026
  ACC/AHA differences" comparison drafts, Traditional Chinese, internally citing a "五組專題分析團隊"
  multi-draft merge process and its own adjudication log). Per PI directive, no clinically material
  claim from it may enter `20_EVIDENCE/`/`40_SYNTHESIS/` without independent verification against a
  primary guideline/trial/lawful full text.
- Intake's own evidence-confidence-tier scheme (`direct_guideline / trial_supported /
  observational_extrapolation / future_direction`, defined in `adjudication_log_v2.md`) is **not**
  adopted as this project's taxonomy — `CLAUDE.md` §7's Evidence Hierarchy remains authoritative.
  The intake's own tags may be recorded as a provenance cross-reference only, never substituted for
  our own tagging.

### Major unplanned finding: `inbox/2026-acc-aha-drive/official/` (appeared during Wave 0 recon)

A subfolder not mentioned in the PI's original intake description was found present during Wave 0
reconnaissance, timestamped 2026-09-01 10:50–10:52 (i.e., dropped in this morning, after this run's
authorization message):

| File | Size | SHA-256 |
|---|---:|---|
| `2026_ACC_AHA_Multisociety_Dyslipidemia_Guideline_Circulation.pdf` | 16,887,416 bytes (123 pages, per its own manifest) | `2a6af5e2801b02d75f43d9ed25181e01f344b8751cc76bbc03d181957bf81ffa` |
| `2026_ACC_AHA_Multisociety_Dyslipidemia_Guideline_Circulation.md` | 697,056 bytes / 9,536 lines | `b7d468b7730973b70a200de6a3ae9550a91cda77b928d14bbf53f8f09f216cf7` |
| `OFFICIAL_SOURCE_MANIFEST.md` | 1,238 bytes | `232f8b65d72c1789cbafbef30b1cd891357f29b953647a091da3e41326380687` |

`OFFICIAL_SOURCE_MANIFEST.md` claims: title "2026 ACC/AHA/AACVPR/ABC/ACPM/ADA/AGS/APhA/ASPC/NLA/PCNA
Guideline on the Management of Dyslipidemia," *Circulation*. 2026;153:e1154–e1276, DOI
`10.1161/CIR.0000000000001423`, retrieved 2026-09-01 (Asia/Taipei), with AHA landing-page and PDF
URLs given. **Both stated SHA-256 hashes and the stated line count (9,536) were independently
re-computed by this Director and match exactly.**

**Director's own spot-check (Wave 0, read-only, no MCP call yet):** the `.md`'s header
self-identifies consistently with the manifest (same title, same DOI, same *Circulation*
2026;153:e1154–e1276 citation repeated as a running footer); realistic PDF-extraction artifacts are
present (e.g., a rotated sidebar heading garbled to "STNEMETATS LACINILC SENILEDIUG DNA" = "AND
GUIDELINES CLINICAL STATEMENTS" reversed) that would be unusual for a purely AI-generated fabrication.
Grep sanity: `pitavastatin` ×8, `ezetimibe` ×110, `bempedoic` ×52, `inclisiran` ×35, `Lp(a)` ×127 —
consistent with a genuine, comprehensive multi-society dyslipidemia guideline. Cross-checked 4 of the
new intake's `adjudication_log_v2.md` line-number claims against this file: the **topic content**
(CAC 300–999 two-tier LDL-C/non-HDL-C targets at lines ~4408/4460; dialysis-continuation COR 2b C-LD
near line ~5271; HFrEF ischemic COR 2b B-R near line ~5210; older-adult deprescribing/CAC guidance
near lines ~4971–4989) is **present and topically consistent** with 3–4 of the 4 claimed corrections,
but the **exact line numbers do not match** this file's own numbering (e.g., "line ~1521" in the
intake log lands on an unrelated triglyceride/weight-loss passage here) — meaning the intake's
adjudication log was almost certainly built against a *different* extraction/pagination of the same
underlying guideline (it names its own source as `markdown/1-s2.0-S0735109725102544.md`, an
Elsevier/JACC-PII-pattern filename — not present anywhere in this intake — vs. this file's AHA/
Circulation DOI prefix `10.1161`). **This is a real, unresolved discrepancy, not yet reconciled.**

**This is treated as an unverified candidate primary source, not yet a verified one.** It is NOT
independently confirmed via Crossref/PubMed/doi.org yet (MCP connectivity for `paper-search`/
`tavily`/`research_hub` was down for literature search at Wave 0 recon time — re-check at Wave 1
dispatch). It must not be called "the official guideline" in any output until guideline-risk-
intelligence completes independent DOI/metadata verification and a PDF-vs-MD spot check (the `.md`
is explicitly labeled by its own manifest as "a machine-extracted convenience copy, not an
independently published guideline"). Assigned as guideline-risk-intelligence's #1 Wave 1 priority —
see `04_OPEN-QUESTIONS.md`. If verified, this would resolve the prior run's long-standing citation
#28 `BLOCKED_FOR_SOURCE` gap (DOI `10.1016/j.jacc.2025.11.016`, JACC) — note that DOI differs from
this file's `10.1161/CIR.0000000000001423` (Circulation); whether these are two genuine co-publication
DOIs for the same joint guideline (a known real pattern for major ACC/AHA guidelines) or one is a bad
citation is itself an open question, not assumed either way.

Per `CLAUDE.md` §11 (full-text/licensing) and §9 (numeric integrity / tool-confabulation caution),
this PDF/MD pair remains local-only: `.gitignore` updated this Wave 0 to exclude `inbox/` entirely
(previously only `**/*.pdf`/`**/*.PDF` were covered — the 697 KB `.md` derivative and the 34 small
intake drafts were not). No redistribution license has been verified for either the PDF or its `.md`
derivative; neither may be committed.

## MCP connectivity at Wave 0 (2026-09-01)

Failed to connect this session: `paper-search` (ENOENT: `uv` not found), `tavily` (ENOENT: `npx` not
found), `openevidence` (ENOENT: `node` not found). Connected: `research_hub` (metadata/search tools
only — `download_paper` remains permanently prohibited, Decision 2026-08-31-08), `llamaparse`,
`google-scholar`. Re-confirm all before Wave 1 literature dispatch; do not assume prior run's Wave 2
"repaired" status carries over session-to-session (per the prior run's own established caution).

## Persistent session topology (see CLAUDE.md §2)

1. Research Director (this session, `pit-eze-research-director [5aa219]`)
2. guideline-risk-intelligence (`pit-eze-guideline-risk [dac378]`)
3. trials-efficacy-intelligence (`pit-eze-trials-efficacy [615600]`)
4. safety-pharmacology-intelligence (`pit-eze-safety-pharmacology [192773]`)
5. independent-auditor (Wave 4 only — not yet spawned this run)

All three specialists were observed via `ListAgents` at Wave 0, `idle`, having restarted ~9 minutes
prior (consistent with the duplicate-dispatch incident above, not yet contacted by this Director as
of manifest creation).

## Output folders

Full tree created at Wave 0: `10_DATA/{guideline-risk,trials-efficacy,safety-pharmacology,fulltext}/`,
`20_EVIDENCE/{guideline-risk,trials-efficacy,safety-pharmacology}/`,
`30_METHODS/{shared,guideline-risk,trials-efficacy,safety-pharmacology}/`, `40_SYNTHESIS/`,
`50_MANUSCRIPT/` (owned by Director per CLAUDE.md §3, manuscript work explicitly PI-authorized this
run — still gated behind Wave 3 per CLAUDE.md §4), `90_CROSS-SESSION-LOG/`.

## File ownership

See `CLAUDE.md` §3 — unchanged from the prior run, authoritative, not duplicated here.

## Current research gate

**Gate 0** — Wave 0 (Orientation) in progress. `05_STATUS.md` is the authoritative current-gate
pointer going forward, per the prior run's established convention (this manifest is not edited in
place for later gate transitions — additive updates only, appended below).
