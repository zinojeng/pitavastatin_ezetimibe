# Cross-session log — safety-pharmacology Wave 2 report + REAL-CAD verification — 2026-08-31

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Logged by: Research Director (`pit-eze-research-director`)

## IN — trials-efficacy-intelligence: T-016/REAL-CAD verified

Taguchi I, Iimuro S, Iwata H, et al., Circulation 2018;137(19):1997-2009, DOI
10.1161/CIRCULATIONAHA.117.032615, PMID 29735587. N=13,054, pitavastatin 4mg vs 1mg, Japanese
stable CAD, median follow-up 3.9y. Primary endpoint 266 (4.3%) vs 334 (5.4%), HR 0.81 (95% CI
0.69–0.95), P=0.01. Matches the secondhand citation exactly. Placed alongside T-015/REPRIEVE as a
second "pitavastatin itself has hard-outcome evidence" reference point, kept outside the FDC-specific
Level 1/2/3 framework. Q8 closed.

→ Decision (folded into 2026-08-31-19's close-out). `02_SOURCE-INVENTORY.md` T-016 row updated with
full verification.

## IN — safety-pharmacology-intelligence: Wave 2 completion report (condensed)

`READY_WITH_PENDING_ITEMS`. (1) T-012/Katzmann obtained lawfully via direct Europe PMC PMCID lookup
(PMC8873069, CC BY 4.0) — contradicts trials-efficacy's earlier `BLOCKED_FOR_SOURCE` finding via a
different method (Unpaywall + publisher link); both correct for their respective methods, not a
factual disagreement. (2) T-003/Singh 2024 confirmed `BLOCKED_FOR_SOURCE` (Europe PMC: no OA, no
PMCID). (3) T-010 DDI matrix re-verified directly against DailyMed: 5 figures unchanged/confirmed;
clarithromycin upgraded to `CONFIRMED_ABSENT_FROM_LABEL`; fenofibrate's correct location (Section
12.3 Table 3, not 7) found; new fibrate-class/niacin/colchicine content captured. (4) T-013
bibliographically verified via Crossref. Two unplanned finds: T-017 (Li H, Li J 2026, elderly
pitavastatin-vs-atorvastatin NODM cohort, n=126, abstract-only) and **T-018 (Tramontano D et al.
2025, CKD-dosing review, PMC12098426, CC BY-NC 4.0, cross-verified against the FDA label —
pitavastatin 1mg/2mg max in eGFR 15-59/HD, no adjustment eGFR≥60, lowest CKD ceiling of 7 statins
tabulated)** — resolves most of the Wave 1 CKD-dosing gap; FDC-specific CKD dosing remains
unaddressed by any source. BCRP gap partially converged (T-019/T-020, mechanism only, no
pitavastatin-specific fold-change number — still open). All three MCP tools (research_hub
search-only, llamaparse, paper-search sub-tools) confirmed working this session.

→ Decisions 2026-08-31-20 (Katzmann access-method correction + method tip relayed to other two
specialists), 2026-08-31-21 (T-010 refinements), 2026-08-31-22 (T-017/T-018, CKD gap mostly
resolved) added. `02_SOURCE-INVENTORY.md` T-003, T-010, T-012, T-013 updated; T-017, T-018, T-019,
T-020 added as new rows. `04_OPEN-QUESTIONS.md` reorganized accordingly.

## OUT — Director replies

To safety-pharmacology: commended the Katzmann find and CKD-gap resolution; asked it to pull the
Katzmann cohort-*n* from its own already-obtained full text to resolve Decision 2026-08-31-11,
since re-fetching via another role would be redundant.
To guideline-risk: relayed the Europe-PMC-PMCID method tip for its 3 remaining blocked sources.
To trials-efficacy: relayed the same tip for Chou MT 2022 (#33); confirmed REAL-CAD verification
received and Q8 closed; noted the Katzmann correction was a different-method result, not an error
on trials-efficacy's part.

## Status

All three specialists' primary Wave 2 assignments are now closed out. Outstanding: the PI's decision
on directly supplying the still-blocked PDFs (Taiwan STS 2026, ACC/AHA 2026, ESC 2025, Chou 2022);
safety-pharmacology's Katzmann cohort-*n* follow-up; guideline-risk's and trials-efficacy's
Europe-PMC-PMCID retries (not yet reported back as of this entry).
