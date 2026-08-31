# evidence-map — trials-efficacy-intelligence / Wave 1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Role: trials-efficacy-intelligence · Wave: 1

本檔案將 `10_DATA/trials-efficacy/extraction-table.csv` 的原始數字，依 `pitavastatin topic.md`
§6（Level 1/2/3 hard-outcome evidence hierarchy）與 CLAUDE.md §7（Evidence Hierarchy 標籤）組織
成可供 Wave 3 synthesis 直接引用的證據地圖。所有 citation_id 對應 extraction-table.csv。

---

## Wave 3 明確框架總表（Director 2026-08-31 指派 §3：明確建構 Level 1/2/3 區分，禁止混淆）

**核心規則（不可違反）**：以下每一列的比較對象、用藥組成、收案族群三者若有任一項不同，即**不可**
互相替代、加強、或暗示彼此的結論可以類推。Director 於任務指派中指出這是 Wave 2 Challenge Round
標記的最高風險過度延伸點（其引用路徑 `30_METHODS/shared/wave2-challenge-round.md`——**註**：
本角色所在的獨立 worktree 中該檔案尚未出現（僅見 `.gitkeep` 佔位），可能是 Director 所在 worktree
尚未合併回來，本角色未能直接讀取核對其內容，此處的框架整理是依 Director 訊息中的敘述重建，
而非直接引用該檔案原文）。

| Citation | 藥物比較 | 收案族群 | 對本專案 FDC 問題的定位 | Evidence Hierarchy |
|---|---|---|---|---|
| **Level 1** — TE-001（Chou 2022, Taiwan）、TE-002（Tsujita 2023, Japan）、TE-015（Jeong 2022, Korea）、TE-003（Ako 2024, Japan 延伸） | pitavastatin 2/4mg **+ ezetimibe 10mg** vs pitavastatin 2/4mg 單方（或 vs ezetimibe 單方） | 一般 hypercholesterolemia／mixed dyslipidemia 門診族群（台/日/韓，非 ACS、非二級預防為主） | **FDC 問題本身**——LDL-C 降幅的直接證據 | DIRECT EVIDENCE（僅 LDL-lowering efficacy，非 CV outcome） |
| TE-013（Lu 2026, Taiwan real-world） | pitavastatin 4mg **+ ezetimibe 10mg** vs 病人自身 baseline（無對照組） | Taiwan post-PCI（**次級預防**，高風險） | FDC 問題的台灣真實世界佐證 | OBSERVATIONAL EVIDENCE（單臂回溯性世代） |
| **Level 2** — TE-005/006（RACING, Kim BK 2022 / Lee YJ 2023） | **rosuvastatin** 10mg + ezetimibe 10mg vs **rosuvastatin** 20mg 單方 | 南韓 ASCVD 族群（含 DM 次族群） | Combination-strategy CV outcome 的**間接**證據——藥物是 rosuvastatin，**不是 pitavastatin** | INDIRECT EVIDENCE（對 pitavastatin/ezetimibe 專屬論斷而言） |
| TE-007（Sydhom 2024 meta-analysis） | 泛統計「低/中強度 statin + ezetimibe」vs「高強度 statin 單方」（statin 種類不限） | 混合（RCT + observational 分開 pool） | Combination-strategy 的統合層級佐證，**statin-agnostic**，非 pitavastatin 專屬 | OBSERVATIONAL EVIDENCE（RCT-pooled 分析本身未達顯著，見下方 SOURCE_CONFLICT 章節） |
| **Level 3** — TE-004（HIJ-PROPER, Hagiwara 2017） | **pitavastatin** 標準劑量 **+ ezetimibe** vs **pitavastatin** 單方 | 日本 ACS 族群（**唯一**藥物組成與收案族群都精準對應本專案核心問題的 hard-outcome RCT） | **唯一**真正回答「pitavastatin+ezetimibe FDC 是否有 hard-outcome 證據」的直接試驗——但整體 primary endpoint 未達顯著 | DIRECT EVIDENCE（整體）／INSUFFICIENT EVIDENCE（sitosterol 次族群，僅 hypothesis-generating） |
| **框架外參考點（不屬於 Level 1/2/3，禁止類推套用）** — TE-011（REPRIEVE, Grinspoon 2023） | **pitavastatin 單方 4mg** vs **安慰劑**（無 ezetimibe） | HIV 感染、初級預防、低至中度風險（**非**一般三高族群，**非**次級預防） | 只回答「pitavastatin 單方本身是否有 hard-outcome 證據」——與 FDC 問題**無關** | DIRECT EVIDENCE（但範圍狹窄，見下方專節） |
| TE-012（REAL-CAD, Taguchi 2018） | **pitavastatin 單方**劑量強度（4mg vs 1mg，**無 ezetimibe**） | 日本穩定型 CAD，**次級預防** | 只回答「pitavastatin 劑量強度本身是否有 hard-outcome 證據」——與 FDC 問題**無關** | DIRECT EVIDENCE（但範圍狹窄，見下方專節） |

**明確禁止的三種混淆（依 Director 指示重申）**：
1. 不可將 RACING（rosuvastatin）的 CV outcome 結果，寫成或暗示為「pitavastatin/ezetimibe 的 CV
   outcome 證據」——RACING 只能支持「combination strategy 這個概念」，藥物本身必須明確標註為
   rosuvastatin。
2. 不可將 REPRIEVE 或 REAL-CAD（兩者皆為 pitavastatin **單方**、**無 ezetimibe**）的正向 hard-outcome
   結果，寫成或暗示為對 Level 3（HIJ-PROPER 缺口）的補強——兩者完全不涉及 ezetimibe 併用問題。
3. 不可將 HIJ-PROPER 的 sitosterol 次族群訊號（HR 0.71）升級為「已證實」的 phenotype-selection
   策略證據——母試驗整體 primary endpoint 未達顯著，次族群訊號僅為 hypothesis-generating。

以下各節維持 Wave 1/2 已建立的詳細分析，本節僅作為 Wave 3 要求的**明確總覽**，不取代下方細節。

---

## Level 1：LDL-lowering efficacy（pitavastatin/ezetimibe 產品層級，強證據）

### TE-001 — Chou MT et al. Clin Ther 2022（多中心 Phase III RCT）

- Evidence Hierarchy: **DIRECT EVIDENCE**（僅適用於 LDL-lowering efficacy 與短期 safety，
  不適用於 CV outcome — 依 CLAUDE.md §7 明文規定）。
- Pitavastatin 2mg/ezetimibe 10mg FDC 於 week 4／week 12 分別使 LDL-C 下降 −51.04% / −50.5%，
  顯著優於 pitavastatin 2mg 單方（−34.99% / −36.11%，皆 p<0.001 vs FDC）與 ezetimibe 10mg 單方
  （−20.01% / −19.85%，皆 p<0.001 vs FDC）。
- LDL-C 達標率（<100 mg/dL, week 12）：LDL-C≥190 mg/dL 次族群 FDC 65.22% vs pitavastatin 6.67%
  vs ezetimibe 0%；40–75 歲 DM 次族群 FDC 94.12% vs pitavastatin 25% vs ezetimibe 0%
  （**p<0.0001 vs FDC）— 此即 `pitavastatin topic.md` 標題「協助超過 9 成糖尿病血脂異常病人血脂
  達標」的數字來源，已核對一致。
- 安全性：三組間 AE 與 drug-related AE 發生率無顯著差異；CPK 上升、myalgia 等個別 AE 發生率低
  且組間相近。
- **provenance 註記**：DOI/期刊/卷期頁碼已以 Crossref 獨立驗證與 `Tonvasca_2026.md` 引用字串
  完全相符；但上述數字本身目前仍是「由 `Tonvasca_2026.md` 轉錄」而非「由本角色直接讀取
  publisher 全文核對」— 全文下載嘗試失敗（Elsevier 付費牆，見 `fulltext-manifest.md`）。依
  Numeric Integrity Rule（CLAUDE.md §9），這些數字狀態為 **VERIFIED（來源比對已核對一致）但
  NEEDS_ANALYST（尚待全文覆核）**，非「完全獨立重新萃取」。
- **人群範圍待釐清**：`pitavastatin topic.md` 描述此研究為「多國多中心（Taiwan/Australia/NZ）」，
  但作者列（Chou, Jong, Chao, Lee, Huang, Chen, Hsieh, Lu, Sheu 均為台灣姓名模式）本身不足以
  獨立確認 Australia/NZ 收案中心 — 見 `unresolved-questions.md` Q1。

### TE-002 — Tsujita K, Yokote K, Ako J, et al. J Atheroscler Thromb 2023（日本，K-924 4-arm RCT）

- **本次 Wave 1 新發現的來源**，直接回答 Search Protocol item 5（先前 `02_SOURCE-INVENTORY.md`
  標記 T-004「pitavastatin 2 mg vs 4 mg dose-comparison studies」為 not yet located）。
- Evidence Hierarchy: **DIRECT EVIDENCE**（head-to-head 劑量比較，日本人群，非 Taiwan 人群 — 套用
  至 Taiwan STS 情境時須註明族群差異）。
- 4 組平行設計，12 週 LDL-C % change：pitavastatin 2mg −39.5% ／ pitavastatin 4mg −45.2% ／
  K-924 LD（2mg/eze10mg）−51.4% ／ K-924 HD（4mg/eze10mg）−57.8%。
- 機轉標記物分化明確：cholesterol synthesis marker（lathosterol）在 pitavastatin 單方與 FDC 皆顯著
  下降（FDC 組降幅較小）；cholesterol absorption marker（beta-sitosterol、campesterol）僅在 FDC
  組下降，pitavastatin 單方無效 — 與 `pitavastatin topic.md` §五「statin 抑制 synthesis／ezetimibe
  抑制 absorption」的機轉敘述直接吻合，且提供了**量化證據**支持這個敘述，可用於強化「Add
  ezetimibe or double the statin?」這張 clinical decision slide。
- 這組數字可以直接建構 `pitavastatin topic.md` 建議的實用比較：
  - **2mg+eze10 vs 4mg 單方**：−51.4% vs −45.2%（加 ezetimibe 優於加倍劑量至 4mg）。**⚠ Wave 2
    全文覆核確認：本研究並未對這項跨劑量比較做正式統計檢定**（差異僅為點估計相減，非有
    CI/p-value 支持的比較）— 引用時須註明為描述性觀察，不得暗示已達統計顯著。
  - **2/10 vs 4/10**：−51.4% vs −57.8%（4mg 起始仍能再多降約 6.4 個百分點）。**Wave 2 全文覆核
    確認：此項有正式 MMRM 統計檢定**，差異 −6.4%（95% CI −9.6% to −3.2%, p≤0.001），達統計顯著
    — 可直接引用為「達顯著」的劑量遞增效益。
- 安全性（**Q2 已於 Wave 2 全文覆核解決**，見 `10_DATA/trials-efficacy/wave2-fulltext-extraction.md`）：
  逐組 AE 發生率 PS2mg 12(16.7%)／PS4mg 19(26.4%)／K-924 LD 18(25.0%)／K-924 HD 14(19.4%)；
  K-924 LD vs PS2mg（p=0.305）、K-924 HD vs PS4mg（p=0.428）之 AE 發生率皆無統計顯著差異；ADR
  發生率同樣無顯著差異（p=0.681／1.000）。無病人 AST/ALT/CK 達預設 cutoff；肝功能與肌病變相關
  檢驗值雖上升但仍在參考範圍內，**唯一例外為 PS 2mg 組的 CK**（原文如此敘述，未附確切數值）。

### TE-003 — Ako J, Yokote K, Tsujita K, et al. J Atheroscler Thromb 2024（K-924 52 週延伸試驗）

- Evidence Hierarchy: **DIRECT EVIDENCE**，但為單臂設計（無同期 monotherapy 對照組），僅能佐證
  「statin 單方未達標病人轉換為 FDC 後」的長期（52 週）LDL-C 降幅與安全性，不能直接回答
  「add ezetimibe vs dose escalation」的隨機比較問題。
- 109 名 pitavastatin 單方未達 LDL-C 目標的病人轉換為 K-924 後，52 週 LDL-C 降幅 −30.3±14.3%
  （p<0.001）；一級預防族群 91.8% 達標、二級預防族群僅 37.5% 達標 — 這個「二級預防達標率明顯偏低」
  的數字，對強化「即使加上 ezetimibe，極高風險/二級預防病人仍可能無法單靠 pitavastatin/ezetimibe
  FDC 達到 <55 mg/dL 的 2026 ACC/AHA 目標」這條 guideline-risk 相關論述，是有用的交叉引用素材。
- **⚠ Wave 2 全文覆核發現，abstract 層級敘述可能低估 AE 量級**：本文獻 abstract 僅稱「a single
  adverse drug reaction occurred」，讀起來像安全性極佳；但全文 Table 4 顯示**整體 AE 發生率高達
  59.6%（65/109 名病人，129 件事件）**，另有 12 名病人（11.0%）發生共 15 件嚴重 AE。**唯一
  被判定為藥物相關（ADR）的僅 1 件**（K-924 HD 組 CK 上升，0.9%），15 件嚴重 AE 全數被判定與
  研究藥物無關。換言之，「well-tolerated」的結論本身仍站得住腳（因為絕大多數 AE 非藥物相關），
  但若 `40_SYNTHESIS/` 僅引用 abstract 的措辭而不揭露 59.6% 這個整體 AE 發生率，可能給讀者
  「幾乎零 AE」的錯誤印象 — 建議未來引用時同時呈現「AE 發生率 59.6%」與「僅 1 件判定為 ADR」
  兩個數字，避免斷章取義。詳見 `10_DATA/trials-efficacy/wave2-fulltext-extraction.md`。

### TE-015 — Jeong HS et al. Clin Ther 2022;44(10):1310-1325（韓國，**第三個**獨立國家的 Phase III FDC RCT，Wave 3 新發現）

- 於 Wave 3 全文取得 TE-013（Lu 2026）時，於其參考文獻列表中發現此篇，獨立以 PubMed/Crossref
  驗證（非二手轉引）。與 TE-001（台灣）、TE-002（日本）同為 pitavastatin 2mg/4mg + ezetimibe
  10mg 的 4-arm 設計 Phase III RCT，且與 TE-001 發表於**同一期**期刊（Clin Ther 2022;44(10)）。
- Pooled pitavastatin/ezetimibe vs pooled pitavastatin：LDL-C %change −52.8%(SD 11.2%) vs
  −37.1%(SD 14.1%)；組間差異 −15.8 mg/dL（95% CI −18.7 to −12.9, P<0.001，**注意此為 mg/dL
  單位而非百分點差異，依原文如實保留**）。LDL-C 達標率：94.2% vs 69.1%（P<0.001）。整體 AE/ADR
  發生率無顯著組間差異，嚴重 AE 亦相當。
- **三國（台/日/韓）獨立重複驗證**：TE-001、TE-002、TE-015 三篇獨立、不同國家、相同藥物組成設計
  的 Phase III RCT，一致顯示 pitavastatin 2mg/4mg + ezetimibe 10mg 可使 LDL-C 降幅達 50% 以上，
  安全性與單方相當——這是 Level 1 證據**跨國一致性**的有力佐證，大幅強化「Level 1 為強證據」
  這個既有判斷的可信度，非僅單一試驗的孤證。
- 全文取得受阻（延世大學機構典藏連結遇 JavaScript 反機器人 challenge，未嘗試破解），
  BLOCKED_FOR_SOURCE，僅能使用 abstract 層級數字。

---

## Level 2：Combination-strategy 的 cardiovascular outcome evidence（strong，但非 pitavastatin-specific）

### TE-005 — RACING trial 主文（Kim BK et al. Lancet 2022）與 TE-006 — RACING DM 次族群（Lee YJ et al. Eur Heart J 2023）

- Evidence Hierarchy: **INDIRECT EVIDENCE** 對於任何 pitavastatin/ezetimibe 專屬的 hard-outcome
  論斷（試驗用藥為 rosuvastatin，非 pitavastatin — 依 CLAUDE.md §7 強制標註，不得混用）。
- 整體族群（N=3780）：3 年複合結果 combination 9.1% vs high-intensity monotherapy 9.9%（絕對差
  −0.78%，90% CI −2.39 至 0.83）達到非劣性；LDL-C<70 mg/dL 達標率 1/2/3 年皆顯著較高
  （73%/75%/72% vs 55%/60%/58%，皆 p<0.0001）；因不耐受而停藥/減量：4.8%（88 人）vs 8.2%
  （150 人），p<0.0001。**數字已與 `pitavastatin topic.md` 原文逐字核對一致。**
- DM 次族群（N=1398，佔全體 37.0%，pre-specified）：複合結果 10.0% vs 11.3%（HR 0.89, 95% CI
  0.64–1.22, P=0.460 — **未達統計顯著**）；LDL-C<70 mg/dL 於 3 年為 79.9% vs 66.8%（皆
  p<0.001）；不耐受停藥/減量 5.2% vs 8.7%（P=0.014）。**`pitavastatin topic.md` 的四捨五入數字
  （「10.0% vs 11.3%，沒有顯著差異」「LDL<70 約80% vs 65%左右」「intolerance 5.2% vs 8.7%」）
  與本文獻的精確數字實質相符，確認該段文字的數據來源即為此篇。**
- **重要框架提醒（呼應 `pitavastatin topic.md` 的既有告誡）**：DM 次族群的 3 年複合結果 HR 0.89
  未達統計顯著（P=0.460, 95% CI 涵蓋 1），此為 pre-specified 但非 powered-for-significance 的
  subgroup 分析；一篇隨文刊登的社論（Stone NJ, Eur Heart J 2023;44(11):984-985）明確提醒讀者
  審慎解讀 pre-specified subgroup 的價值 — 這個編輯評論本身也是一個值得在 synthesis 中引用的
  「證據謹慎性」佐證，避免把 DM subgroup 的方向性訊號（LDL 達標率顯著較高、不耐受顯著較低）過度
  延伸為「combination therapy 對 DM 病人的 MACE 有效益」的結論。
- 合理的 take-home（沿用 `pitavastatin topic.md` 既有措辭，未加碼）：moderate-intensity statin +
  ezetimibe 可作為 high-intensity statin monotherapy 的臨床上有效替代策略，具更佳 LDL target
  attainment 與耐受性；**不能**寫成「combination 已證實在心血管結果上優於 high-intensity statin」。

### TE-007 — Sydhom et al. BMC Cardiovasc Disord 2024（meta-analysis）

- Evidence Hierarchy：**須按證據來源分層標註** — 對於臨床結果（clinical outcome）論斷，
  observational-study pooled 分析屬 **OBSERVATIONAL EVIDENCE**；本文獻自陳的 RCT-pooled 分析
  **並未**在臨床結果上達統計顯著差異，因此不能作為 DIRECT/INDIRECT EVIDENCE 支持
  「combination therapy 效益超越 high-intensity statin」這類臨床結果論斷。RCT-pooled 分析對
  **LDL-lowering 效果與安全性結果**（LDL<70 達標率 RR 1.27 [1.21–1.34]、肌肉相關 AE RR 0.52
  [0.32–0.85]、肝酶升高 RR 0.51 [0.29–0.89]）則可視為 DIRECT/INDIRECT EVIDENCE（視個別 pooled
  study 的 statin/ezetimibe 用藥是否含 pitavastatin 而定，本文獻未在 abstract 層級細分各研究
  用藥，需全文才能判斷是否含 pitavastatin/ezetimibe 研究）。
- **⚠ 待 Research Director / PI 裁決的 SOURCE_CONFLICT 候選項**：`Tonvasca_2026.md`（第 53 頁，
  line ~2796）引用本文獻支持「綜合分析證實，中強度 statin+ ezetimibe，效益超越高強度
  statin」，未附加 RCT vs observational 的區分限定詞。但本文獻 abstract 原文明確寫著：
  「the pooled analysis of RCTs **did not** demonstrate a statistically significant difference
  between both arms concerning clinical endpoints」，僅 observational pooled 分析顯示效益
  （HR 0.76, 95% CI 0.73–0.80）。這是**證據強度被 Tonvasca 投影片省略限定詞而可能被讀者誤解為
  RCT 等級證據**的具體案例，建議 Research Director 依 Decision Taxonomy 標記為
  `SOURCE_CONFLICT` 或 `NEEDS_PI`，決定 Wave 3 synthesis／未來簡報中是否需要恢復
  RCT-vs-observational 的限定詞（見 `unresolved-questions.md` Q4，已列入本角色 cross-session
  summary 的 FINDING）。

---

## Level 3：Pitavastatin/ezetimibe 專屬的 hard-outcome evidence（弱／未充分證明，如實呈現）

### TE-004 — HIJ-PROPER 主文（Hagiwara N et al. Eur Heart J 2017）

- Evidence Hierarchy：整體試驗結果為 **DIRECT EVIDENCE**（pitavastatin+ezetimibe vs pitavastatin
  monotherapy 的頭對頭 ACS hard-outcome RCT，日本人群 N=1734，19 家醫院，中位追蹤 3.86 年）；
  但 sitosterol/absorber-phenotype 次族群結果為 **HYPOTHESIS-GENERATING / INSUFFICIENT
  EVIDENCE**（依 CLAUDE.md §7 強制標註，即使母試驗本身是 DIRECT EVIDENCE，次族群發現不可升級
  為「已證實」的 phenotype-selection 策略證據）。
- Overall primary endpoint：283/864（32.8%）vs 316/857（36.9%），HR 0.89, 95% CI 0.76–1.04,
  P=0.152 — **未達統計優越性**。追蹤期平均 LDL-C：combination 組 65.1 mg/dL vs monotherapy 組
  84.6 mg/dL（兩組確實有明顯 LDL-C 分離，但仍未轉化為顯著的臨床結果差異）。
- 高 baseline sitosterol（cholesterol-absorber phenotype）次族群：HR 0.71, 95% CI 0.56–0.91
  （方向性支持該表型病人可能自 combination therapy 獲得較大效益）。
- **上述所有數字已與 `pitavastatin topic.md` 原文（32.8% vs 36.9%, HR 0.89, 95% CI 0.76–1.04,
  P=0.152；subgroup HR 0.71）逐字核對一致**，經 PubMed 摘要獨立確認為完全相同數字 — 此為 Wave 1
  中證據品質最高的一組核對結果（PI 提供的 topic notes 數字與主要發表論文完全吻合，無需 PI
  correction）。
- 對應 `pitavastatin topic.md` 建議的敘事框架（**應沿用，勿加碼**）：「Could cholesterol
  absorption phenotype help identify patients who derive greater benefit from ezetimibe?」—
  這是一個開放的 precision-lipidology 研究問題，**不是**「Ezetimibe everyone should use」的證據。
- 已定位但**未於 Wave 1 逐一驗證**的 4 篇 HIJ-PROPER substudy（單/多血管病灶分層、EPA/AA 比值
  分層、心衰竭發生率、以及本篇本身），留待 Wave 2 視 synthesis 需要決定是否深入萃取（見
  `unresolved-questions.md`）。

---

## 三層證據等級總結表（呼應 `pitavastatin topic.md` §六／CLAUDE.md §5 item 9 的既定框架）

| Level | 內容 | 本 Wave 1 驗證狀態 |
|---|---|---|
| Level 1 — LDL-lowering efficacy | TE-001（Taiwan Phase III FDC trial）、TE-002（Japan 4-arm 劑量比較，**新發現**）、TE-003（52 週延伸試驗，**新發現**） | 三篇均 VERIFIED（DOI/期刊/數字比對一致）；TE-001 之數字為 legacy 轉錄，全文覆核仍待 Wave 2 |
| Level 2 — Combination-strategy CV outcome evidence（非 pitavastatin 專屬） | TE-005（RACING 主文）、TE-006（RACING DM 次族群）、TE-007（Sydhom meta-analysis，**發現與投影片框架的潛在落差**） | RACING 兩篇 VERIFIED，數字與 topic notes 完全吻合；Sydhom 之 RCT vs observational 限定詞落差已標記 SOURCE_CONFLICT 候選 |
| Level 3 — Pitavastatin/ezetimibe 專屬 hard-outcome evidence | TE-004（HIJ-PROPER 主文） | VERIFIED，數字與 topic notes 完全吻合；**仍是本專案證據鏈中最弱的一環，如 `pitavastatin topic.md` 原先所預期，Wave 1 未發現任何更新的試驗已補上這個缺口** |

---

## 補充：Pitavastatin 單方本身（非 FDC）的 hard-outcome RCT — REPRIEVE trial

### TE-011 — Grinspoon SK et al. NEJM 2023;389(8):687-699（T-015，Director 於 2026-08-31 指派，guideline-risk 域外發現）

- Evidence Hierarchy：**DIRECT EVIDENCE**，但適用範圍狹窄——這是 pitavastatin **單方**（非 FDC、
  非與 ezetimibe 併用）對照**安慰劑**（非另一 statin）的心血管結果 RCT，收案族群為**HIV 感染、
  低至中度心血管風險、正接受抗病毒治療**的一般初級預防族群（非 ACS，非台灣/日本一般血脂異常
  族群）。依 CLAUDE.md §7 與 Director 指示，**不可與 HIJ-PROPER（pitavastatin+ezetimibe vs
  pitavastatin，ACS 族群）或 RACING（rosuvastatin+ezetimibe vs rosuvastatin）混為一談**——三者
  雖然都是「pitavastatin 相關」的 hard-outcome RCT，但比較對象、藥物組成、收案族群三者皆不同，
  屬於 `pitavastatin topic.md` §6 Level 1/2/3（FDC 專屬）框架**之外**的第四個獨立參考點：
  「pitavastatin 單方本身是否已有 hard-outcome RCT 證據」。
- N=7769 隨機分派，中位年齡 50 歲，中位追蹤 5.1 年（**因效益顯著而提前終止試驗**）。
  Pitavastatin calcium 4mg/day vs placebo。
- Primary outcome（MACE 複合終點）：4.81 vs 7.32 per 1000 person-years；**HR 0.65, 95% CI
  0.48–0.90, P=0.002** — 達統計顯著，且效果量頗大（35% 相對風險下降）。
- 安全性：肌肉相關症狀 91(2.3%) vs 53(1.4%)（pitavastatin 較高）；**糖尿病** 206(5.3%) vs
  155(4.0%)（pitavastatin 較高）。
- **交叉領域提醒（轉知 safety-pharmacology，非本角色越權解讀）**：此處的糖尿病訊號是
  **pitavastatin vs 安慰劑**的絕對風險比較，並非 `pitavastatin topic.md` 既有框架中「pitavastatin
  vs atorvastatin/rosuvastatin 之相對 NODM 風險較低」的那種頭對頭比較（TE-003/Singh 2024
  meta-analysis 的比較對象是其他 statin，非安慰劑）。**兩者問題不同，不互相矛盾**，但若
  safety-pharmacology 或未來簡報要呈現「pitavastatin 幾乎不影響血糖」的印象，REPRIEVE 這筆
  絕對風險數字（5.3% vs 4.0%, 安慰劑對照）提供了一個重要的平衡視角——pitavastatin 相對於**完全
  不使用 statin**仍會增加 NODM 絕對風險，只是**相對於其他強效 statin**風險較低。建議
  safety-pharmacology 在其 owned evidence 中自行評估是否納入此交叉引用。
- **對本專案主軸的定位建議**：REPRIEVE 是一篇高品質、大型、正向的 pitavastatin 心血管結果 RCT，
  可作為「pitavastatin 這個分子本身具備 hard-outcome 證據基礎」的有力背景佐證，但因族群
  （HIV、初級預防）與 `pitavastatin topic.md` 主要臨床情境（Taiwan 一般三高族群、次級預防為主）
  有明顯落差，**不建議直接等同於「pitavastatin/ezetimibe FDC 對台灣一般族群的 hard-outcome
  證據」**——引用時應清楚註明族群限制，作為第四個獨立參考點而非 Level 3 證據的替代或加強。

### TE-012 — Taguchi I et al. Circulation 2018;137(19):1997-2009（REAL-CAD trial，T-016，本角色於 2026-08-31 主動驗證，Director Decision 2026-08-31-19 授權）

- Evidence Hierarchy：**DIRECT EVIDENCE**，同樣是 pitavastatin **單方**（非 FDC）的 hard-outcome
  RCT，但問題與 TE-011（REPRIEVE）不同——這是**pitavastatin 劑量強度**（4mg vs 1mg）本身的
  比較，收案為**日本穩定型 CAD 二級預防**族群（非 HIV 初級預防）。
- N=13,054 隨機分派 1:1（高劑量 4mg n=6526／低劑量 1mg n=6528），中位追蹤 3.9 年。收案前先經
  pitavastatin 1mg run-in period 確認 LDL-C<120 mg/dL。
- Baseline LDL-C（run-in 後）：高劑量組 87.7 mg/dL vs 低劑量組 88.1 mg/dL；追蹤期間高劑量組
  LDL-C 平均低 14.7 mg/dL（p<0.001）。
- **Primary endpoint**（CV 死亡、非致死性 MI、非致死性缺血性中風、需急診住院的不穩定心絞痛）：
  266(4.3%) vs 334(5.4%)；**HR 0.81, 95% CI 0.69–0.95, P=0.01** — 達統計顯著。
- Secondary composite endpoint（primary + 臨床指示之冠脈血運重建）：489(7.9%) vs 600(9.7%)；
  HR 0.83, 95% CI 0.73–0.93, P=0.002。
- **此為 Q8 的完整解決**：TE-002（Tsujita 2023）全文中曾二手引用此試驗數字（HR 0.81, 95% CI
  0.69–0.95）作為其「選擇 2mg/4mg 為 FDC 劑量」的立論依據之一，本角色現已獨立驗證原始發表，
  數字**完全吻合**，TE-002 的這項立論依據站得住腳。
- **與 TE-011（REPRIEVE）合併觀察**：兩篇獨立、大型、正向的 pitavastatin 單方 hard-outcome
  RCT（REAL-CAD 二級預防 CAD 族群、REPRIEVE 初級預防 HIV 族群）共同構成「pitavastatin 這個分子
  本身具備 hard-outcome RCT 證據基礎」的有力背景，可作為 `40_SYNTHESIS/` 中與
  `pitavastatin topic.md` §6 Level 1/2/3（FDC 專屬）框架**並列但不混淆**的第四類參考點。
  兩者皆非 FDC/ezetimibe 併用證據，**不可**用來替代或加強 Level 3（HIJ-PROPER）的 FDC-hard-outcome
  證據缺口，僅能佐證「pitavastatin 本身劑量與強度具有心血管結果證據」這個相鄰但獨立的論點。

---

## 補充：Wave 2 尾聲新發現的兩筆來源（2026-08-31，重試 Chou 2022 全文時意外找到）

### TE-014 — Abbas MS et al. Future Cardiol 2026;22(6):607-619（**可能是本專案最直接相關的既有統合分析**）

- 這是本專案目前找到的**第一篇專門針對 pitavastatin+ezetimibe FDC**（而非泛統計所有
  statin+ezetimibe 組合）的系統性回顧/統合分析，PROSPERO 已註冊（CRD420251233057），納入條件
  明確為「pitavastatin 2mg 或 4mg + ezetimibe 10mg vs pitavastatin 2mg 單方的 RCT」——這個納入
  條件與 TE-001（Chou 2022）、TE-002（Tsujita 2023）高度吻合，**極可能就是以這兩篇（或其中一篇）
  為核心納入研究**，但本角色**尚未取得全文確認實際納入清單**。
  Evidence Hierarchy：**INSUFFICIENT EVIDENCE**（abstract 層級無法取得任何量化 pooled 數字——
  Results 段落異常簡短，僅列出結果變項名稱，未附 MD/RR/CI/p-value，可能是索引摘要本身的截斷，
  非本角色遺漏摘錄）。
- **強烈建議列為 Wave 3 全文取得最高優先序**——若能取得全文，可能直接補上/驗證
  `pitavastatin topic.md` §6 Level 1 證據的「正式統合分析」層級佐證，這是目前專案缺乏的一塊。

### TE-013 — Lu YW et al. Acta Cardiol Sin 2026（Taiwan 真實世界 post-PCI 世代）

- Evidence Hierarchy：**OBSERVATIONAL EVIDENCE**（回溯性真實世界世代，單臂、無對照組、N=120，
  台灣兩家醫學中心，2008–2021 收案）。
- Pitavastatin 4mg + ezetimibe 10mg（P4/E10，**較高劑量**的 FDC 組合）於 post-PCI（次級預防、
  高風險）病人中使用 >1 年：12 個月 LDL-C 降幅 32.54%；糖尿病次族群 HbA1c 變化 −0.40%、
  TyG index 變化 −0.23。
- **⚠ Numeric Integrity 提醒（Wave 3 全文已證實此提醒站得住腳）**：本研究聲稱「研究期間無任何
  AE 記錄」——在長達 13 年收案窗口（2008–2021）、N 僅 120 的回溯性病歷回顧研究中，這是一個異常
  強烈的安全性宣稱，較可能反映回溯性資料蒐集對 AE 的系統性低估（非結構化追蹤，非如 RCT 般主動
  系統性詢問），而非真正零 AE。**Wave 3 取得全文後證實**：作者本人在 Discussion／Limitations
  中明確承認此限制（「adverse events were assessed based on information recorded in the
  patients' medical charts... minor or transient adverse effects that were not documented in
  the notes may have been missed」）——本角色 Wave 2 憑 abstract 層級數字所做的謹慎判斷，經全文
  獨立證實為作者自己也認可的限制，非本角色過度懷疑。`40_SYNTHESIS/` 若引用此研究的安全性結論，
  **不應**與 TE-002（Tsujita 2023 RCT，有系統性 AE 追蹤與分組統計檢定）的安全性證據等量齊觀，
  應明確標註證據層級差異。
- 對 `pitavastatin topic.md` 而言，這是難得的**台灣本地、高劑量 FDC、post-PCI 高風險族群**真實
  世界資料，可作為 Level 1/2 證據的台灣本土佐證，補足 TE-001（Chou 2022，一般 hypercholesterolemia
  族群）與 TE-002/003（日本族群）之外的台灣次級預防真實世界視角。
- **Wave 3 全文新增細節**（完整數字見 `extraction-table.csv` TE-013 notes 欄）：依前次降脂治療
  暴露分層後，statin-naïve 病人的 LDL-C 降幅（−38.47%）明顯大於曾用 statin+ezetimibe（−16.03%）
  或曾用 statin 單方（−13.17%）者——這個「治療反應隨前次暴露遞減」的型態，對詮釋真實世界 FDC
  效果時應納入考量，不應直接與 treatment-naïve RCT 族群（如 TE-001/002/015）的效果量直接比較。
  另外，全文引用本專案已驗證的 HIJ-PROPER（TE-004）作為效果量的參照基準點，顯示這篇真實世界
  研究的作者本身也將其結果放入既有的 pitavastatin+ezetimibe 證據脈絡中討論。

---

## 補充：FDC 劑型本身（非 pitavastatin 專屬）的 adherence/efficacy 佐證

### TE-010 — Katzmann JL et al. Clin Res Cardiol 2022（德國真實世界 EMR 分析，T-012，Director 指派於 2026-08-31）

- Evidence Hierarchy：**OBSERVATIONAL EVIDENCE**（retrospective real-world EMR 分析，非
  RCT；且非 pitavastatin 專屬 — statin 種類未明確限定為 pitavastatin，應理解為泛統計所有
  statin+ezetimibe 用藥模式）。
- 支持「FDC 優於分開服用兩顆藥」的 adherence/efficacy 敘事（呼應 `pitavastatin topic.md`
  對 FDC 簡化用藥的核心賣點）：加用 ezetimibe 於 statin 之上，FDC 劑型使 LDL-C 額外下降 28.4%
  （40.0±39.1 mg/dL），優於分開服用兩顆藥的 19.4%（27.5±33.8 mg/dL），p<0.0001；LDL-C<70
  mg/dL 達標率 FDC 31.5% vs 分開服用 21.0%。**此四個數字已與 PubMed abstract 原文逐字核對一致**。
- **⚠ 待 Wave 2 全文覆核的樣本數矛盾**：`Tonvasca_2026.md` 同一張投影片標題與結果表格分別列出
  兩組不同、且大小關係相反的樣本數（n=6,429/533 於標題 vs n=1,639/796 於表格）。已依 Numeric
  Integrity Rule 如實保留、標記 `POSSIBLE_ERROR`，見 `unresolved-questions.md` Q7 與
  `10_DATA/trials-efficacy/extraction-table.csv` TE-010 notes 欄。**在此矛盾透過全文解決之前，
  `40_SYNTHESIS/` 或未來簡報若要引用此篇的樣本數，應避免直接沿用 `Tonvasca_2026.md` 投影片上的
  任一組 n，或需並列兩組數字並註明來源不一致。**

---

**Wave 1 結論**：`01_RESEARCH-CHARTER.md`「Major uncertainty」中列出的疑慮——「是否存在
HIJ-PROPER 之外的 pitavastatin/ezetimibe 專屬 hard-outcome 證據」——經 Wave 1 檢索，**未發現**
任何新的、更新的、pitavastatin/ezetimibe 專屬的 hard-outcome RCT。三層證據框架的說服力分布（
Level 1 強、Level 2 強但非藥物專屬、Level 3 尚未充分證明）在 Wave 1 之後**維持不變，且獲得更嚴謹
的原始文獻數字確認**。
