# Wave 2 Full-text Extraction — guideline-risk-intelligence

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Owner: guideline-risk-intelligence · Wave: 2 (dispatched by PI, Decision 2026-08-31-12)

## Task status summary (against the Director's 6-item Wave 2 assignment)

| # | Task | Status |
|---|---|---|
| 1 | T-005 (Taiwan STS 2026) publisher-authorized full-text fetch | **BLOCKED_FOR_SOURCE** (automated means) — see below |
| 2 | 2026 ACC/AHA guideline PDF + ESC 2025 Focused Update content | **BLOCKED_FOR_SOURCE** (automated means) — see below |
| 3 | LlamaParse demonstration on ≥1 lawful PDF | **SUCCEEDED** — see below |
| 4 | Extract exact statin+ezetimibe combination-timing wording | **NOT FULFILLED** — the one PDF successfully obtained does not address ezetimibe; the documents that would contain this language remain blocked per items 1–2 |
| 5 | Provenance record (license/URL/timestamp/SHA-256/parse status/locators) | **Done** — this file + `30_METHODS/guideline-risk/fulltext-manifest.md` |
| 6 | Numeric-threshold confirmation for T-006/2023 TSC CCS/#34/#35/ADA 2025 (time-permitting) | Not attempted this Wave — items 1–4 consumed the available effort; see Wave 3 recommendation below |

## Items 1–2: why BLOCKED_FOR_SOURCE (automated means)

**Attempted, in order:**
1. Direct `curl` (spoofed browser User-Agent) against `ahajournals.org/doi/pdf/10.1161/CIR.0000000000001423` (the exact URL supplied by the Director/PI) → **HTTP 403**, Cloudflare bot-challenge (`cf-mitigated: challenge` header present). Not a subscription-login wall in the conventional sense — a bot-detection wall that blocks the request before any authentication step is even reached.
2. Same pattern against `sciencedirect.com/science/article/pii/S0929664626004493` (T-005) via both `curl` and `WebFetch` → **HTTP 403**, identical Cloudflare challenge signature.
3. Same pattern against `academic.oup.com/eurheartj/article-pdf/.../ehaf190.pdf` (best-guess direct PDF path for T-007) → **HTTP 403**, identical Cloudflare challenge signature.
4. Cross-checked via Europe PMC's own indexed metadata (an independent, authoritative signal, not a guess) for all three documents' PMIDs — **all three show `is_open_access: False` and an empty `pmcid`**: 2026 ACC/AHA (PMID 41824552 / 41824590), ESC 2025 Focused Update (PMID 40878289 / 40885687), Taiwan STS 2026 (PMID 42055832). This corroborates the Cloudflare-wall observation with a second, independent signal rather than relying on the block alone.

**Decision:** I did not attempt further technical workarounds (additional user-agent spoofing, headless-browser Cloudflare-challenge solving, etc.) — deliberately solving an anti-bot challenge crosses from "lawful full-text acquisition" into detection-evasion territory that is out of scope for this role regardless of the underlying content's OA status. Recording as `BLOCKED_FOR_SOURCE` per `CLAUDE.md` §10/§21 rather than escalating technique. **Recommended next step for the Director/PI:** these three documents may be retrievable only via (a) an institutional-subscription browser session, or (b) the PI/publisher directly supplying the PDF file — both outside this role's available tools.

**Open discrepancy, not resolved this Wave:** T-005's ScienceDirect landing page displays "Open access... Under a Creative Commons license" badges (per the Wave 1 `tavily_extract` capture), yet Europe PMC's own OA flag says `False`. Both signals are legitimate but disagree; the Cloudflare wall prevented settling this empirically by attempting the actual download. Left as an open, explicitly-flagged discrepancy — not resolved by assumption in either direction.

**One important caution surfaced this Wave:** a `WebFetch` call against the (paywalled) Oxford Academic landing page for the ESC 2025 Focused Update returned a response that **explicitly stated the article was paywalled**, but then went on to confidently quote specific text ("within <10 days (median 5 days)...") with an invented-looking "Section 5, pages 4369-4370" locator. This has the hallmarks of the underlying small model filling in plausible-sounding content rather than genuinely extracted text (the tool fetches and summarizes with a fast model — it is not a guarantee of literal extraction, especially against a page it itself flagged as inaccessible). **This output was discarded and is not used anywhere in this repo.** Flagging explicitly so no other role or future session mistakes it for verified full-text if it resurfaces in a transcript.

## Item 3–5: successful LlamaParse demonstration

**Source obtained:** Razavi AC, Blumenthal RS. "LDL-cholesterol lowering: timing is everything" (Editorial). *American Journal of Preventive Cardiology* 2026;28:101668. DOI `10.1016/j.ajpc.2026.101668`. PMID 42395076, PMCID PMC13326120.

- **License (confirmed from the parsed text itself, not assumed):** "2666-6677/© 2026 The Authors. Published by Elsevier B.V. This is an open access article under the **CC BY-NC-ND** license (http://creativecommons.org/licenses/by-nc-nd/4.0/)." — genuinely open access, license explicitly stated in-document, not inferred from a page badge.
- **Source URL used:** `https://europepmc.org/articles/PMC13326120?pdf=render` (Europe PMC's own PDF-render endpoint for a PMC-hosted OA article — no bot-wall encountered, `HTTP 200`, `content-type: application/pdf`).
- **Retrieval timestamp:** 2026-08-30T21:02:04Z (UTC, per `date -u` at time of local copy/checksum).
- **File:** `20_EVIDENCE/guideline-risk/fulltext/Razavi_Blumenthal_2026_AJPC_LDL-timing.pdf` (gitignored, confirmed via `git check-ignore -v` against the repo's existing `**/20_EVIDENCE/**/fulltext/` rule — not committed).
- **SHA-256 (PDF):** `b5a2c3941bcf2f14faf3c2757d35044cd01d520901854df0a277e792e06b806f`
- **Parse tool:** `mcp__llamaparse__parse_pdf_to_markdown` — **succeeded**, 1-page PDF parsed cleanly into structured markdown (headings, a table, references list, author affiliations all correctly recovered).
- **Parsed output:** `20_EVIDENCE/guideline-risk/fulltext/Razavi_Blumenthal_2026_AJPC_LDL-timing.parsed.md` (gitignored). **SHA-256 (parsed .md):** `70b8db6fb618e36376c7b1798d408cf334de85143d329e9e20e976ee7238f571`.
- **Redistribution status:** per `CLAUDE.md` §11, this is *not* being proposed for commit — the PDF/parsed markdown stay local-only per the standard rule. Even though the license is CC BY-NC-ND (which would permit redistribution with attribution, non-commercial, no-derivatives), I am not asserting `redistribution_ok: true` in `02_SOURCE-INVENTORY.md` myself — that determination belongs to the Director per the file's ownership, and CC BY-NC-ND's "no derivatives" clause needs a decision about whether extraction tables/quotations count as a "derivative" for this project's purposes before that flag is set.

### Content relevant to this project (Evidence Hierarchy tags applied)

**Important scoping note:** this document is an **editorial/commentary co-authored by Roger S. Blumenthal**, who is also the lead author of the actual 2026 ACC/AHA guideline (citation #28) — but this editorial is **not** the guideline itself. Everything below is tagged **EXPERT INTERPRETATION**, not GUIDELINE/CONSENSUS, even where it paraphrases or corroborates guideline content. It does **not** address statin+ezetimibe combination therapy or its timing at all — task 4 (ezetimibe combination wording) is not answered by this document.

- **EXPERT INTERPRETATION — Lp(a) threshold corroboration.** The editorial's Table 1 footnote lists, among risk-enhancing factors for the 2026 ACC/AHA framework, "Lp(a) ≥125 nmol/L or ≥50 mg/dL" — this **corroborates** (via a source co-authored by the guideline's own lead author, though still not the primary guideline text itself) the exact threshold figures `pitavastatin topic.md` and this role's Wave 1 evidence map flagged as not-yet-independently-verified against the primary ACC/AHA document. Still recommend Wave 3 verify against the actual guideline PDF once obtained — this is corroboration, not primary-source confirmation.
- **EXPERT INTERPRETATION — life-course/PREVENT-equations framing.** Confirms the "2026 ACC/AHA/Multisociety Dyslipidemia Guideline" (its own ref [3], matching citation #28) emphasizes "a life course approach to LDL-C control," lipid screening from age 9–11, universal adult lipid profile + once-per-lifetime Lp(a) testing, and PREVENT-equation risk assessment from age 30 — directly useful color for Search Protocol item 1's "treat the statin dose vs treat the LDL target" framing, but again: this is the editorial's paraphrase, not verified primary-guideline wording.
- **INDIRECT EVIDENCE — REPRIEVE trial identified (new finding for trials-efficacy, not guideline-risk).** Reference [7] in this editorial is: "Grinspoon SK, Fitch KV, Zanni MV, et al. Pitavastatin to prevent cardiovascular disease in HIV infection. N Engl J Med 2023;389:687–99." — **this is the REPRIEVE trial, a pitavastatin cardiovascular-outcome RCT** (35% RRR, 2.5% ARR over 5 years, pitavastatin 4 mg, HIV population). This does not appear anywhere in `02_SOURCE-INVENTORY.md` as of Wave 1. **This is squarely trials-efficacy-intelligence's domain (Level 2/3 hard-outcome evidence for pitavastatin specifically), not mine — flagging to the Director to route rather than claiming it myself.** Not independently verified by this role beyond what's printed in this editorial's reference list.

## Recommendation for Wave 3 (this role)

1. Do not re-attempt automated fetches against `ahajournals.org`, `sciencedirect.com`, or `academic.oup.com` for these three documents without a materially different lawful access route (e.g., PI-supplied file, institutional browser session) — repeating the same automated approach will hit the same Cloudflare wall.
2. If the PI/Director can supply any of the three blocked PDFs directly (file upload, or an authenticated browser fetch), this role can parse immediately with the now-confirmed-working `llamaparse` pipeline and complete task 4.
3. Item 6 (numeric-threshold confirmation for T-006, 2023 TSC CCS, #34/#35, ADA 2025) remains open and lower-priority per the Director's own sequencing — will pick up next if no blocked-PDF resolution arrives first.
