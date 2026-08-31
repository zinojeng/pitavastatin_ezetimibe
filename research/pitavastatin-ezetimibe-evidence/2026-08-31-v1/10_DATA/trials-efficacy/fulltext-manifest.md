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

## Wave 2 尾聲：Chou 2022 retry 與新發現來源（2026-08-31）

依 Director 建議，以 Europe PMC/PMC PMCID 查詢法（safety-pharmacology 用此法成功取得 T-012 全文
的同一方法）重試 TE-001（Chou 2022）：`search_europepmc` 確認 Europe PMC**有**索引此文獻的
metadata（PMID 36030106），但 `is_open_access: False` 且 `pmcid` 欄位為**空值**——與 T-012（有
確切 PMCID PMC8873069）不同，Chou 2022 **未被 PMC 收錄全文**，故此方法對本文獻不適用。
**BLOCKED_FOR_SOURCE 維持不變**。（附帶收穫：取得比 Crossref 更完整的 structured abstract，已
更新至 `extraction-table.csv` TE-001 notes 欄。）

同一批檢索中意外發現兩筆先前未登記的相關新文獻（TE-013、TE-014，詳見
`20_EVIDENCE/trials-efficacy/evidence-map.md`）：

| citation_id | 全文取得狀態 | PMC 收錄狀態 | 備註 |
|---|---|---|---|
| TE-013（Lu YW 2026, Acta Cardiol Sin） | 未嘗試（本次尾聲檢索僅取得 abstract） | PMCID PMC13202365（Europe PMC 回報 `is_open_access: False`，狀態待確認） | Wave 3 中優先序 |
| TE-014（Abbas MS 2026, Future Cardiol） | 未嘗試 | PMCID PMC13288897（同上，`is_open_access: False`） | **Wave 3 最高優先序**——此為專案目前找到唯一專門針對 pitavastatin+ezetimibe FDC 的統合分析，abstract 層級無可用數字，全文價值極高 |

兩者的 Europe PMC 回報皆為 `is_open_access: False`，意味著即使有 PMCID，未必代表可直接下載——
需 Wave 3 實際嘗試（如 PMC 直接連結或期刊官網）才能確認，本次尾聲檢索未進一步嘗試下載（時間
範圍限制，已完整記錄留待下次）。

## Wave 3 全文取得結果（2026-08-31，PI 授權開啟 Wave 3）

| citation_id | 全文取得狀態 | 來源 URL | 取得時間 (UTC) | SHA-256 | 授權/license | LlamaParse 狀態 |
|---|---|---|---|---|---|---|
| TE-013（Lu 2026, Taiwan post-PCI） | **成功** | `https://tpl.ncl.edu.tw/NclService/pdfdownload?...`（台灣國家圖書館「臺灣期刊論文索引系統」公開服務，非 publisher 官網、非繞過付費牆——國圖為公共圖書館法定服務，合法公開取用管道） | 2026-08-31T02:34:55Z | `98925f95b62b9687ba20f4d9af087836229da1fbcf2d3744aee77e89990e5ffd` | Acta Cardiologica Sinica（台灣心臟學會發行）；國圖服務條款下載，**未查證**確切 CC 授權字樣（未見於解析出的全文內），依現有資訊視為合法公開取用但授權條款細節待補 | **成功**（11 頁 PDF 完整解析，含 Table 1–3、Figure 1–4、全部 34 篇 References，人工檢視首尾與段落完整性，無截斷跡象） |
| TE-014（Abbas 2026, meta-analysis） | **失敗（BLOCKED_FOR_SOURCE）** | Taylor & Francis (Future Cardiology)；`tandf.figshare.com` 補充項目連結；ResearchGate 鏡像頁 | 2026-08-31（嘗試時間） | 不適用 | `search_unpaywall` 查無 OA 版本；`tandf.figshare.com` 直接 fetch 回傳 AWS WAF bot-challenge（`x-amzn-waf-action: challenge`, HTTP 202, 無內容）——**未嘗試破解**；`tavily_extract` 於 ResearchGate 鏡像頁未取得可用內容 | 不適用（無檔案可解析） |
| TE-015（Jeong 2022, Korea 第三篇獨立 FDC RCT，Wave 3 新發現） | **失敗（BLOCKED_FOR_SOURCE）** | Europe PMC 提供之延世大學機構典藏連結 `ir.ymlib.yonsei.ac.kr/bitstream/...` | 2026-08-31（嘗試時間） | 不適用 | 直接 fetch 回傳 JavaScript 反機器人 challenge 頁（`data-name="js-challenge"`，非真實 PDF）——**未嘗試破解**，與 Wave 2 PMC POW challenge 同一政策處理 | 不適用（無檔案可解析） |

**方法論記錄**：Wave 3 對兩個新來源（T-024／TE-014、TE-015）各嘗試至少 2–3 條合法路徑
（Unpaywall、期刊/供應商 CDN 直連、第三方學術典藏鏡像），確認皆遭遇**反機器人防護機制**
（AWS WAF challenge 或 JavaScript proof-of-work challenge）而非傳統「付費牆頁面」——依本角色
一貫政策，**遇到反機器人 challenge 一律不嘗試破解**，即使該挑戰機制本身可能與 Sci-Hub 無關；
理由：破解反機器人機制屬於 detection-evasion 範疇，超出本專案「合法取用」授權範圍，即使目的是
取得學術文獻全文。兩者維持 `BLOCKED_FOR_SOURCE`。TE-013（Lu 2026）則透過台灣國家圖書館的
公開查詢/下載服務（非破解、非繞過）成功取得，示範了「反機器人 challenge 擋下直連 publisher／
典藏站」與「改走合法第三方公開服務」兩者的區別——後者是本角色認可的正當替代路徑，前者不是。

## Wave 2 全文取得建議優先序（供 Research Director / 本角色自行後續處理參考）

1. TE-007（Sydhom, open access, 高優先 — 需釐清 pooled study 清單以解決 SOURCE_CONFLICT 疑慮）
2. TE-002 / TE-003（J Atheroscler Thromb, 可能 open access — 需全文取得各劑量組細分 AE/CK/肝功能
   表格，才能完整回答 Search Protocol item 5 的安全性比較部分）
3. TE-009（PLoS ONE, open access, 低優先 — 目前 abstract 已足夠）
4. TE-001（Elsevier, 付費牆 — 若 PI/機構有訂閱管道，建議走機構授權而非 MCP 自動下載）

## Post-Gate-2 持久化修復（2026-08-31，Director 指派的窄範圍任務）

**背景**：Wave 2 取得的 TE-002（Tsujita 2023）與 TE-003（Ako 2024）PDF／LlamaParse 解析結果原先
存於暫時性的 `$CLAUDE_JOB_DIR/tmp/pdfs/`（見上方「LlamaParse 使用狀況」一節），該目錄已不存在，
兩份檔案遺失。本次任務範圍**僅限**重新取得並持久化存放此二檔案，**不開啟 Wave 3**、不變更任何
共用檔案（00–05、02/03、99）或其他角色的 10_DATA/20_EVIDENCE/30_METHODS。

**新的持久化、角色自有、gitignored 路徑**：`20_EVIDENCE/trials-efficacy/fulltext/`
（已由現有 `.gitignore` 第 16 行規則 `**/20_EVIDENCE/**/fulltext/` 涵蓋，經 `git check-ignore -v`
逐檔驗證確認全部被忽略，不會被追蹤）。

| citation_id | 檔案 | 來源 URL（與原 manifest 逐字相同，未變更） | HTTP 狀態 | 檔案大小 | SHA-256 | 與原記錄比對 |
|---|---|---|---|---|---|---|
| TE-002（Tsujita 2023） | `TE-002_Tsujita2023.pdf` | `https://www.jstage.jst.go.jp/article/jat/advpub/0/advpub_64006/_pdf` | `200` (`Content-Disposition: inline; filename="advpub_64006.pdf"`) | 717,939 bytes（PDF v1.3，10 頁，經 `file` 指令確認） | `afe6befc78a9084f95580e513568615618153abd45ddb20ff76ca5e9f4022c26` | **完全相同**於原 manifest 記錄之雜湊值 — 確認重新下載內容與 Wave 2 當時取得版本位元組級一致，未被 publisher 更版 |
| TE-003（Ako 2024） | `TE-003_Ako2024.pdf` | `https://www.jstage.jst.go.jp/article/jat/advpub/0/advpub_64272/_pdf` | `200` (`Content-Disposition: inline; filename="advpub_64272.pdf"`) | 321,262 bytes（PDF v1.6, zip deflate） | `1e103ff00040a986f88820ef2b96924bcac4a9ae4bad4bc313fad4d6f21ac960` | **完全相同**於原 manifest 記錄之雜湊值 — 內容一致，未見更版 |

取得時間（本次重新下載，本機 UTC）：2026-08-30T22:35:01Z（TE-002）／2026-08-30T22:35:02Z（TE-003）。

**LlamaParse 重新解析結果**：

| citation_id | 解析輸出檔 | 解析狀態 | 備註 |
|---|---|---|---|
| TE-002 | `TE-002_Tsujita2023.md`（與 PDF 同目錄） | **成功** — 114,243 bytes / 939 行，逐段檢視首尾（標題/作者/機構起始，Advance Publication 版權聲明結尾）與縮寫表皆完整，`grep -in "truncat\|error\|failed to parse"` 僅命中「standard error」「within-subject errors」等合法醫學統計用詞，非解析錯誤標記 | 字元數（114,243 bytes）與 Wave 2 原記錄（114,893 字元）數值相近但非逐位元相同——屬正常現象：LlamaParse 每次呼叫可能因版面辨識微小差異產生略有不同的 markdown 輸出（PDF 位元組本身經 SHA-256 確認完全一致），內容範圍（10 頁全文、Table 1–3、Fig. 2–3 註腳、Discussion）經檢視仍完整 |
| TE-003 | `TE-003_Ako2024.md`（與 PDF 同目錄） | **成功** — 106,855 bytes / 814 行，首尾（標題/期刊頁首，Table 資料含 Accepted/Published 版權聲明結尾）完整，同上 grep 檢查未見真正錯誤標記 | 同上，字元數與 Wave 2 原記錄（107,117 字元）相近但非逐位元相同，內容完整性已人工檢視確認 |

**授權/access 備註**（與原記錄一致，未變更）：J Atheroscler Thromb 為 J-STAGE 開放取用期刊平台
（`jstage.jst.go.jp`），HTTP 200 直接取得、無需登入或付費牆繞過；**未查證**此 Advance
Publication 版本的確切 CC 授權條款（與 Wave 2 原記錄相同的既有限制，本次未新增查證）。依
CLAUDE.md §11，PDF 本體與 LlamaParse 解析 markdown 僅供本角色萃取比對用，**未提交進 repo**（已
以 `git check-ignore -v` 逐檔驗證 6 個檔案— 2 PDF + 2 MD + 2 個下載 header log — 全數被
`.gitignore` 第 16 行規則忽略）。

**結論**：TE-002／TE-003 全文與解析結果已恢復至持久化、角色自有、gitignored 路徑，內容與 Wave 2
原始取得版本（PDF 位元組層級）一致，可供後續 Wave（Wave 3 或之後）萃取使用。本次任務未變更任何
已提交的 Wave 1/Wave 2 資料結論，`wave2-fulltext-extraction.md` 中既有萃取內容無需修改。
