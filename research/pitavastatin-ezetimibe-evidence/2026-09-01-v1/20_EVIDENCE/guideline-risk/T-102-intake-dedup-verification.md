# T-102 — Google Drive intake dedup and cross-reference verification

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-09-01-v1`
Owner: guideline-risk-intelligence · Wave 1, priority 3 (per Director's follow-up dispatch)

Scope, per the Director's instructions: dedupe the 34-file bundle, confirm nothing in it materially
contradicts the now-VERIFIED T-101 primary source (flag real conflicts, don't quietly prefer T-101
without noting), identify content T-101 doesn't cover, confirm the byte-identical
`adjudication_log_v2.md` pair needs no separate treatment. **Not** a heavy re-verification pass —
T-101 is now the load-bearing source; this is secondary-material triage.

## 1. Dedup table (latest-timestamp file per "topic slot," per `MANIFEST.md`)

| Slot | Versions | Latest (kept) file ID | Latest timestamp |
|---|---|---|---|
| `00_master_comparison` | 4 | `11yQPwzaGS5IVj7abcTHeGQkJvQVVnkQh` | 2026-03-16T18:10:46Z |
| `01_risk_targets` | 3 | `1K5CsKGQLhLSpTv6yNu20apf6ScX0RtQi` | 2026-03-16T04:27:53Z |
| `00_quick_reference_card` | 3 | `1JNOsb3pmfDtiWosZTYtwFzMbTKCqHgA0` | 2026-03-16T04:27:12Z |
| `05_monitoring_lifestyle` | 3 | `16xsqtzk-rD_7oiJFk1M6UToMsIWsUw0i` | 2026-03-16T04:27:00Z |
| `02_pharmacotherapy` | 3 | `1oEWcA-bSUNPiwrNSYc1nrmVKHodgQGyk` | 2026-03-16T04:26:30Z |
| `03_special_populations` | 3 | `1rbj--pB1JcG5bMrsorXb4JtvRdKdof6K` | 2026-03-16T04:26:19Z |
| `differences_summary` | 3 | `16h0M7VzYvCjqmHLvwxJsupbSfnp6KT0V` | 2026-03-16T04:22:29Z |
| `04_evidence_key_trials` | 3 | `1EPQFxW85pso5yY0EeF_AEuoWShOTabOa` | 2026-03-16T04:29:36Z |
| `confidence_map` | 2 | `1ZgPQllh5xIhZ88j5jNcM6peKtkFqVtxk` | 2026-03-16T04:19:18Z |
| `adjudication_log_v2` | 2 | `1iZ5z7JpSPKYGtCgXqb3pMBXDw0SmwCuu` | 2026-03-16T04:17:46Z |

Plus 5 unique `draft_11_12` / `draft_13_14` / `draft_15_16` / `draft_17_18` / `draft_19_20.md` files
(no dedup needed — each covers a distinct topic-number range, confirmed by sampling `draft_11_12.md`:
covers topics #11–12, familial hypercholesterolemia). **Deduped working set: 15 files** (10 latest
slot-versions + 5 unique drafts) out of the original 34.

**`adjudication_log_v2.md` duplicate pair:** confirmed no separate treatment needed. The Director's
Wave 0 byte-identical SHA-256 finding stands — both copies (`1iZ5z7JpSPKYGtCgXqb3pMBXDw0SmwCuu` and
`1kSqP4HeCkQa8gy1aJqravEKSKReepv-T`) are the literal same file content; using the latest-timestamp
one per the general dedup rule is arbitrary but correct (either copy reads identically).

## 2. Cross-reference against T-101 — no unresolved SOURCE_CONFLICT, but one real self-correction

**Read in full:** `00_quick_reference_card.md` (latest version, 160 lines) — a dense, well-organized
zh-TW "2018 vs 2026" comparison table covering risk assessment, LDL-C targets, pharmacotherapy,
special populations, monitoring, new/removed recommendations, and acknowledged evidence gaps.

**Discrepancy found and resolved — in my own favor being wrong, not the intake's:** the
quick_reference_card states "Ezetimibe（VHR ASCVD，statin 後）| 2a, B-R（必須先於PCSK9i）| **1, A**
（排序要求取消）" — i.e., 2026 COR 1 for ezetimibe add-on at very-high-risk, with the ezetimibe-
before-PCSK9i sequencing requirement removed. **My own Wave 1 `focus-area-1-guideline-wording.md`
had this recommendation mis-graded as COR 2a** (a `pdftotext -layout` column-alignment misread from
an insufficiently wide extraction window). Re-extracted directly from T-101 with a wider context
window: **the intake was correct — COR 1, LOE A** — and the "sequencing requirement removed" language
is also directly confirmed in T-101's own synopsis text ("the revised recommendations no longer
require that ezetimibe be added to statin therapy prior to initiating a PCSK9 mAb"). **Fixed in
`focus-area-1-guideline-wording.md` with a transparent correction note, not silently changed.** This
is exactly the kind of cross-check value the Director anticipated in assigning this task even though
T-101 is now primary — logged as a positive example of the dedup pass catching my own error, not
just the intake's.

**Independently spot-verified 2 of the `adjudication_log_v2.md`'s 4 claimed "v1.1→v1.2" corrections
directly against T-101** (the log's own claims about what the *current*, already-corrected intake
files should say — checking whether the correction itself is accurate, not re-litigating the log's
history):

| # | Claim (as stated, already applied in current files) | Checked against T-101 | Result |
|---|---|---|---|
| 1 | CAC 300–999 AU: two-tier target — standard COR 1 (LDL-C <70, non-HDL-C <100) **and** optional-intensified COR 2a (LDL-C <55, non-HDL-C <85, "adding ezetimibe, a PCSK9 mAb or bempedoic acid") | Located both recommendations verbatim in T-101 (Section 4.2.7) | **CONFIRMED, exact match** |
| 3 | HFrEF: three-way split — (a) no ASCVD/no other LLT indication → COR 3 No Benefit, LOE A; (b) ischemic-etiology HFrEF → COR 2b, LOE B-R for initiation | Located both verbatim in T-101 (Section 4.2.8.6) | **CONFIRMED, exact match** |

Items #2 (dialysis initiation-vs-continuation split) and #4 (older-adults COR 2a→2b correction)
were **not** independently re-verified this Wave — `grep` located the relevant T-101 passages
(dialysis: lines ~5390–5460; older adults not specifically re-located) but full verbatim confirmation
was not completed, given the Director's explicit instruction not to over-invest here after the
primary source is already verified. **Not flagged as a problem — simply not exhaustively checked.**
If either topic becomes load-bearing for `40_SYNTHESIS/` or `50_MANUSCRIPT/`, recommend a targeted
follow-up check before citing, same as any other unverified-but-plausible secondary claim.

**No SOURCE_CONFLICT requiring PI escalation was found.** The one discrepancy located was this role's
own transcription error, now corrected transparently — not a case of the intake being wrong.

## 3. Content the intake covers that T-101 does not (useful for the zh-TW brief later)

- **Native, well-structured Traditional Chinese framing** of the entire 2018→2026 comparison,
  including a symbol legend (🆕/✏️/📊/🔄/➕/🔀/❌/💊 for change type) and an explicit "acknowledged
  evidence gaps" section (inclisiran CVOT pending, Lp(a)-lowering CV benefit unproven, CAC-tiered
  target lacks RCT support, icosapent ethyl mineral-oil-placebo controversy, very-low-LDL-C long-term
  neurocognitive safety) — genuinely useful, well-organized secondary framing for the zh-TW brief
  deliverable, tagged `EXPERT INTERPRETATION` (AI-drafted secondary synthesis), not `GUIDELINE/
  CONSENSUS`, per this run's dual-tagging requirement.
- **Per-topic deep-dive narrative files** (`draft_11_12.md` sampled: FH-specific reforms — PCE
  banned as COR 3: Harm, PCSK9 mAb upgraded to COR 1, genetic testing COR 1/2a, pediatric statin age
  lowered to ≥8y, evinacumab added for HoFH) — direct 2018-vs-2026 quote pairs with zh-TW narrative
  bridging them. Tangential to this project's core pitavastatin/ezetimibe focus (FH is a distinct
  population) but potentially useful supporting/contextual material if the zh-TW brief needs broader
  guideline-landscape framing.
- **`confidence_map.md`** — the intake's own evidence-confidence tiering (`direct_guideline /
  trial_supported / observational_extrapolation / future_direction`) applied per-claim across its
  files. Per Decision (Q4, already resolved by the Director): **not adopted** as this project's
  taxonomy; may be recorded as a provenance cross-reference only if a specific claim from the intake
  is ever cited.

## 4. Recommendation

- No blocking issues found. The deduped 15-file set is internally consistent with T-101 wherever
  spot-checked, and materially useful as secondary zh-TW framing/context for later deliverables — but
  every clinically material claim drawn from it must still be tagged no higher than `EXPERT
  INTERPRETATION` and independently checked against T-101 (or another primary source) before it
  enters `20_EVIDENCE/` at a higher tier, per Decision 2026-09-01-03/`01_RESEARCH-CHARTER.md`.
- Suggest the Director treat T-102 as closed for Wave 1 purposes; a full read-through of the
  remaining 13 files (beyond the two sampled here) is better deferred to whenever the zh-TW brief is
  actually drafted, rather than done speculatively now.
