# 04_OPEN-QUESTIONS — pitavastatin-ezetimibe-evidence / 2026-08-31-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`

Categories: `NEEDS_SOURCE` | `NEEDS_ANALYST` | `NEEDS_METHODS` | `NEEDS_PI`. Additive — do not delete
resolved items, move them to a "Resolved" section at the bottom with a pointer to the
`03_DECISION-LOG.md` entry that resolved them.

## Open

- [NEEDS_PI] Should a dedicated **manuscript/presentation-intelligence** persistent role be created
  for this run, to eventually turn `40_SYNTHESIS/` content into slide/manuscript material in
  `50_MANUSCRIPT/`? The task's role list names only Research Director + 3 domain specialists +
  auditor; the mandated directory structure includes `50_MANUSCRIPT/` with no owner. Left unowned
  at Wave 0 (Decision 2026-08-31-04). See `CLAUDE.md` §3 and `03_DECISION-LOG.md` (2026-08-31-04).

- [NEEDS_ANALYST] `Tonvasca_2026.md` lines 1795–2811 (~36% of the file) were not read during Wave 0
  orientation (single-read output cap). The owning specialist(s) must read the remainder in Wave 1
  and add any further citations found there to `02_SOURCE-INVENTORY.md` before treating that
  inventory as complete (Decision 2026-08-31-02).

- [NEEDS_SOURCE] `research_hub`, `llamaparse`, and `openevidence` MCP servers failed to connect
  during Wave 0 (binary/venv not found for the first two; connection closed for the third).
  Re-confirm connectivity at Wave 1 start; if still down, either (a) the PI/environment owner fixes
  them (rebuild `research_hub`'s Rust binary, recreate the `llamaparse` Python venv, retry
  `openevidence`), or (b) Wave 1/2 proceeds on the remaining lawful source set (`paper-search`,
  `google-scholar`, PubMed/PMC, Crossref, Unpaywall, `tavily`) and this is logged as a coverage
  limitation, never as a reason to use Sci-Hub or any unauthorized source (Decision 2026-08-31-03).

- [NEEDS_SOURCE] Primary publications not yet located for: HIJ-PROPER (T-001), RACING (T-002), the
  2024 pitavastatin-vs-atorvastatin/rosuvastatin NODM systematic review referenced generically in
  `pitavastatin topic.md` (T-003), pitavastatin 2 mg vs 4 mg dose-comparison studies (T-004), the
  Taiwan STS 2026 consensus (T-005), the Taiwan Lp(a) 2026 consensus (T-006), and the ESC 2025
  Focused Update on in-hospital ACS lipid-lowering intensification (T-007). See
  `02_SOURCE-INVENTORY.md` for detail. All are Wave 1/2 acquisition targets for
  trials-efficacy-intelligence and/or guideline-risk-intelligence per the Search Protocol
  (`CLAUDE.md` §5).

- [NEEDS_ANALYST] Every numeric figure currently quoted from `Tonvasca_2026.md` in
  `02_SOURCE-INVENTORY.md` (HIJ-PROPER's 32.8%/36.9%/HR 0.89/95% CI 0.76–1.04/P=0.152/subgroup HR
  0.71; RACING's 9.1%/9.9%/DM-subgroup 10.0%/11.3%/discontinuation 4.8%/8.2%/5.2%/8.7%; Phase III
  FDC trial's −51.04%/−50.5%/−34.99%/−36.11%/−20.01%/−19.85%, all p<0.001 vs FDC; Sydhom et al. 2024
  meta-analysis figures) is an **unverified legacy figure** until independently checked against the
  primary publication in Wave 1 — none of these may be cited in `20_EVIDENCE/` or `40_SYNTHESIS/` as
  confirmed until that verification is recorded.

## Resolved

*(none yet)*
