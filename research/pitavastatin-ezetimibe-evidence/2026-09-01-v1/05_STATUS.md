# 05_STATUS — pitavastatin-ezetimibe-evidence / 2026-09-01-v1

**Authoritative current-gate/wave pointer for this run** (per prior-run convention — manifest/charter
are not edited in place for gate transitions; this file is).

## Current state: Wave 0 (Orientation) complete; Wave 1 (Source/Evidence Verification) underway

- Duplicate-Director collision detected and resolved (Decision 2026-09-01-01) before any specialist
  contact or shared-state write. ✅
- Repo/governance scaffold created: `00_RUN-MANIFEST.md`, `01_RESEARCH-CHARTER.md`,
  `02_SOURCE-INVENTORY.md`, `03_DECISION-LOG.md`, `04_OPEN-QUESTIONS.md`, this file, full output
  directory tree. ✅
- `.gitignore` extended to exclude `inbox/` wholesale (Decision 2026-09-01-02). ✅
- New Google Drive intake inventoried (35 files, checksummed; 1 true byte-identical duplicate pair
  found among the "adjudication_log_v2.md" copies). ✅
- Major unplanned finding: `inbox/2026-acc-aha-drive/official/` — a candidate genuine full text of
  the 2026 ACC/AHA dyslipidemia guideline. Director's own read-only spot-check found it plausible but
  explicitly unverified (Decision 2026-09-01-03); assigned to guideline-risk-intelligence as Wave 1
  priority #1. ✅ (finding recorded, not yet independently confirmed)
- Combined resume + Wave 1 `TASK_ASSIGNMENT` sent to all three specialists (deliberate relaxation of
  strict wait-for-READY-before-any-task sequencing — justified in `90_CROSS-SESSION-LOG/
  2026-09-01-wave1-dispatch.md`, since all three are already-oriented long-lived roles from the
  just-closed prior run, not fresh spawns). ✅
- Local-worktree-branch coordination issue hit and resolved: this run's commits live on the
  Director's local worktree branch (`worktree-pit-eze-run-2026-09-01`), deliberately not pushed to
  origin per the PI's no-push instruction. `trials-efficacy` and `safety-pharmacology` each initially
  reported `BLOCKED_FOR_SOURCE` (couldn't find `2026-09-01-v1/` on `main`/`origin`); both resolved by
  reading the branch directly (`git show worktree-pit-eze-run-2026-09-01:<path>`) since all sessions
  share one local `.git` — no push was needed. `guideline-risk` found this independently without
  reporting a blocker. See `90_CROSS-SESSION-LOG/2026-09-01-wave1-dispatch.md` addenda for detail.

## Wave 1 — underway

| Specialist | Status | Notes |
|---|---|---|
| `pit-eze-guideline-risk` | **T-101 verified, focus area 1 complete (2 rounds of self/QA correction), T-102 dedup complete, STS/ESC/Lp(a) re-check done** | Cherry-picked onto Director branch (`0a19899`, `f6b5f92`, `8a1ab51`). Corrected the target-attainment table to a genuine 3-tier severe-hypercholesterolemia structure (Decision 2026-09-01-10, supersedes -08); confirmed Taiwan STS is now genuine Gold OA/CC BY but still Cloudflare-blocked for fetch. Attack/defense writeup in progress — last item before Wave 1 closure for this role. |
| `pit-eze-trials-efficacy` | **Focus areas 2/3/5 complete, K-924 independently verified** | Cherry-picked onto Director branch (`29a832e`). See Decision 2026-09-01-09. Two new HIJ-PROPER substudies flagged with honest confidence caveats (Q9); inclisiran hard-outcome-trial gap confirmed (Q10). `STATUS: READY_WITH_PENDING_ITEMS`. |

**All three specialists' Wave 1 work (+ most of Wave 2 attack/defense) is now consolidated onto the
Director's branch (`worktree-pit-eze-run-2026-09-01`) via clean cherry-picks — this branch is the
current single source of truth for this run's evidence content.**

## Gate 1: PASSED (Decision 2026-09-01-11)

Facts substantively verified before interpretation. Proceeding to Wave 2 wrap-up (already
substantively complete) → Gate 2 → **Wave 3: synthesis (in progress)**.

## Current state: Wave 3 (Synthesis) — in progress

Director building `40_SYNTHESIS/` (integrated zh-TW evidence brief + attack/defense + traceability),
`50_MANUSCRIPT/` (slide-ready positioning/defense doc), drawing on all three specialists' consolidated
evidence. Elevated framing note carried into synthesis: the Taiwan STS "ezetimibe as first add-on"
claim is this project's single largest unverified-but-load-bearing framing claim (guideline-risk's
own assessment, Decision 2026-09-01-11) — must be stated explicitly as unverified everywhere it
appears, never as if resolved.
| `pit-eze-safety-pharmacology` | **Focus area 4 + attack/defense complete; 2 rounds of QA corrections applied, committed** | Latest commit `b7bf5fa`. All 3 QA items from Decision 2026-09-01-06 fixed: K-924 dose-doubling claim downgraded to `OBSERVATIONAL SIGNAL`/`INSUFFICIENT EVIDENCE`; mg/dL↔mmol/L anomaly confirmed + extended (7+ correct 2.6 conversions found elsewhere, column-merge-artifact hypothesis); Taiwan STS attribution removed, retagged `EXPERT INTERPRETATION`. Flagged that no role has yet independently verified the K-924 matched-dose LS-difference figures — routed to trials-efficacy. |

## Gate 0 checklist

- [x] Duplicate-Director conflict resolved
- [x] Governance files created
- [x] Intake inventoried and major findings recorded
- [x] Task assignments sent to all 3 specialists; 2 of 3 (`safety-pharmacology`, `trials-efficacy`)
      confirmed `READY` and starting; `guideline-risk` has its own worktree checked out (observed via
      `git worktree list`), no report received yet
- [ ] MCP connectivity re-confirmed for Wave 1 — confirmed independently by `trials-efficacy` and
      `safety-pharmacology`: `paper-search`/`tavily`/`openevidence` down (PATH: `uv`/`npx`/`node`
      missing), `research_hub`/`google-scholar`/`llamaparse` live. Treated as a workable-around
      environment note, not a hard blocker — to mention to the PI, not yet escalated.

**Gate 0 treated as informally open (Wave 1 work underway) pending all three specialists' first
substantive reports** — will be formally declared `READY_FOR_NEXT_WAVE` once all three have reported
at least once with real findings or an explicit blocker.

## Next actions (in order)

1. Continue processing specialist replies as they arrive (trials-efficacy and guideline-risk still to
   report in).
2. Record specialist findings into `02_SOURCE-INVENTORY.md`/`03_DECISION-LOG.md` as they land —
   especially the `official/` guideline verification outcome from guideline-risk (top priority).
3. Once all three have reported, formally close Gate 0 and confirm Wave 1 → Gate 1 readiness.
4. Gate 1 → Wave 2 → Gate 2 → Wave 3 (synthesis + zh-TW brief + `50_MANUSCRIPT/` slide-ready doc,
   now PI-authorized) → Gate 3 (Director Challenge Round) → Wave 4 (new sonnet independent auditor)
   → Final Gate, per `CLAUDE.md` §4.
