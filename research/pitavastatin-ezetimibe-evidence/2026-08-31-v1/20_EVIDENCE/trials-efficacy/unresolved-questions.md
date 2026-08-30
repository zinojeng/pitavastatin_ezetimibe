# unresolved-questions — trials-efficacy-intelligence / Wave 1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`

本檔案為本角色（trials-efficacy-intelligence）owned path 下的工作清單，供 Wave 2 延續或提報
Research Director 併入專案層級 `04_OPEN-QUESTIONS.md`（該檔案僅 Director 可寫，本角色不直接
編輯）。分類沿用 CLAUDE.md §6：`NEEDS_SOURCE` | `NEEDS_ANALYST` | `NEEDS_METHODS` | `NEEDS_PI`。

## Q1 [NEEDS_SOURCE] Chou 2022 Phase III FDC trial 的收案國家範圍

`pitavastatin topic.md` 描述 TE-001（Chou MT et al. Clin Ther 2022）為「多國多中心
（Taiwan/Australia/NZ）」試驗，但本角色透過 Crossref 取得的作者列（全數為台灣姓名模式，加一位
可能屬於跨國 CRO 的 "Anthony McGirr"）不足以獨立確認 Australia/NZ 收案中心是否存在。全文取得
失敗（見 `10_DATA/trials-efficacy/fulltext-manifest.md`）。
**需要**：Wave 2 取得全文（Methods/收案中心清單）或透過 ClinicalTrials.gov 登錄資訊核實。在此之前，
`40_SYNTHESIS/` 若要重複「多國」的描述，應標註為「PI-supplied，未經本角色獨立確認」。

## Q2 [RESOLVED — 2026-08-31 Wave 2] TE-002（Tsujita 2023 K-924 4-arm 劑量比較）各劑量組的分項安全性數字

**已解決**：Wave 2 取得 J-STAGE 官方全文並以 LlamaParse 解析成功，逐組 AE/ADR/CK/AST/ALT 數字
已完整萃取，見 `10_DATA/trials-efficacy/wave2-fulltext-extraction.md` TE-002 章節與
`extraction-table.csv` TE-002 notes 欄位更新。Search Protocol item 5 的安全性比較維度已可回答。

## Q3 [NEEDS_METHODS] HIJ-PROPER 四篇 substudy 是否需要納入 Wave 2 萃取範圍

Wave 1 檢索過程中額外定位到 4 篇 HIJ-PROPER substudy（未逐一驗證數字，僅記錄存在，避免超出
Wave 1「先驗證既有引用」的範圍）：

- Ogiso M et al. Circ Rep 2020（PMID 33693218）— single-vessel vs multivessel disease 分層
- Arashi H et al. J Am Heart Assoc 2019（PMID 31390907）— baseline EPA/AA ratio 分層
- Yoshikawa M et al. Circ J 2024（PMID 39261090）— heart failure hospitalization 發生率
  （HR 0.47, 95% CI 0.27–0.81, P<0.005 — 依 abstract，此為 Level 3 證據中一個方向明確的正向訊號，
  可能值得 Wave 2 納入）
- Kawada-Watanabe E et al. J Jpn Coll Cardiol 2017（PMID 27349705）— trial design/rationale
  （背景用，非結果）

**需要**：Research Director 或本角色自行判斷，這些 substudy 是否對 40_SYNTHESIS 的 Level 3
論述有加值（尤其 heart-failure substudy 的正向訊號），若加值則納入 Wave 2 逐一驗證清單。

## Q4 [NEEDS_PI] Sydhom et al. 2024 meta-analysis 的 RCT vs observational 限定詞落差（SOURCE_CONFLICT 候選）

見 `20_EVIDENCE/trials-efficacy/evidence-map.md` Level 2 章節之詳述。摘要：`Tonvasca_2026.md`
（第 53 頁）以此文獻為據，寫「中強度statin+ezetimibe，效益超越高強度statin」，未附加限定詞；
但該文獻 abstract 原文明確區分「observational studies pooled 顯示效益（HR 0.76）」與
「RCT-pooled **未**達統計顯著差異」。

**需要**：Research Director 依 Decision Taxonomy（CLAUDE.md §8）裁決此為
`VERIFIED_NEW_SENSITIVITY`（保留原結論但補上限定詞）、`SOURCE_CONFLICT`（需要 PI 決定投影片
用語是否修正）、或其他分類，並記錄於 `03_DECISION-LOG.md`（本角色無寫入權限，僅在此提出並於
cross-session summary 中一併回報）。

## Q8 [NEEDS_SOURCE] REAL-CAD 試驗（pitavastatin 4mg vs 1mg hard-outcome RCT）— 新識別候選來源

於 Wave 2 全文覆核 TE-002（Tsujita 2023）時，於其 Introduction／Discussion 段落發現該文獻引用
REAL-CAD 試驗：「compared with 1 mg/day, 4 mg/day of pitavastatin led to a 19% relative risk
reduction in cardiovascular events (hazard ratio, 0.81; 95% confidence interval (CI), 0.69–0.95)
in the REAL-CAD trial conducted in Japanese patients with CAD」。本角色**未獨立搜尋/驗證**此試驗
的原始發表（僅為 Tsujita 2023 一篇文獻中的二手引用），亦未確認其正式引用格式（期刊/年份/DOI）。

**相關性**：這是**pitavastatin 劑量本身（非 FDC）的 hard-outcome RCT 證據**，若獨立驗證後可能是
`pitavastatin topic.md` §6 三層證據框架之外、值得補充的「pitavastatin 劑量與心血管結果」背景證據
（與 Level 1-3 框架討論的「FDC vs monotherapy」問題不同維度，屬於「pitavastatin 4mg vs 1mg 是否
本身已有 hard-outcome 證據」這一相鄰但不同的問題）。

**需要**：Wave 2/3 獨立搜尋並驗證 REAL-CAD 試驗原始發表（PubMed/Crossref），確認引用字串與數字，
評估是否納入 `20_EVIDENCE/trials-efficacy/evidence-map.md`。在獨立驗證前，此為二手轉引，
不可視為已驗證來源。

## Q7 [NEEDS_ANALYST] Katzmann et al. 2022（T-012, TE-010）— Tonvasca_2026.md 同一張投影片內兩組不同的樣本數自相矛盾

Director 於 2026-08-31 轉來 safety-pharmacology 找到的 Katzmann JL et al. Clin Res Cardiol
2022;111(3):243-252（T-012）交由本角色驗證。經 PubMed／Crossref 核對，期刊/卷期頁碼/DOI 與
`Tonvasca_2026.md` 引用字串完全相符（VERIFIED），且投影片表格中的 −28.4% / −19.4% / 31.5% /
21.0% 四個關鍵數字與原始論文 abstract 完全吻合。

**但**在核對過程中發現：`Tonvasca_2026.md`（約 line 2313–2340）同一張投影片內，**標題**寫
「Statin + ezetimibe FDC (n=6,429) vs Statin + ezetimibe separate pills (n=533)」，緊接著的
**結果表格**卻寫「Statin + ezetimibe FDC (n=1,639)」與「Statin + Ezetimibe (As separate pills,
n=796)」— 兩組樣本數彼此不一致，且大小關係甚至相反（6,429>533，但 1,639<796）。PubMed abstract
僅提供全研究 N=311,242（涵蓋所有 LLT 種類的病人，非僅 ezetimibe-FDC-vs-separate-pills 次族群），
無法從 abstract 層級判斷何者正確、甚至兩者皆非。

**依 Numeric Integrity Rule（CLAUDE.md §9），本角色未做任何猜測性選擇或修正**，兩組數字皆已
如實保留於 `extraction-table.csv`（TE-010 notes 欄），標記 `FLAG = POSSIBLE_ERROR`，
`ACTION = NEEDS_ANALYST`。**Wave 2 更新（2026-08-31）**：已重新嘗試取得全文——Unpaywall 查無 OA 版本；直接以 HTTP HEAD
檢測 Crossref 提供的 Springer pdf_url，回傳 `content-type: text/html`（3038 bytes），非真實 PDF，
判定為付費牆頁面。**正式記錄為 `BLOCKED_FOR_SOURCE`**（見 `fulltext-manifest.md`）。依 CLAUDE.md
§10，未嘗試登入/繞過，亦未使用 `mcp__research_hub__download_paper`（已永久禁用）或 Sci-Hub。
在 PI／機構透過訂閱管道取得全文之前，本題維持懸而未決：兩組樣本數皆不可作為 `40_SYNTHESIS/`
的可引用數字，且 `Tonvasca_2026.md` 本身是否有誤植也無法確認（依 CLAUDE.md §1，legacy file 本身
不可編輯，即使誤植亦僅能於未來輸出中註記差異，不得修改原檔）。

## Q6 [RESOLVED — 2026-08-31 Wave 2] TE-002 標題「vs. Pitavastatin」與 4-arm 設計的統計比較結構

Director 於 2026-08-31 review 時指出：TE-002 的期刊標題為「Efficacy and Safety of
Pitavastatin/Ezetimibe Fixed-Dose Combination **vs. Pitavastatin**: Phase III, Double-Blind,
Randomized Controlled Trial」，字面讀起來像是單純的 2-arm 比較（FDC vs pitavastatin），但本角色
從 PubMed abstract 摘錄的設計是明確的 **4-arm**（pitavastatin 2mg／4mg／2mg+eze10mg（K-924
LD）／4mg+eze10mg（K-924 HD）並列隨機分派，N=293）。

本角色覆核 abstract 原文（"A total of 293 patients were randomly assigned into four groups
receiving 2 mg pitavastatin, 4 mg pitavastatin, 2 mg pitavastatin/10 mg ezetimibe (K-924 LD), and
4 mg pitavastatin/10 mg ezetimibe (K-924 HD) once daily for 12 weeks."）— **4-arm 設計本身在
abstract 層級是明確、無歧義的**；標題的「vs. Pitavastatin」讀法上應理解為「FDC（不分劑量）vs.
pitavastatin monotherapy（不分劑量）」這種期刊標題慣用的簡化措辭，而非與 abstract 內容矛盾。
但由於 **統計分析方式**（例如主要 endpoint 的組間比較是否真的是簡單 pooled FDC-vs-monotherapy
兩組檢定，還是四組各自兩兩比較）僅憑 abstract 無法完全確認，這會影響 Wave 2/40_SYNTHESIS 引用
「2mg+eze10 vs 4mg 單方」「2/10 vs 4/10」這類 head-to-head 劑量比較數字時的統計顯著性判讀。

**已解決（Wave 2, 2026-08-31）**：取得 J-STAGE 官方全文並以 LlamaParse 解析成功。確認統計比較為
**pairwise MMRM**（同劑量 pitavastatin vs 對應 K-924，以及 K-924 LD vs K-924 HD 的探索性比較），
並非簡單 pooled FDC-vs-monotherapy 兩組檢定：K-924 LD vs PS 2mg 差異 −11.9%（95% CI −15.2% to
−8.7%, p=0.000）；K-924 HD vs PS 4mg 差異 −12.7%（95% CI −15.9% to −9.4%, p=0.000）；K-924 HD vs
K-924 LD 差異 −6.4%（95% CI −9.6% to −3.2%, p≤0.001）。**重要限定**：「K-924 LD (2/10) vs PS 4mg」
這個跨劑量比較（`pitavastatin topic.md`「Add ezetimibe or double the statin?」框架所需）**本研究
並未做正式統計檢定**——這是描述性點估計相減（−51.4% vs −45.2%），非有 CI/p-value 支持的比較，
`40_SYNTHESIS/` 引用時應註明此點為描述性觀察。詳見 `10_DATA/trials-efficacy/
wave2-fulltext-extraction.md`。

## Q5 [NEEDS_SOURCE] CEPHEUS（citation #20）、DYSIS-II（citation #21）、Masana 2020（citation #25）三篇未能定位逐字相符原文

`02_SOURCE-INVENTORY.md` 中列出的三筆既有引用，本角色多輪嘗試（PubMed 與 Crossref 交叉查詢）
**未能找到與 `Tonvasca_2026.md` 引用字串完全逐字相符**的原始文獻：

- `Chiang CE, et al. J Atheroscler Thromb. 2016;23(5):567-587`（CEPHEUS study）—
  找到的是同一 CEPHEUS-Pan-Asian Taiwan cohort 之另外兩篇分析（Wang KF/Chiang CE，
  J Chin Med Assoc 2014，PMID 24332414 與 24882620），期刊/年份與引用字串不符，可能是
  `Tonvasca_2026.md` 引用了同一資料集的不同分析文章，或引用字串本身有誤植。
- `Gitt AK, et al. Atherosclerosis. 2017;266:158-166`（DYSIS-II study）— 找到多篇 DYSIS-II 相關
  文獻（分屬 Thailand/France/Europe 子分析，散見 Heart Lung Circ、Eur Heart J 摘要、
  Arch Cardiovasc Dis 等），但沒有一篇的期刊/卷/頁與引用字串完全相符。
- `Masana L, et al. Curr Cardiol Rep. 2020;22(8):66`（combination LLT mechanism synergy）—
  找到的是同作者較新的相關文章（Masana L et al. Pharmacol Res 2023;190:106738,
  "Lipid lowering combination therapy: From prevention to atherosclerosis plaque treatment"），
  但年份/期刊與引用字串不符。

**依 Numeric Integrity Rule（CLAUDE.md §9），本角色未對這三筆引用做任何猜測性修正**，維持
`Tonvasca_2026.md` 中的原始引用字串為 `SOURCE_VALUE`，狀態標記為 `FLAG = POSSIBLE_ERROR`，
`ACTION = NEEDS_ANALYST`（Wave 2 以期刊官網或更精確的 PMID 檢索重試）或 `NEEDS_PI`（若 Wave 2
仍找不到，需請 PI 確認原始投影片來源檔案或 Data-on-file 文件）。這三筆引用**目前不應在
`40_SYNTHESIS/` 中被當作已驗證來源引用**。
