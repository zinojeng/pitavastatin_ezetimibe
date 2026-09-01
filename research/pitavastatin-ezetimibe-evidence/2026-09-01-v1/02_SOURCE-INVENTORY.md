# 02_SOURCE-INVENTORY — pitavastatin-ezetimibe-evidence / 2026-09-01-v1

Specialists never edit this file directly (Decision 2026-08-31-05, carried forward) — they report
per-citation verification findings to the Director via the message schema (`CLAUDE.md` §6), and the
Director records them here.

This run's inventory is additive to `2026-08-31-v1/02_SOURCE-INVENTORY.md` (T-001–T-028 plus ~35
legacy citations). New entries continue the `T-0NN` numbering from where the prior run left off,
prefixed `T-1xx` to make the run boundary unambiguous at a glance. Nothing in the prior run's
inventory is edited here.

## Status legend

`UNVERIFIED` (recorded, not yet checked) · `VERIFICATION_IN_PROGRESS` · `VERIFIED` (independently
confirmed against a primary/lawful source) · `BLOCKED_FOR_SOURCE` · `SOURCE_CONFLICT` ·
`RETIRED` (superseded by a later, more specific entry).

## Candidate sources under active verification (Wave 0/1)

| ID | Source | Claimed DOI/locator | Status | Owner | Notes |
|---|---|---|---|---|---|
| T-101 | `inbox/2026-acc-aha-drive/official/2026_ACC_AHA_Multisociety_Dyslipidemia_Guideline_Circulation.{pdf,md}` — "2026 ACC/AHA/AACVPR/ABC/ACPM/ADA/AGS/APhA/ASPC/NLA/PCNA Guideline on the Management of Dyslipidemia," Circulation. 2026;153:e1154–e1276 | DOI `10.1161/CIR.0000000000001423` | `UNVERIFIED` — Director's Wave 0 read-only spot-check found internally consistent self-citation, plausible extraction artifacts, and topical (not line-exact) agreement with 3–4 of `T-104`'s claimed corrections; SHA-256/line-count match the file's own `OFFICIAL_SOURCE_MANIFEST.md` exactly. Not yet confirmed via Crossref/PubMed/doi.org. | guideline-risk-intelligence (assigned Wave 1 #1 priority) | Local-only per `CLAUDE.md` §11 (gitignored). If verified, is the leading candidate to resolve prior-run citation #28 (`BLOCKED_FOR_SOURCE`, DOI `10.1016/j.jacc.2025.11.016`) — but note the DOI prefix differs (`10.1161` Circulation vs `10.1016` JACC); relationship between the two DOIs is itself unresolved, see `04_OPEN-QUESTIONS.md`. |
| T-102 | `inbox/2026-acc-aha-drive/` bundle overall (34 files + `MANIFEST.md`) — AI-assisted "2018 vs 2026 ACC/AHA Dyslipidemia Guidelines Comparison" draft set | n/a (secondary/derivative) | `UNVERIFIED` — per-file dedup and claim-level verification pending | guideline-risk-intelligence | Treat as `EXPERT INTERPRETATION`/`INSUFFICIENT EVIDENCE` at best until specific claims are checked against T-101 (if verified) or another primary source. Never cite as "the official guideline." |
| T-103 | `.../adjudication_log_v2.md` (2 byte-identical copies, file IDs `1iZ5z7JpSPKYGtCgXqb3pMBXDw0SmwCuu` / `1kSqP4HeCkQa8gy1aJqravEKSKReepv-T`) — 4 claimed corrections (CAC 300-999 targets, dialysis statin COR, HFrEF statin COR, older-adults ≥75 COR), each with a line reference into `markdown/1-s2.0-S0735109725102544.md` | Self-cited source file not present in intake | `UNVERIFIED` / partially cross-checked | guideline-risk-intelligence | Director's Wave 0 check: 3–4 of 4 corrections are topically consistent with real content found in T-101, but at different line numbers — suggests the intake's cited source is a *different* extraction of the same guideline, not T-101 itself. `markdown/1-s2.0-S0735109725102544.md` (Elsevier/JACC-PII-pattern filename) is referenced but absent from this intake — do not assume it exists or is obtainable. |

## Legacy items carried forward (unchanged from prior run, reference only — see `2026-08-31-v1/02_SOURCE-INVENTORY.md` for full detail)

- T-028 (Blumenthal RS et al., "2026 ACC/AHA guideline," DOI `10.1016/j.jacc.2025.11.016`) remains
  `BLOCKED_FOR_SOURCE` as of prior-run closure. This run's T-101 discovery is directly relevant to
  resolving it, but T-028 itself is **not edited** here — any resolution is recorded as a *new* entry
  in this run's inventory cross-referencing T-028, per additive-versioning discipline.

## New per-focus-area entries

To be populated by Wave 1 specialist reports (T-105 onward): Phase III/FDC trial RWE search results,
new 2 mg-vs-4 mg data, any newer HIJ-PROPER follow-up/re-analysis, 2025–2026 guideline citations
beyond T-101 (ESC 2025 Focused Update, Taiwan STS/Lp(a) consensus re-checks if new versions exist),
PCSK9-targeting/bempedoic acid/inclisiran positioning trials for the attack/defense section.
