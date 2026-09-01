# 04_OPEN-QUESTIONS — pitavastatin-ezetimibe-evidence / 2026-09-01-v1

Additive to `2026-08-31-v1/04_OPEN-QUESTIONS.md`. Open items from that run are not repeated here
unless this run's new material bears on them directly (noted where relevant).

## Q1 — Is `inbox/2026-acc-aha-drive/official/2026_ACC_AHA_..._Circulation.{pdf,md}` a genuine,
verifiable primary source?

**Status:** OPEN, `NEEDS_ANALYST` (guideline-risk-intelligence, Wave 1 priority #1).
**Why it matters:** if genuine, this is a 123-page, 9,536-line full text of what claims to be the
actual 2026 ACC/AHA/AACVPR/ABC/ACPM/ADA/AGS/APhA/ASPC/NLA/PCNA dyslipidemia guideline — the single
most consequential possible acquisition for this run's focus area 1 (exact guideline wording), and a
candidate resolution for the prior run's long-standing citation #28 `BLOCKED_FOR_SOURCE` gap.
**What's been done:** Director's Wave 0 read-only spot-check (SHA-256/line-count match, internal
self-citation consistency, plausible PDF-extraction artifacts, partial topical cross-check against
the intake's own `adjudication_log_v2.md`) found it plausible but explicitly **not sufficient to
call it verified** — see Decision 2026-09-01-03.
**What's needed:** independent DOI resolution (doi.org/Crossref/PubMed, lawful metadata tools only);
a PDF-level (not just `.md`-derivative) spot-check of at least the claims this run will actually cite;
resolution of how it relates to DOI `10.1016/j.jacc.2025.11.016` (Q2 below).

## Q2 — Relationship between DOI `10.1161/CIR.0000000000001423` (Circulation, new) and DOI
`10.1016/j.jacc.2025.11.016` (JACC, prior run's citation #28)

**Status:** OPEN, `NEEDS_ANALYST`.
**Why it matters:** major ACC/AHA joint guidelines are sometimes simultaneously co-published across
multiple society journals (a real, known pattern) — but a mismatch could equally mean one citation is
wrong/fabricated (the JACC DOI has been unverifiable since Wave 1 of the prior run). Do not assume
either explanation; resolve via Crossref lookup on both DOIs and compare authorship/title/date.

## Q3 — Is `markdown/1-s2.0-S0735109725102544.md` (the intake's own self-cited "raw guideline
source," referenced by `adjudication_log_v2.md`, not present in this intake) obtainable or real?

**Status:** OPEN, `NEEDS_ANALYST`.
**Why it matters:** the intake's four claimed guideline corrections cite specific line numbers into
this file; Director's Wave 0 check found the *content* topically consistent with T-101 (the
`official/` file) at 3–4 of 4 checked points, but at *different* line numbers, suggesting this is a
distinct extraction/pagination of the same guideline, not a separate/fictional source — but this
remains unconfirmed. Ask the PI directly whether this file is available/known to them before
spending further search budget hunting for an Elsevier/JACC-PII-pattern filename that may only ever
have existed in another team's local environment.

## Q4 — How should the intake's own evidence-tier scheme interact with `CLAUDE.md` §7?

**Status:** OPEN, low priority, Director's provisional answer already recorded in
`00_RUN-MANIFEST.md`/`01_RESEARCH-CHARTER.md`: **not adopted** as this project's taxonomy; may be
recorded as a provenance cross-reference only. Revisit only if a specialist finds a case where this
provisional answer causes real friction.

## Q5 — Real-world evidence (RWE) for pitavastatin/ezetimibe FDC (focus area 2)

**Status:** OPEN — not yet searched this run. trials-efficacy-intelligence to determine at Wave 1
whether any RWE (registry, claims-database, or post-marketing observational study) exists beyond the
Phase III/FDC trial and the dose-comparison literature already known from the prior run.

## Carried forward from the prior run (still open, relevant to this run's focus areas)

- Taiwan STS 2026 consensus: citation verified, but the specific "ezetimibe as first add-on" content
  claim remains `BLOCKED_FOR_SOURCE` (PI-confirmed not assumed resolvable) — directly relevant to
  this run's focus area 1; re-check whether T-101 (if verified) or any other new source closes this.
- No trial has been found closing the Level 3 (pitavastatin/ezetimibe-specific hard-outcome) evidence
  gap beyond HIJ-PROPER's non-superior overall primary endpoint — directly relevant to this run's
  focus area 3 and the attack/defense section (focus area 5). Re-confirm no newer trial exists as
  part of Wave 1/2 search, do not assume the prior run's negative finding is still current without
  re-checking.
