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

## LlamaParse 使用狀況

本次 Wave 1 **未呼叫** `mcp__llamaparse__parse_pdf_to_markdown`，因為上表中沒有任何 PDF 被成功
下載到本機。`llamaparse` MCP 連線本身已確認可用（見 `30_METHODS/trials-efficacy/search-log.md`），
非阻塞因素。

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
