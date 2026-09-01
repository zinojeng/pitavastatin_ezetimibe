# Time-boxed re-check — Taiwan STS 2026, ESC 2025 Focused Update, Taiwan Lp(a) 2026

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-09-01-v1`
Owner: guideline-risk-intelligence · Wave 1, per Director's follow-up dispatch (`01_RESEARCH-
CHARTER.md` "major uncertainty" items)

Time-boxed per instruction: first-pass search via lawful sources only (`research_hub`
metadata-search, direct Crossref/Unpaywall API calls — `paper-search`/`tavily`/`openevidence`
unavailable this session, see `search-log.md`). No new access route found for any of the three; all
three remain `BLOCKED_FOR_SOURCE` for full text. One genuinely new, useful finding on OA status.

## Taiwan STS 2026 consensus (Wu YJ et al., J Formos Med Assoc 2026, DOI `10.1016/j.jfma.2026.04.111`)

- `research_hub search_papers` — same record as the prior run, no new access route surfaced.
- **New finding: Unpaywall (`api.unpaywall.org`, free/no-auth) now reports `is_oa: true`,
  `oa_status: gold`, `license: cc-by`** — this is an independent, authoritative confirmation that the
  prior run's "landing page shows OA/CC badges vs. Europe PMC says not OA" discrepancy is now
  resolved: **the article genuinely is Gold Open Access, CC BY**, consistent with Crossref's own
  license metadata for this DOI showing a CC BY 4.0 grant taking effect ~21 days after the
  version-of-record publication date (i.e., an initial embargo that has since lifted).
- **Still `BLOCKED_FOR_SOURCE` for full text, despite confirmed genuine OA status.** Followed the
  full redirect chain: `doi.org` → `linkinghub.elsevier.com` (200, JS meta-refresh) →
  `sciencedirect.com/science/article/pii/S0929664626004493` (**HTTP 403, Cloudflare bot-challenge**,
  with session cookies carried through the chain). The block is bot-detection, not a subscription
  paywall — genuine OA status does not bypass it for automated fetches. No further technique
  attempted (consistent with this project's standing policy against escalating past a bot-wall).
- **Net effect:** `BLOCKED_FOR_SOURCE` status stands, but the *reason* is now more precisely
  characterized (bot-wall, not paywall/access-rights uncertainty) and the OA-status question that
  was an open discrepancy in the prior run is now closed. Worth recording in
  `02_SOURCE-INVENTORY.md` as a status refinement, not a new blocker.

## ESC 2025 Focused Update (Mach F et al., DOI `10.1093/eurheartj/ehaf190`)

- `research_hub search_papers` — same set of results as the prior run (base EHJ publication, the
  parallel Atherosclerosis co-publication DOI `10.1016/j.atherosclerosis.2025.120487`, a correction
  notice, and several secondary commentaries including one new one worth noting for context:
  "How Applicable is the 2025 Focused Update... to the Asia-Pacific Region?" DOI
  `10.15420/japsc.2025.80` — not fetched/verified this Wave, flagged only as a possible future
  secondary-source lead for the Asia/Taiwan-relevance angle of this project, tagged
  `EXPERT INTERPRETATION` if ever used, not `GUIDELINE/CONSENSUS`).
- No new access route found; not re-attempted against Oxford Academic (same Cloudflare pattern
  established in the prior run). Remains `BLOCKED_FOR_SOURCE`.

## Taiwan Lp(a) 2026 consensus (Cheng CY et al., DOI `10.1016/j.jfma.2026.03.073`)

- `research_hub search_papers` did not resurface this specific record this session (result set was
  dominated by unrelated matches) — not a negative finding about the source itself, just this query
  attempt; the DOI/PMID from the prior run's verification stand unchanged.
- Not independently re-checked via Unpaywall/Crossref this Wave (time-boxed; the STS recheck above
  was the higher-priority target given it directly bears on this run's central "ezetimibe as first
  add-on" claim). Remains `BLOCKED_FOR_SOURCE`, unchanged from the prior run.

## Bottom line

None of the three primary documents were obtained this Wave. Time-boxed as instructed — stopping
here rather than continuing to search. **Decision 2026-09-01-05's stepwise-vs-upfront-combination
finding (from T-101, the now-verified 2026 ACC/AHA guideline) is unaffected by any of this** — it
does not depend on these three still-blocked sources and stands on its own primary-source basis.
