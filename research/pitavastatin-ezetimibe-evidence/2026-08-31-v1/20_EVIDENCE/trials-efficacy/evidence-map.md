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
  - **2mg+eze10 vs 4mg 單方**：−51.4% vs −45.2%（加 ezetimibe 優於加倍劑量至 4mg）。
  - **2/10 vs 4/10**：−51.4% vs −57.8%（4mg 起始仍能再多降約 6.4 個百分點，但需權衡劑量遞增的
    邊際效益 vs pitavastatin 高劑量本身的 AE/CK/肝功能負擔，本研究 abstract 未細分各劑量組的
    AE 發生率差異 — 見 unresolved-questions Q2，需全文的分組安全性表格）。
- 安全性：AE/ADR 發生率在 FDC 與單方組間無顯著差異；肝功能與肌病變相關檢驗值雖上升但仍在
  參考範圍內。

### TE-003 — Ako J, Yokote K, Tsujita K, et al. J Atheroscler Thromb 2024（K-924 52 週延伸試驗）

- Evidence Hierarchy: **DIRECT EVIDENCE**，但為單臂設計（無同期 monotherapy 對照組），僅能佐證
  「statin 單方未達標病人轉換為 FDC 後」的長期（52 週）LDL-C 降幅與安全性，不能直接回答
  「add ezetimibe vs dose escalation」的隨機比較問題。
- 109 名 pitavastatin 單方未達 LDL-C 目標的病人轉換為 K-924 後，52 週 LDL-C 降幅 −30.3±14.3%
  （p<0.001）；一級預防族群 91.8% 達標、二級預防族群僅 37.5% 達標 — 這個「二級預防達標率明顯偏低」
  的數字，對強化「即使加上 ezetimibe，極高風險/二級預防病人仍可能無法單靠 pitavastatin/ezetimibe
  FDC 達到 <55 mg/dL 的 2026 ACC/AHA 目標」這條 guideline-risk 相關論述，是有用的交叉引用素材。

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

**Wave 1 結論**：`01_RESEARCH-CHARTER.md`「Major uncertainty」中列出的疑慮——「是否存在
HIJ-PROPER 之外的 pitavastatin/ezetimibe 專屬 hard-outcome 證據」——經 Wave 1 檢索，**未發現**
任何新的、更新的、pitavastatin/ezetimibe 專屬的 hard-outcome RCT。三層證據框架的說服力分布（
Level 1 強、Level 2 強但非藥物專屬、Level 3 尚未充分證明）在 Wave 1 之後**維持不變，且獲得更嚴謹
的原始文獻數字確認**。
