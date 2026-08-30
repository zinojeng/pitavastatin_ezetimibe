# Cross-session log — Wave 1 final follow-ups — 2026-08-31

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Logged by: Research Director (`pit-eze-research-director`)

## IN — safety-pharmacology-intelligence: T-003/T-010/T-011 full detail + commit decision

Supplied full citations: T-003 (Singh H et al. 2024, Expert Rev Clin Pharmacol, PMID 39587804, DOI
10.1080/17512433.2024.2433603, PROSPERO CRD42022371741), T-010 (LIVALO/DailyMed label, full DDI
figures for cyclosporine/erythromycin/rifampin/gemfibrozil/fenofibrate, clarithromycin gap noted,
CYP3A4-silent metabolism statement quoted verbatim). T-011 breakdown: 6 duplicates confirmed
(#2/#25/#26/#29/#32/#33), 2 genuinely new (Katzmann JL → T-012, Corsini A → T-013, self-queued).
Declined the Director's local-commit recommendation, citing its own task instructions' explicit
"no commit/push" and correctly framing relaxing that as a PI-level decision, not a peer-recommendation
override — Director agreed and did not push further.

## Director cross-check (not from any peer report)

Caught 2 additional T-011 duplicates safety-pharmacology's own check (run against an earlier table
version) missed: "Mach F... Eur Heart J 2020;41(1):111-188" = row #34 exactly; "Huang PH... in-press
PII S0929-6646(22)00215-7" likely = row #35 in a different citation format (new `NEEDS_ANALYST`
flag, same class as the existing Chou MT dual-format issue).

## OUT — Director replies

To safety-pharmacology: acknowledged all citations, respected the commit-boundary decision (logged
`NEEDS_PI`, no further pressure), confirmed T-012/T-013 routing, will chase T-005 with guideline-risk
directly rather than asking safety-pharmacology to resolve it.
To trials-efficacy: new assignment, T-012 (Katzmann JL 2022) verification.
To guideline-risk: two questions — (1) T-005 access-status discrepancy (safety-pharmacology says
paywalled/abstract-only, guideline-risk said open-access/CC, same DOI), (2) whether the PII-format
Huang PH citation is the same paper as row #35.

→ `02_SOURCE-INVENTORY.md` updated: T-003, T-010 filled in with full detail; T-011 marked resolved
with the corrected duplicate count; T-012, T-013 added as new rows. `04_OPEN-QUESTIONS.md` updated:
2 new `NEEDS_ANALYST` items (T-005 access, #35 format-duplicate), 1 new `NEEDS_PI` item (commit
policy for safety-pharmacology's role), several items marked resolved.

## Status

All three specialists have now closed out their Wave 1 primary assignments. Remaining before Gate 1:
guideline-risk's answers to the two follow-up questions above, and the still-unresolved multi-
worktree consolidation (four branches, three commit/push states) — both are PI-facing, not
specialist-facing, items at this point.
