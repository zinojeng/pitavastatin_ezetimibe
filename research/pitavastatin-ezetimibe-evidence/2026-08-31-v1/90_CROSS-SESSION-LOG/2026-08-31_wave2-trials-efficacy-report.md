# Cross-session log — trials-efficacy-intelligence Wave 2 report — 2026-08-31

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Logged by: Research Director (`pit-eze-research-director`)

## IN — trials-efficacy-intelligence Wave 2 report (condensed; full text in transcript)

`READY_FOR_NEXT_WAVE`. Tsujita 2023 (T-004a) and Ako 2024 (T-004b) full text obtained via J-STAGE
(PMC's proof-of-work anti-bot challenge blocked the supplied PMC IDs; not attempted to solve, lawful
alternate source used) and LlamaParse-parsed successfully (114,893 and 107,117 characters, no
truncation). Extracted: exact arm structure (293 randomized → 288 analyzed, 72/arm); statistical
structure resolved as pairwise MMRM — the FDC-internal dose-response comparison (K-924 HD vs LD) was
formally tested and significant, but the "add ezetimibe vs double the statin" comparison
`pitavastatin topic.md` frames as a headline question was **not** formally tested, only descriptive;
full AE/CK/AST/ALT tables; and Ako 2024's true AE picture (59.6% overall, only 1 adjudicated ADR)
is broader than its abstract's "single ADR" framing suggests. Chou 2022 (#33) and Katzmann 2022
(T-012) both confirmed `BLOCKED_FOR_SOURCE` on retry post-connectivity-repair (no OA location, a
direct HTTP check on Katzmann's Springer PDF URL returned an access-restriction page). T-015/REPRIEVE
fully verified (N=7,769, MACE HR 0.65, stopped early for efficacy) with a cross-domain diabetes-
signal-framing nuance flagged for safety-pharmacology. New candidate source found secondhand:
REAL-CAD (T-016), logged as its own Q8, asked whether to pursue.

→ Decisions 2026-08-31-16 (add-eze-vs-double-statin not formally tested), 2026-08-31-17 (AE-vs-ADR
distinction), 2026-08-31-18 (REPRIEVE full verification), 2026-08-31-19 (REAL-CAD, authorized to
pursue) all added. `02_SOURCE-INVENTORY.md` T-004a/T-004b/#33/T-012/T-015 updated; T-016 added.
`05_STATUS.md`: **both Gate-2 LlamaParse requirements now confirmed satisfied** (trials-efficacy on
the actual assigned target, guideline-risk on a substitute).

## OUT — Director replies

To trials-efficacy: commended the PMC-bot-avoidance judgment, the two overclaim-prevention catches
(Decisions 16/17), and the REPRIEVE handling; authorized independent pursuit of REAL-CAD; confirmed
its Wave 2 assignment is fully closed out.
To safety-pharmacology: relayed the REPRIEVE diabetes-signal framing nuance for its awareness when
it reaches glycemic-outcomes synthesis (informational, not urgent).

## Status

safety-pharmacology has not yet reported its Wave 2 results as of this entry. One PI-facing question
remains outstanding (whether the PI can supply the Cloudflare/paywall-blocked PDFs directly) — see
`04_OPEN-QUESTIONS.md`.
