# 05_STATUS — pitavastatin-ezetimibe-evidence / 2026-09-01-v1

**Authoritative current-gate/wave pointer for this run** (per prior-run convention — manifest/charter
are not edited in place for gate transitions; this file is).

## Current state: Wave 0 (Orientation) — in progress

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
- Specialists (`pit-eze-guideline-risk`, `pit-eze-trials-efficacy`, `pit-eze-safety-pharmacology`)
  observed alive via `ListAgents` (idle), **not yet contacted this run** — next action.

## Gate 0 checklist (before dispatching Wave 1)

- [x] Duplicate-Director conflict resolved
- [x] Governance files created
- [x] Intake inventoried and major findings recorded
- [ ] `ListAgents` health check + `CROSS_SESSION_TEST` sent to all 3 specialists, `READY` received
- [ ] MCP connectivity re-confirmed for Wave 1 (paper-search/tavily/openevidence were down at Wave 0
      recon; research_hub/llamaparse/google-scholar were up)

**Gate 0 not yet declared `READY_FOR_NEXT_WAVE`** — pending the two unchecked items above. No
specialist should receive real (non-test) task assignments until this gate closes.

## Next actions (in order)

1. Send `CROSS_SESSION_TEST`/resume prompts (CLAUDE.md §14.3, updated for this RUN_ID and scope) to
   all three specialists; wait for `READY`.
2. Declare Gate 0 `READY_FOR_NEXT_WAVE` once specialists confirm and MCP connectivity is re-checked.
3. Dispatch Wave 1: guideline-risk-intelligence on intake dedup/verification + the `official/`
   candidate-source verification (top priority) + focus area 1 exact-wording work; trials-efficacy-
   intelligence on focus areas 2–3; safety-pharmacology-intelligence on focus area 4. All three also
   begin contributing to the attack/defense section (focus area 5) within their domain.
4. Gate 1 → Wave 2 → Gate 2 → Wave 3 (synthesis + zh-TW brief + `50_MANUSCRIPT/` slide-ready doc,
   now PI-authorized) → Gate 3 (Director Challenge Round) → Wave 4 (new sonnet independent auditor)
   → Final Gate, per `CLAUDE.md` §4.
