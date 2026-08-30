# search-log — trials-efficacy-intelligence / Wave 1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Role: trials-efficacy-intelligence · Wave: 1（Source / Evidence Verification）
Session: `pit-eze-trials-efficacy`

## Cross-session health check（Runbook §12–13）

1. `ListAgents` — 確認本 session 為 `pit-eze-trials-efficacy`；可見 peers：
   `pit-eze-safety-pharmacology`（busy）、`pit-eze-guideline-risk`（busy）、
   `pit-eze-research-director`（idle）。三個必要 peer（Director + 兩位同儕 specialist）
   均為可通訊 socket，非僅 session history。
2. 檢查 `90_CROSS-SESSION-LOG/` — 尚無既有紀錄，本 session 為第一個寫入者。
3. Wave 1 起點依 CLAUDE.md §10 重新確認 MCP 連線狀態（Wave 0 記錄 `research_hub` /
   `llamaparse` / `openevidence` 三者失敗）：
   - `research_hub`：**已恢復連線**（`search_papers`／`download_paper` 可正常呼叫，見下）。
   - `llamaparse`：連線已建立（`parse_pdf_to_markdown` 工具可用），本次 Wave 1 未產生需要
     LlamaParse 解析的已下載 PDF（見 `fulltext-manifest.md` 的下載失敗紀錄），故未實際呼叫。
   - `openevidence`：**仍為 CONNECTION_CLOSED**，本次 Wave 1 未使用（不可用，非本角色可修復
     的問題，已忠實記錄，未嘗試繞過）。
   - `paper-search`（PubMed/PMC/Crossref/Europe PMC/Unpaywall 等子工具）、`tavily`、
     `google-scholar`：正常可用，為本次 Wave 1 主要使用來源。
4. 依 CLAUDE.md §6 格式，向 Research Director 送出 CROSS_SESSION_TEST + STATUS_REPORT（見
   `90_CROSS-SESSION-LOG/`），確認本角色進入 Wave 1 Source/Evidence Verification。

## 檢索策略

Scope 依 CLAUDE.md §5（Prioritized Search Protocol）第 5、6、7、8、9 項（trials-efficacy 主責）
以及第 3 項（safety-pharmacology 主責、trials-efficacy 需交叉引用）。分兩軌：

- **軌道 A（Wave 1 — 驗證舊引用）**：針對 `02_SOURCE-INVENTORY.md` 中已標記
  `assigned owner = trials-efficacy` 的既有 `Tonvasca_2026.md` 引用（citation #19, #20, #21,
  #22, #25, #26, #33），逐條以 DOI/PubMed/Crossref 解析、比對期刊/年份/卷期頁碼/作者，並比對
  `Tonvasca_2026.md` 中已抄錄的數字（LDL-C % change、HR、95% CI、P value）。
- **軌道 B（Wave 1/2 — 補齊 `pitavastatin topic.md` 點名但尚未定位的來源）**：
  `02_SOURCE-INVENTORY.md` 中 T-001（HIJ-PROPER）、T-002（RACING）、T-004（2 mg vs 4 mg /
  add-ezetimibe vs dose-escalation）；T-003（NODM meta-analysis）與 safety-pharmacology 共管，
  僅做初步定位交叉引用，不做完整驗證（避免重複另一角色的工作，Runbook §31）。

## 使用的合法 MCP 來源（CLAUDE.md §10 允許清單內）

`mcp__paper-search__search_pubmed` / `search_crossref` / `get_crossref_paper_by_doi` /
`search_europepmc` / `search_pmc`；`mcp__research_hub__search_papers` /
`download_paper`；`mcp__tavily__tavily_search`。未使用、亦未嘗試使用 `scihub` 或
`download_scihub`（CLAUDE.md §10 明文禁止）。

## 檢索紀錄（依主題分組，非逐字 query log）

| # | 主題 / Search Protocol item | 查詢方向 | 結果摘要 | 對應 citation_id |
|---|---|---|---|---|
| 1 | Chou MT et al. Phase III FDC trial 定位與驗證（item 7） | `mcp__research_hub__search_papers` "Chou pitavastatin ezetimibe fixed dose combination Clin Ther 2022"；`mcp__paper-search__get_crossref_paper_by_doi` 驗證 DOI | 找到並以 Crossref 確認：標題、作者、期刊卷期頁碼與 `Tonvasca_2026.md` 引用字串完全相符 | TE-001 |
| 2 | 同一 Phase III 家族的**日本**獨立試驗，含 2 mg vs 4 mg 劑量比較（item 5） | `mcp__research_hub__search_papers` 同一查詢的相鄰結果；`mcp__paper-search__get_crossref_paper_by_doi`；`mcp__paper-search__search_pubmed` "Tsujita Yokote Ako pitavastatin ezetimibe fixed-dose combination Japan phase III" | 找到 Tsujita K et al. J Atheroscler Thromb 2023（K-924 4-arm RCT：pitavastatin 2mg / 4mg / 2mg+eze10mg / 4mg+eze10mg），**直接回答 Search Protocol item 5** | TE-002 |
| 3 | K-924 長期（52 週）延伸試驗 | 同上 PubMed 查詢的相鄰結果 | 找到 Ako J et al. J Atheroscler Thromb 2024（open-label extension） | TE-003 |
| 4 | HIJ-PROPER 主要發表與數字核對（item 6, 9） | `mcp__paper-search__search_pubmed` "HIJ-PROPER pitavastatin ezetimibe acute coronary syndrome" | 找到 rationale/design 論文（Kawada-Watanabe 2017）與**主要結果論文**（Hagiwara N et al. Eur Heart J 2017）；主要結果論文 abstract 中之數字與 `pitavastatin topic.md`／`Tonvasca_2026.md` 完全一致 | TE-004 |
| 5 | HIJ-PROPER 相關 substudy（非本次驗證重點，僅記錄存在） | 同上查詢的相鄰結果 | 另有 4 篇 substudy（單/多血管病灶、EPA/AA、心衰竭、sitosterol 表型延伸）被檢出，未逐一驗證，列入 `unresolved-questions.md` 供 Wave 2 判斷是否需要 | — |
| 6 | RACING 主要試驗與數字核對（item 8） | `mcp__paper-search__search_pubmed` "RACING trial rosuvastatin ezetimibe moderate-intensity vs high-intensity statin"；後以 "RACING trial Lee rosuvastatin ezetimibe statin monotherapy Lancet 2022 randomized" 精確定位主文 | 找到主要結果論文（Kim BK et al. Lancet 2022）；abstract 數字與 `pitavastatin topic.md` 完全一致 | TE-005 |
| 7 | RACING DM 次族群（item 8） | `mcp__paper-search__search_pubmed`（未命中，PubMed 索引詞不符）→ `mcp__paper-search__search_europepmc` → `mcp__tavily__tavily_search` "RACING trial diabetes subgroup analysis rosuvastatin ezetimibe MACE 10.0% 11.3%" | 找到 Lee YJ et al. Eur Heart J 2023;44(11):972-983（pre-specified DM subgroup, n=1398）；數字與 `pitavastatin topic.md` 完全一致（見 extraction-table） | TE-006 |
| 8 | Sydhom et al. 統合分析定位與驗證（item 8, 交叉 safety-pharmacology） | `mcp__paper-search__search_pubmed` "Sydhom meta-analysis low moderate intensity statin ezetimibe..."；`mcp__paper-search__get_crossref_paper_by_doi` | 找到並確認：BMC Cardiovasc Disord 2024;24(1)，與 `Tonvasca_2026.md` 引用字串相符 | TE-007 |
| 9 | 2024 NODM meta-analysis（item 3，safety-pharmacology 主責，交叉核對） | `mcp__paper-search__search_pubmed` "pitavastatin new-onset diabetes systematic review meta-analysis atorvastatin rosuvastatin" | 找到 Singh H et al. 2024（`pitavastatin topic.md` 中泛稱的「2024 systematic review/meta-analysis」極可能即此篇），**已轉知 safety-pharmacology**（非本角色最終驗證責任） | （safety-pharmacology 主責） |
| 10 | Boekholdt 2014 JACC 驗證（item 9, citation #19） | `mcp__paper-search__search_pubmed` "Boekholdt very low levels atherogenic lipoproteins..." | 找到並以 PubMed 確認：標題/期刊/DOI 相符 | TE-008 |
| 11 | T-SPARCLE（Yeh et al.）驗證（citation #22） | `mcp__paper-search__search_pubmed` "T-SPARCLE Taiwan lipid registry Yeh PLoS One 2017" | 找到並確認：標題/期刊/DOI/年份相符 | TE-009 |
| 12 | CEPHEUS（citation #20）、DYSIS-II（citation #21）、Masana 2020（citation #25）驗證 | 多輪 `search_pubmed` / `search_crossref`（見下） | **未能定位與 `Tonvasca_2026.md` 引用字串逐字相符的原始文獻**；找到之相近文獻journal/vol/page 與引用字串不符，見 `unresolved-questions.md` | 未指派 TE-id，列為未驗證 |
| 13 | Chou 2022 全文取得嘗試 | `mcp__research_hub__download_paper`（DOI）| 下載失敗（13 個資料庫均未收錄可下載全文；Elsevier 全文付費牆）；未嘗試 Sci-Hub | — |
| 14 | `Tonvasca_2026.md` 未讀完剩餘段落（04_OPEN-QUESTIONS 待辦） | `Read` 工具直接讀取 line 1680–2811（本 Wave 0 未讀完的剩餘 36%） | 補齊 Phase III FDC trial 之 AE 表格（見 extraction-table）與 DDI/ADR 段落（歸 safety-pharmacology）；未發現額外未登記之 trials-efficacy 引用 | — |

## Coverage 統計摘要（Director bookkeeping 要求，2026-08-31 追加）

- 本角色被指派的 `Tonvasca_2026.md` 既有 legacy citation 共 7 筆（#19, #20, #21, #22, #25, #26,
  #33）：**4 筆已定位並驗證**（→ TE-008, TE-009, TE-007, TE-001）、**3 筆未能定位**
  （#20 CEPHEUS, #21 DYSIS-II, #25 Masana 2020 — 未指派 TE-id，見 `unresolved-questions.md` Q5）。
- 另有 5 個 TE-id 為 `pitavastatin topic.md` 直接點名的主要試驗與 Wave 1 新找到的來源，**不屬於**
  上述 7 筆 legacy citation：TE-004（HIJ-PROPER）、TE-005（RACING 主文）、TE-006（RACING DM
  次族群）、TE-002（Tsujita 2023，新發現）、TE-003（Ako 2024，新發現）。
- 兩組計數為互不重疊：4（已驗證 legacy）+ 3（未定位 legacy）= 7（全部 legacy 指派）；
  4（已驗證 legacy）+ 5（topic-notes 主要試驗 + 新發現）= 9（extraction-table.csv 中的 TE-id 總數）。

## 新發現來源之完整格式化引用（Director 要求，2026-08-31 追加）

- Tsujita K, Yokote K, Ako J, Tanigawa R, Tajima S, Suganami H. Efficacy and Safety of
  Pitavastatin/Ezetimibe Fixed-Dose Combination vs. Pitavastatin: Phase III, Double-Blind,
  Randomized Controlled Trial. *J Atheroscler Thromb*. 2023;30(11):1580-1600.
  DOI: 10.5551/jat.64006. PMID: 36908150. ClinicalTrials.gov: NCT04289649.
- Ako J, Yokote K, Tsujita K, Tanigawa R, Kamei R, Suganami H. Long-term Efficacy and Safety of
  K-924 Pitavastatin/Ezetimibe Fixed-dose Combination in Patients with Hypercholesterolemia: A
  Phase III, Multi-center, Open-label Trial. *J Atheroscler Thromb*. 2024;31(3):288-305.
  DOI: 10.5551/jat.64272. PMID: 37722882.

（vol/issue/page 皆以 Crossref `get_crossref_paper_by_doi` 直接取得，非轉錄自二手來源。）

## Wave 2 全文取得與解析紀錄（2026-08-31，PI 授權 Decision 2026-08-31-12）

依 Director／PI 指派，重新確認 `research_hub`／`llamaparse` 連線（皆已修復，`llamaparse` 通過
dummy-PDF smoke test）後執行：

1. **TE-002（Tsujita 2023）**：以 Director 提供的 J-STAGE URL 直接下載官方 PDF（`curl`，非
   research_hub／scihub），取得 10 頁真實 PDF（717,939 bytes），SHA-256 見
   `fulltext-manifest.md`。以 `mcp__llamaparse__parse_pdf_to_markdown` 解析成功（114,893 字元）
   — **此為 Director 指定的 Gate 2 LlamaParse 示範案例之一，已確認成功**。萃取結果見
   `10_DATA/trials-efficacy/wave2-fulltext-extraction.md`。
2. **TE-003（Ako 2024）**：Director 僅提供 PMC ID（PMC10918028）；本角色由 TE-002 的 J-STAGE
   URL pattern（`article/jat/advpub/0/advpub_<DOI後綴>/_pdf`）推導出對應 URL 並驗證下載成功
   （321,262 bytes 真實 PDF）。以 LlamaParse 解析成功（107,117 字元）。
3. **PMC 直接下載嘗試（先於上述 J-STAGE 方案）**：依 Director 提供的 PMC ID
   （PMC10627746／PMC10918028）嘗試直接 `curl` PMC PDF 端點，兩者皆被 PMC 的
   proof-of-work（POW）反機器人機制攔截（回傳 JS challenge 頁面，非真實 PDF）。**未嘗試破解此
   POW challenge**（此非合法來源存取限制，而是反爬蟲機制，破解會落入 detection-evasion 範疇，
   本角色主動避免），改用 Director 提供的 J-STAGE 官方連結，成功取得相同內容的官方版本。
4. **TE-001（Chou 2022）全文重試**：`mcp__paper-search__search_unpaywall` 查無 OA 版本。未嘗試
   `mcp__research_hub__download_paper`（Decision 2026-08-31-08 永久禁用）。判定
   `BLOCKED_FOR_SOURCE`。
5. **T-012（Katzmann 2022）全文取得**：`search_unpaywall` 查無 OA 版本；以 `curl -I` 檢測
   Crossref 提供的 Springer pdf_url，回傳 `content-type: text/html`（3038 bytes，非真實 PDF，
   判定為存取限制頁）。未嘗試登入/繞過。判定 `BLOCKED_FOR_SOURCE`。
6. **T-015（REPRIEVE trial, Grinspoon SK et al. NEJM 2023）**：`mcp__paper-search__search_pubmed`
   + `get_crossref_paper_by_doi`（DOI 10.1056/NEJMoa2304146）—— 找到並確認：期刊/卷期頁碼/DOI/
   PMID 皆與 Director 提供的引用字串完全相符（VERIFIED）。詳見
   `20_EVIDENCE/trials-efficacy/evidence-map.md` 新增章節（TE-011）。
7. **T-016（REAL-CAD trial，Q8，Director Decision 2026-08-31-19 授權本角色自行驗證）**：
   `mcp__paper-search__search_pubmed`「REAL-CAD randomized evaluation aggressive lipid-lowering
   pitavastatin coronary artery disease Japan」先找到設計論文與多篇 substudy，再以更精確關鍵字
   「Taguchi high-dose versus low-dose pitavastatin coronary artery disease randomized trial
   Circulation 2018」定位主要結果論文（PMID 29735587）；`get_crossref_paper_by_doi`（DOI
   10.1161/CIRCULATIONAHA.117.032615）確認期刊/卷期頁碼。數字與 TE-002 全文中的二手引用完全
   吻合（VERIFIED）。詳見 `evidence-map.md`（TE-012）。

## Chou 2022 Europe PMC 重試與意外新發現（2026-08-31，Director 建議）

`mcp__paper-search__search_europepmc`「Chou pitavastatin ezetimibe fixed-dose combination
hypercholesterolemia Clinical Therapeutics 2022」——確認 Europe PMC 有此文獻 metadata（PMID
36030106）但 `pmcid` 為空、`is_open_access: False`，與 T-012 的情況不同，PMCID 查詢法不適用，
BLOCKED_FOR_SOURCE 維持。同時以 `mcp__paper-search__search_pmc`「1PC111 pitavastatin ezetimibe
fixed-dose combination phase III」廣泛檢索，意外找到兩筆先前未登記的相關新文獻：TE-013（Lu YW
et al. Acta Cardiol Sin 2026，Taiwan post-PCI 真實世界世代）、TE-014（Abbas MS et al. Future
Cardiol 2026，pitavastatin+ezetimibe 專屬統合分析）。以 `search_europepmc` 個別確認取得完整
structured abstract；TE-014 另以 `get_crossref_paper_by_doi` 確認期刊卷期頁碼。詳見
`10_DATA/trials-efficacy/extraction-table.csv`（TE-013、TE-014）與 `evidence-map.md`。

## 未執行 / 刻意跳過的檢索

- 未使用 `scihub` MCP 工具或 `paper-search` 的 `download_scihub`（CLAUDE.md §10 明文禁止，無例外）。
- 未重複搜尋已由 `02_SOURCE-INVENTORY.md` 標記為 guideline-risk 或 safety-pharmacology 主責的
  citation（Runbook §31：避免 specialist 之間職責重疊／蜘蛛網式互相接管）。
- Taiwan STS 2026 consensus（T-005）、Taiwan Lp(a) consensus（T-006）、ESC 2025 Focused Update
  （T-007）為 guideline-risk 主責項目，本角色未主動搜尋；若後續 synthesis 需要 trials-efficacy
  角度交叉引用，將於收到 guideline-risk 的 EVIDENCE_UPDATE 後處理。
