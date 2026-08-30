# evidence-map — trials-efficacy-intelligence / Wave 1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Role: trials-efficacy-intelligence · Wave: 1

本檔案將 `10_DATA/trials-efficacy/extraction-table.csv` 的原始數字，依 `pitavastatin topic.md`
§6（Level 1/2/3 hard-outcome evidence hierarchy）與 CLAUDE.md §7（Evidence Hierarchy 標籤）組織
成可供 Wave 3 synthesis 直接引用的證據地圖。所有 citation_id 對應 extraction-table.csv。

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
