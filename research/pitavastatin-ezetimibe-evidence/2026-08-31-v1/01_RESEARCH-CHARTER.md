# 01_RESEARCH-CHARTER — pitavastatin-ezetimibe-evidence / 2026-08-31-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence`
RUN_ID: `2026-08-31-v1`

## Primary question

What is the current (2025–2026) evidence base — guideline positioning, RCT/meta-analytic efficacy,
and safety/pharmacology — for pitavastatin, ezetimibe, and pitavastatin/ezetimibe fixed-dose
combination (FDC) therapy in dyslipidemia management, and how strong is that evidence at each level
(LDL-lowering efficacy → combination-strategy cardiovascular outcome evidence →
pitavastatin/ezetimibe-specific hard-outcome evidence)?

Framed as the topic file's own reorientation question: **"Should we treat the statin dose, or treat
the LDL target?"** — and, downstream of that: where does an FDC strategy (specifically pitavastatin/
ezetimibe) sit within a goal-directed, STS-aware, tolerability-conscious treatment paradigm for
Asian/Taiwanese patients with polypharmacy and comorbidity burden.

## Scope (PECO-style framing)

- **Population:** adults with primary hypercholesterolemia / mixed dyslipidemia / established
  ASCVD or high cardiovascular risk, with emphasis on Asian/Taiwanese populations, elderly patients,
  and patients with diabetes/polypharmacy where the literature allows.
- **Exposure/Intervention:** pitavastatin (as monotherapy, at 1/2/4 mg doses), ezetimibe, and
  pitavastatin/ezetimibe FDC; secondarily, other statin+ezetimibe combination-strategy evidence
  (e.g., rosuvastatin+ezetimibe/RACING) used as indirect strategy-level evidence, and other statins
  used as glycemic/DDI comparators.
- **Comparator:** high-intensity statin monotherapy; individual monotherapy components; dose
  escalation (2 mg→4 mg) vs add-on ezetimibe at fixed statin dose; other statins for glycemic/DDI
  comparisons.
- **Outcomes:** LDL-C percent change and target attainment (<100/<70/<55 mg/dL as risk-tier
  appropriate); MACE and other hard cardiovascular outcomes where available; new-onset diabetes
  (NODM)/glycemic parameters; muscle AE/CK; hepatic enzyme elevation; DDI risk; tolerability/
  discontinuation; residual risk markers (Lp(a), ApoB, remnant cholesterol) as a bounded secondary
  theme (≤10–15% of eventual output weight, per the topic file's own guidance).

## Secondary questions

See `CLAUDE.md` §5 (Prioritized Search Protocol), items 1–10 — each is a secondary question this
review must be able to answer, each pre-assigned to an owning specialist role.

## Final outputs (of the overall project, not of Wave 0)

- `20_EVIDENCE/`: evidence-hierarchy-tagged notes per domain (guideline-risk, trials-efficacy,
  safety-pharmacology), each claim traceable to a verified source.
- `10_DATA/`: exact numeric extraction tables (LDL-C % change, MACE rates, HR/RR with CI, AE rates,
  dose-comparison figures) with full provenance.
- `40_SYNTHESIS/`: an integrated evidence map and clinical synthesis organized around the Level
  1/2/3 hard-outcome evidence-hierarchy framework (`pitavastatin topic.md` §6), explicit about what
  is/is not directly proven for pitavastatin/ezetimibe specifically vs what is strategy-level or
  guideline-level support.
- Presentation/manuscript-ready conclusions in `50_MANUSCRIPT/` — **contingent** on the PI resolving
  the open question of whether a dedicated manuscript/presentation-intelligence role is created for
  this run (see `04_OPEN-QUESTIONS.md`); not committed to as a Wave 0 deliverable.
- `04_OPEN-QUESTIONS.md`: unresolved evidence gaps, explicitly not silently filled.

## Source of truth

- Repo root legacy files: `pitavastatin topic.md`, `Tonvasca_2026.md` — read-only inputs (do not
  overwrite; see `CLAUDE.md` §1). `Tonvasca_2026.md`'s citations are **unverified legacy
  claims** until independently re-verified in Wave 1.
- `docs/CROSS-SESSION-RESEARCH-RUNBOOK.md` — the general operating-system reference this project's
  `CLAUDE.md` instantiates.
- This run's own `10_DATA/`, `20_EVIDENCE/`, `30_METHODS/`, `40_SYNTHESIS/` once populated — always
  the current run's outputs, never a conversation transcript, are the durable record.

## Files that must not be modified

- `pitavastatin topic.md`, `Claude_Code_Cross-Session_Research_完整建議與經驗_Runbook.md`,
  `Tonvasca_2026.md` (repo root legacy inputs — read-only for every role, per `CLAUDE.md` §1).
- Any prior RUN_ID's output folders, once a RUN_ID is superseded — additive versioning only
  (Runbook §29, Golden Rule 9). (No prior RUN_ID exists yet for this project.)

## Major uncertainty going in (Wave 0 assessment)

- Whether pitavastatin/ezetimibe-specific hard cardiovascular outcome evidence exists beyond
  HIJ-PROPER's non-superior overall primary endpoint (the topic file already flags this as the
  weakest of the three evidence levels — Wave 1/2 must confirm no newer trial has closed this gap).
- Whether the Taiwan STS 2026 consensus and Taiwan Lp(a) 2026 consensus are indexed/retrievable
  through the allowed lawful MCP sources, or require manual PI-supplied full text.
- MCP connectivity gaps recorded in `00_RUN-MANIFEST.md` (`research_hub`, `llamaparse`,
  `openevidence`) that may constrain full-text acquisition in Wave 1/2 until resolved.

**Status update, Gate 2, 2026-08-31 (Decision 2026-08-31-27) — kept additive, original assessment
above left unedited:** No newer trial closing the Level 3 gap was found through Wave 2 (HIJ-PROPER
remains the anchor; REPRIEVE/REAL-CAD are pitavastatin monotherapy hard-outcome trials, kept
explicitly outside the FDC-specific framework — see the Wave 2 Challenge Round,
`30_METHODS/shared/wave2-challenge-round.md`, for why this remains the project's top overclaim
risk). Taiwan STS 2026's citation is verified but its content (the specific "ezetimibe as first
add-on" claim) remains unverified against primary text — `BLOCKED_FOR_SOURCE`, PI-confirmed not to
be assumed resolvable. `research_hub`/`llamaparse` MCP connectivity was repaired before Wave 2;
`openevidence` remains down. See `04_OPEN-QUESTIONS.md` for the current, itemized state of all
three.

## Role division (see CLAUDE.md §2–§3 for full detail; not duplicated here)

Research Director; guideline-risk-intelligence; trials-efficacy-intelligence;
safety-pharmacology-intelligence; independent-auditor (Wave 4).

## Stop conditions

- A required persistent peer is unreachable after the recovery procedure (CLAUDE.md §13) →
  BLOCKED, reported, not silently substituted.
- A needed source is not lawfully obtainable through allowed MCP sources → `BLOCKED_FOR_SOURCE`,
  never routed around via Sci-Hub or any unauthorized access (CLAUDE.md §10).
- A numeric or factual conflict cannot be resolved by the Decision Taxonomy without PI input →
  `NEEDS_PI`, logged in `03_DECISION-LOG.md` / `04_OPEN-QUESTIONS.md`, not guessed.

## Success conditions

- Every claim entering `20_EVIDENCE/` or `40_SYNTHESIS/` carries an Evidence Hierarchy tag
  (CLAUDE.md §7) and a traceable citation.
- Every number in `10_DATA/` is byte-for-byte traceable to a specific source (Numeric Integrity
  Rule, CLAUDE.md §9).
- All ten Search Protocol items (CLAUDE.md §5) have been addressed with either evidence, an explicit
  "insufficient evidence" determination, or a logged blocker — not silence.
- Independent audit (Wave 4) reaches PASS or PASS_WITH_MINOR_ISSUES before anything is marked FINAL.
