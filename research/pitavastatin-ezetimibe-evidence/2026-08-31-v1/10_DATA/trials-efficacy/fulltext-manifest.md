# fulltext-manifest — trials-efficacy-intelligence / Wave 1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`

依 CLAUDE.md §11：本檔案僅記錄 metadata／取得狀態／授權狀態；任何已取得的全文 PDF 或
LlamaParse 解析結果一律存放於本機 gitignored 目錄，**不提交進 repo**，除非該檔案的
redistribution license 已被明確查證並記錄（`verified: true`, `license: <name>`,
`redistribution_ok: true`）。本次 Wave 1 **無任何檔案符合此條件**，故無 local_path 指向已提交
內容；以下皆為 metadata-only 紀錄。

| citation_id | title (short) | DOI | 全文取得狀態 | 嘗試方法 | 授權/可取得性備註 |
|---|---|---|---|---|---|
| TE-001 | Chou MT et al. Clin Ther 2022 (Phase III FDC trial) | 10.1016/j.clinthera.2022.08.006 | **下載失敗** | `mcp__research_hub__download_paper` — 13 個資料庫皆未收錄可下載版本 | Elsevier 期刊，付費牆；未嘗試 Unpaywall（Elsevier 論文通常無 OA 版本）；未嘗試 Sci-Hub（CLAUDE.md §10 禁止） |
| TE-002 | Tsujita K et al. J Atheroscler Thromb 2023 (K-924 4-arm dose-comparison) | 10.5551/jat.64006 | 未嘗試下載（Wave 1 時間/範圍限制） | — | J Atheroscler Thromb 為日本動脈硬化學會期刊，多數文章為 open access（.jstage 平台）；**Wave 2 優先下載目標**，可能可直接取得全文供更細緻的劑量別 AE 表格萃取 |
| TE-003 | Ako J et al. J Atheroscler Thromb 2024 (K-924 52-week extension) | 10.5551/jat.64272 | 未嘗試下載 | — | 同上，J Atheroscler Thromb 通常 open access；Wave 2 候選 |
| TE-004 | Hagiwara N et al. Eur Heart J 2017 (HIJ-PROPER) | 10.1093/eurheartj/ehx162 | 未嘗試下載 | — | Oxford University Press 期刊，可能付費牆；abstract 已透過 PubMed 完整取得且數字與二手來源逐字相符，Wave 1 判斷全文非必要，未強行取得 |
| TE-005 | Kim BK et al. Lancet 2022 (RACING 主文) | 10.1016/S0140-6736(22)00916-3 | 未嘗試下載 | — | Elsevier/Lancet 期刊，付費牆；abstract 已足以核對本角色所需數字 |
| TE-006 | Lee YJ et al. Eur Heart J 2023 (RACING DM subgroup) | 未經 Crossref 獨立確認 DOI | **部分取得**（非官方全文，第三方託管） | `mcp__tavily__tavily_search` 找到 SCHMC（南韓某醫院圖書館）機構典藏 PDF 連結（`chlib.schmc.ac.kr/bitstream/...`） | **未下載保存**此第三方 PDF — 授權狀態未查證，且非 publisher 官方版本，依 CLAUDE.md §11「Full-text PDFs...一律存放本機 gitignored 目錄，除非授權已查證」原則，本角色選擇不下載/不保存，僅使用其顯示的摘要數字作交叉核對佐證（已與 PubMed/ACC.org 官方摘要頁的數字一致） |
| TE-007 | Sydhom et al. BMC Cardiovasc Disord 2024 | 10.1186/s12872-024-04144-y | 未嘗試下載 | — | BMC 系列期刊為 **open access**（Springer Nature，CC BY 通常適用）；Crossref 回傳 `pdf_url: https://link.springer.com/content/pdf/10.1186/s12872-024-04144-y.pdf` — **Wave 2 高優先下載目標**，OA 狀態高，且本文獻存在 RCT-vs-observational 限定詞的 SOURCE_CONFLICT 疑慮（見 evidence-map.md），全文可協助釐清 pooled study 清單是否含 pitavastatin/ezetimibe 研究 |
| TE-008 | Boekholdt SM et al. JACC 2014 | 10.1016/j.jacc.2014.02.615 | 未嘗試下載 | — | Elsevier 期刊，付費牆；abstract 已足夠 |
| TE-009 | Yeh YT et al. PLoS ONE 2017 (T-SPARCLE) | 10.1371/journal.pone.0186861 | 未嘗試下載 | — | **PLoS ONE 為 open access**；Wave 2 可直接取得全文，目前未見必要性（abstract 數字已足夠） |

## Wave 2 全文取得結果（2026-08-31，PI 授權 Decision 2026-08-31-12）

| citation_id | 全文取得狀態 | 來源 URL | 取得時間 (UTC) | SHA-256 | 授權/license | LlamaParse 狀態 |
|---|---|---|---|---|---|---|
| TE-002（Tsujita 2023） | **成功** | `https://www.jstage.jst.go.jp/article/jat/advpub/0/advpub_64006/_pdf`（期刊官方 J-STAGE 平台，開放取用） | 2026-08-30T20:58:06Z（本機 UTC） | `afe6befc78a9084f95580e513568615618153abd45ddb20ff76ca5e9f4022c26` | J Atheroscler Thromb 為 J-STAGE 開放取用期刊；未查證確切 CC 授權條款（Advance Publication 版本），本檔案僅供本角色萃取比對用，**未提交進 repo**（依 CLAUDE.md §11，PDF 本體一律留在本機 gitignored 路徑，不 commit） | **成功**（114,893 字元 markdown，10 頁全部解析）— 此為 Gate 2 要求的 LlamaParse 示範之一，**已確認成功** |
| TE-003（Ako 2024） | **成功** | `https://www.jstage.jst.go.jp/article/jat/advpub/0/advpub_64272/_pdf`（同上平台；URL pattern 由 TE-002 之 DOI-slug 規則推導後驗證成功） | 2026-08-30T20:58（本機 UTC，與 TE-002 同批次） | `1e103ff00040a986f88820ef2b96924bcac4a9ae4bad4bc313fad4d6f21ac960` | 同上 | **成功**（107,117 字元 markdown，全文解析） |
| TE-001（Chou 2022, item 4 覆核） | **仍失敗（重試後維持 BLOCKED_FOR_SOURCE）** | Elsevier ScienceDirect（Clinical Therapeutics） | 2026-08-30（重試時間） | 不適用 | Unpaywall 查無 OA 版本（`search_unpaywall` 回傳空結果）；未嘗試 `mcp__research_hub__download_paper`（Decision 2026-08-31-08 永久禁用），未嘗試 Sci-Hub | 不適用（無檔案可解析） |
| T-012（Katzmann 2022） | **仍失敗（BLOCKED_FOR_SOURCE）** | `https://link.springer.com/content/pdf/10.1007/s00392-020-01740-8.pdf`（Crossref 提供的 pdf_url） | 2026-08-30（嘗試時間） | 不適用 | Unpaywall 查無 OA 版本；直接以 `curl -I` 檢測該 Springer pdf_url，回傳 `content-type: text/html`、`content-length: 3038`（明顯為付費牆/存取拒絕頁面，非真實 PDF）— 未進一步嘗試登入/繞過，依 CLAUDE.md §10「不得繞過」原則停止 | 不適用（無檔案可解析） |

**BLOCKED_FOR_SOURCE 正式紀錄**：TE-001（Chou 2022 全文，用於取得逐劑量/逐組 AE/CK/肝功能細項
表格）與 T-012（Katzmann 2022 全文，用於解決 `unresolved-questions.md` Q7 的樣本數矛盾）
兩者在 Wave 2 皆已重新嘗試（`research_hub`/`llamaparse` 連線已修復後），透過 Unpaywall 查詢與
直接 HTTP 檢測確認**無合法可取得的開放版本**。依 CLAUDE.md §10，正式記錄為 `BLOCKED_FOR_SOURCE`
——不繞過、不使用 Sci-Hub、不重試 `research_hub` 的 download 工具。若 PI／機構有訂閱管道，需透過
機構授權管道另行取得，非本角色可解決的技術問題。

## LlamaParse 使用狀況

Wave 1 **未呼叫** `mcp__llamaparse__parse_pdf_to_markdown`（當時無成功下載的本機 PDF 可供解析）。
**Wave 2 更新**：已成功呼叫兩次，對 TE-002（Tsujita 2023）與 TE-003（Ako 2024）的 J-STAGE 官方
PDF 全文執行解析，皆完整成功（見上表）。TE-002 為 Director 指定的 Gate 2 LlamaParse 示範案例，
**已確認成功**：輸出 114,893 字元、10 頁全文皆解析出表格與內文（含 Table 1–3、Fig. 2–3 註腳、
Discussion 全段），未見截斷或亂碼。原始 PDF 檔案本體與 LlamaParse 解析出的完整 markdown 皆存於
本機 `$CLAUDE_JOB_DIR/tmp/pdfs/`（gitignored，不提交 repo）；`10_DATA/trials-efficacy/
wave2-fulltext-extraction.md` 為本角色從解析結果中萃取、可提交 repo 的結構化摘要與逐字引用。

## 專案層級新限制（Decision 2026-08-31-08，2026-08-31 追加）

Research Director 已裁示：**`mcp__research_hub__download_paper` 不得由任何角色呼叫**（其內部
metasearch 含 Sci-Hub 且無 opt-out 參數，牴觸 CLAUDE.md §10 的 Sci-Hub 全面禁令）；
`research_hub` 的 metadata-only 工具（如 `search_papers`）仍可使用。

**揭露**：本 Wave 1 過程中，在此限制發布**之前**，本角色曾呼叫 `mcp__research_hub__download_paper`
一次（TE-001／Chou 2022 的 DOI，見上表）。該次呼叫**失敗**（回傳「13 個資料庫均未收錄」錯誤，未取得
任何檔案內容，亦未見任何 Sci-Hub 連結或內容被回傳）。因限制發布前無法得知此工具的內部 Sci-Hub
fallback 行為，特此如實記錄，供 Director／PI 判斷是否需要進一步追查。**Wave 2 起本角色不會再呼叫
此工具**，全文取得將改用 `mcp__paper-search__search_unpaywall` 或直接請 PI 透過機構訂閱管道取得。

## Wave 2 全文取得建議優先序（供 Research Director / 本角色自行後續處理參考）

1. TE-007（Sydhom, open access, 高優先 — 需釐清 pooled study 清單以解決 SOURCE_CONFLICT 疑慮）
2. TE-002 / TE-003（J Atheroscler Thromb, 可能 open access — 需全文取得各劑量組細分 AE/CK/肝功能
   表格，才能完整回答 Search Protocol item 5 的安全性比較部分）
3. TE-009（PLoS ONE, open access, 低優先 — 目前 abstract 已足夠）
4. TE-001（Elsevier, 付費牆 — 若 PI/機構有訂閱管道，建議走機構授權而非 MCP 自動下載）
