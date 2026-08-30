# evidence-map — safety-pharmacology-intelligence

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Owner: safety-pharmacology-intelligence

每筆 claim 皆標示 Evidence Hierarchy（CLAUDE.md §7）與 activity 來源
（`LEGACY_VERIFICATION` = 驗證 `Tonvasca_2026.md` 既有引用；`NEW_SOURCE_DISCOVERY` = 本輪新搜尋，
未見於 legacy 文件）。精確數字另見 `10_DATA/safety-pharmacology/extraction-table.csv`；DDI 專用表見
`ddi-matrix.md`。所有數字皆逐字保留原文，如遇疑似錯誤已標 `FLAG = POSSIBLE_ERROR`，不逕行修正
（Numeric Integrity Rule, CLAUDE.md §9）。

---

## 1. Pitavastatin 血糖/NODM 安全性（Search Protocol item 3）

> 語言校準提醒（CLAUDE.md §5 item 3）：本節任何敘述禁止寫成 "pitavastatin does not cause
> diabetes"；正確框架為 "pitavastatin may have a more favorable glycemic profile than some other
> potent statins."

### 1.1 「2024 systematic review/meta-analysis」的具體定位 — NEW_SOURCE_DISCOVERY

**Singh H, Kaur S, Kaushal P, Sharma J, Singla M.** "Risk of new onset diabetes mellitus with
pitavastatin as compared to atorvastatin and rosuvastatin: a systematic review and meta-analysis."
*Expert Rev Clin Pharmacol.* 2024 Dec;17(12):1173-1181. PMID 39587804. DOI
10.1080/17512433.2024.2433603. PROSPERO CRD42022371741.

- 設計：SRMA，13 篇研究（RCT + observational 混合），來源 PubMed/CENTRAL/EMBASE/
  ClinicalTrials.gov，篩選 517 筆紀錄；風險偏差評估用 JBI/Newcastle-Ottawa/SIGN checklist；
  RevMan 5.4.1 統計。
- 結果（逐字保留）：pitavastatin vs atorvastatin RR = 0.86, 95% CI = 0.79–0.93, p = 0.0002；
  pitavastatin vs rosuvastatin RR = 0.77, 95% CI = 0.71–0.84, p < 0.00001。
- **Evidence Hierarchy: INDIRECT EVIDENCE**（統計層級為 pooled RCT+observational meta-analysis，
  對「pitavastatin 相對其他 statin 的 NODM 風險」而言屬直接比較性證據，但因混合 RCT 與
  observational 且未逐一取得各納入研究之原始數據，暫標 INDIRECT EVIDENCE，待與各納入 RCT
  對照後可考慮升級）。
- 驗證方式：PubMed 標題/摘要層級核對，**未取得全文逐字核對** — `CONFIDENCE: MODERATE`。
- **Wave 2 更新**：經 Europe PMC 查證 `is_open_access: false`，無 PMCID —— **全文合法取得管道
  已確認為 BLOCKED_FOR_SOURCE**（非未嘗試，而是查證後確認無開放取用管道），已取得之完整結構化
  摘要（Background/Methods/Results/Conclusion 皆完整，含 PROSPERO 註冊碼）已足供本專案目前需求，
  數字與先前一致，`CONFIDENCE` 維持 MODERATE（摘要層級，非全文逐字）。
- **與 `pitavastatin topic.md` 的對應**：此篇與 topic notes 所述「2024 systematic review/
  meta-analysis 納入 RCT 與 observational studies，顯示 pitavastatin 相較 atorvastatin/
  rosuvastatin 的 new-onset diabetes risk 較低」完全吻合，建議 Director 將本篇登錄為 T-003 的
  正式來源（`02_SOURCE-INVENTORY.md` 由 Director 更新，本角色僅回報）。

### 1.1b 比較基準提醒（trials-efficacy 提供，2026-08-31）：REPRIEVE 試驗與 Singh 2024 不可直接合併

trials-efficacy-intelligence 驗證的 REPRIEVE 試驗（pitavastatin 4mg vs placebo, HIV 族群, MACE
HR 0.65）之糖尿病訊號為 5.3%（pitavastatin）vs 4.0%（placebo）—— 這是 **placebo 對照之絕對風險
比較**，與 Singh 2024（T-003）之 **其他 statin 相對風險比較**（RR 0.86 vs atorvastatin, RR 0.77
vs rosuvastatin）為不同問題/不同比較基準，**非互相矛盾，但不可直接合併為單一數字**。撰寫
glycemic-outcomes synthesis 時務必分別標示比較對象（placebo vs 其他 statin），不得混用。

### 1.2 重要區辨：Sydhom P et al. 2024 並非同一篇（LEGACY_VERIFICATION，見 §5 全文）

`Sydhom P, et al. BMC Cardiovasc Disord. 2024;24(1):660`（`02_SOURCE-INVENTORY.md` #26）
是「low/moderate-intensity statin + ezetimibe vs high-intensity statin monotherapy」的策略性
meta-analysis，NODM 只是其中一個 observational-only 次要結果（HR 0.80, 95% CI 0.74–0.87，
支持 combination therapy），**不是** pitavastatin 對其他 statin 的頭對頭 NODM 比較。
**Decision 建議（NEEDS_ANALYST，交 Director 登錄至 03_DECISION-LOG.md）**：manuscript 撰寫時
不得將 Singh 2024 與 Sydhom 2024 交互引用或合併陳述其結論。

### 1.3 Head-to-head / cohort 證據總表 — NEW_SOURCE_DISCOVERY

完整逐字數字見 `extraction-table.csv`。摘要：

| Study | 設計 | 族群 | Evidence Hierarchy | 重點 |
|---|---|---|---|---|
| Seo WW et al. 2022, Cardiovasc Diabetol (PMID 35606846) | Distributed network cohort, 10 個 OMOP-CDM real-world DB（韓國），PSM 1:2 | 新使用 statin、無基礎 DM/HbA1c≥5.7% | OBSERVATIONAL EVIDENCE | pitavastatin vs atorva+rosuva 合併 HR 0.72 (0.59–0.87) |
| Vallejo-Vaz AJ et al. 2015, Atherosclerosis (PMID 26074315) | MA, 15 RCTs, ~1600 person-yrs | 非糖尿病族群 | INDIRECT EVIDENCE（統合非糖尿病族群 RCT） | NOD RR 0.70 (0.30–1.61)，作者自陳可能有 publication bias；FBG/HbA1c 無統計差異 |
| **Liu PY et al. (PAPAGO-T) 2013, PLoS ONE (PMID 24098467)** | RCT, double-blind, non-inferiority, 12wk，**台灣** | 高風險漢族，n=225（含 DM 次族群 n=125） | DIRECT EVIDENCE（唯一台灣 RCT） | pitavastatin 2mg vs atorvastatin 10mg；DM 次族群 HbA1c 顯著較低於 atorvastatin 組（p=0.001）。**注意**：PLoS One 2014;9(11):e114175 有 erratum，引用前應先核對 erratum 內容 |
| Huang CH et al. 2016, J Diabetes Investig (PMID 27181110) | Retrospective chart review, 6mo，**台灣**（長庚） | T2DM, n=222 | OBSERVATIONAL EVIDENCE | Naive→pitavastatin HbA1c 8.1→7.4% (p=0.018)；atorvastatin 換藥組 9.7→9.0% (p=0.015) |
| Sasaki J et al. 2008, Clin Ther (PMID 18640465) | RCT, open-label, 52wk，日本 | 89% 已有 DM, n=173 | DIRECT EVIDENCE | 血糖代謝指標組間無顯著差異；HDL-C 改善優於 atorvastatin (p=0.031) |
| Mita T et al. 2013, J Diabetes Investig (PMID 24843669) | RCT, quasi-randomized crossover，日本 | T2DM, n=28 | DIRECT EVIDENCE | HbA1c 差異 -0.18% (95% CI -0.34, -0.02), p=0.03，有利 pitavastatin |
| Nakagomi A et al. 2015, J Atheroscler Thromb (PMID 26084792) | RCT, 12mo，日本 | 無已知 CVD 的高血脂族群, n=146 | DIRECT EVIDENCE | atorvastatin 5mg vs **pitavastatin 1mg**：HOMA-IR +26% vs -13% (p<0.001) |
| Yanagi K et al. 2011, Adv Ther (PMID 21222064) | RCT, 24wk，日本 | T2DM, n=90 | DIRECT EVIDENCE | rosuvastatin 2.5mg vs pitavastatin 2mg；摘要僅敘述「無不良血糖影響」未附數字 |
| Cui JY et al. 2018, J Clin Pharm Ther (PMID 29733433) | Network meta-analysis, 23 RCTs | T2DM | INDIRECT EVIDENCE | 中強度 pitavastatin vs 高強度 atorvastatin HbA1c SMD -0.77 |
| Chapman MJ et al. (CAPITAIN/PREVAIL-US) 2014, Curr Med Res Opin (PMID 24328357) | RCT (CAPITAIN n=12) + PREVAIL-US 驗證子集 (n=9) | 代謝症候群 | DIRECT EVIDENCE — **高劑量 pitavastatin 4mg** 資料 | HbA1c/insulin/HOMA-IR/QUICKI 無顯著變化；FPG 微升 +4% (p<0.05) |
| Lee J et al. 2022, J Clin Med (PMID 36431233) | RCT, open-label, 24wk，韓國 | T2DM, n=93 | DIRECT EVIDENCE | pitavastatin 2mg vs 飲食/運動；HOMA-IR 差異未達顯著 (p=0.59 / p=0.36) |
| Devi G et al. 2025, Cureus (PMID 40964577) | RCT, open-label, 12wk，印度 | T2DM+dyslipidemia on metformin+glimepiride | DIRECT EVIDENCE | pitavastatin 4mg vs atorvastatin 20mg；FBG 改善 22.7±11.6% vs 15.4±6.4% (p=0.004)；HbA1c 未達顯著 (p=0.09) |

### 1.3b Elderly 次族群新證據（Wave 2, NEW_SOURCE_DISCOVERY）— 部分填補先前 elderly 缺口

**Li H, Li J.** "Association of Pitavastatin Versus Atorvastatin Therapy With Glycaemic Control and
New-Onset Diabetes in Older Adults With Atherosclerotic Cardiovascular Disease." *Br J Hosp Med.*
2026 Jul;87(7). PMID 42528438. DOI 10.31083/bjhm56151.

- 設計：回溯性世代研究，Public Health Clinical Center Affiliated to Shandong University（中國），
  2022年1月–2023年12月，隨訪 12 個月。
- 族群：ASCVD 老年病人 ≥60 歲，n=126（pitavastatin 4mg/day, n=58 vs atorvastatin 20mg/day, n=68）。
- 結果（逐字）：HDL-C 1.41±0.30 vs 1.26±0.28 mmol/L (p=0.005)；FPG 5.85±0.70 vs 6.19±0.85 mmol/L
  (p=0.018)；HbA1c 6.10±0.42% vs 6.33±0.51% (p=0.009)；**NODM 0% (pitavastatin) vs 10.29%
  (atorvastatin)**；多變量邏輯回歸 OR=0.212 (p=0.018)（pitavastatin 為保護因子）。
- **Evidence Hierarchy: OBSERVATIONAL EVIDENCE**（回溯性世代研究，非 RCT）。
- **Full-text 狀態**：經 Europe PMC 查證 `is_open_access: false`，無 PMCID —— **BLOCKED_FOR_SOURCE**
  （全文無法透過合法免費管道取得），僅取得完整結構化摘要（Crossref + Europe PMC 皆提供，內容一致）。
- **重要限制**：此為單一中心、非隨機、樣本數小（n=126）之回溯性研究，且劑量非對等
  （pitavastatin 4mg 為其最高劑量，atorvastatin 20mg 為中等劑量，非對等劑效比較）——引用時需
  明確揭露此設計限制，不可作為「pitavastatin 於老年族群優於 atorvastatin」之高強度證據，僅為
  部分填補本項目原先標註的 elderly-subgroup 資料缺口的**支持性**觀察證據。

**Dose-response 缺口（Search Protocol item 5 的血糖面向）**：查無 pitavastatin 1mg vs 2mg vs 4mg
「同一試驗內」head-to-head glycemic RCT；現有 dose-response 推論須跨試驗拼接（Nakagomi=1mg，
PAPAGO-T/Sasaki/Mita=2mg，CAPITAIN/Devi=4mg），方法學上弱於真正的 dose-ranging 設計 — 若
manuscript 要做 dose-response 論述，須明確揭露此限制。

### 1.4 已知但未取得結果之試驗 — BLOCKED_FOR_SOURCE 候選

- **CAMPUS**（中國，pitavastatin 2mg vs atorvastatin 20mg，n=396 計畫，prediabetes+HTN+
  dyslipidemia，12mo，HbA1c primary）— protocol PMID 30187345，ClinicalTrials.gov
  NCT03532620。**結果論文未找到**，需查 ClinicalTrials.gov completion status 後再確認是否已發表。
- **LESS-DM**（pitavastatin 4mg vs atorvastatin 20mg，n=500 計畫，MetS，24mo，HbA1c primary +
  NODM/CVD incidence secondary）— protocol PMID 29078817。**結果論文未找到**。
- "**J-PREDICT**"（若曾出現於任何 legacy 資料中，指稱 pitavastatin 糖尿病預防試驗）——
  多組關鍵字搜尋均**查無此名稱**之 PubMed 收錄試驗。**在有具體引用出現前，不應在本專案任何
  文件中使用此名稱**，若日後於 legacy 材料中發現，應視為 unverified/可能誤植，交 NEEDS_PI。

---

## 2. Drug-Drug Interaction（DDI）— Search Protocol item 4

> 語言校準提醒（CLAUDE.md §5 item 4）：禁止「Pitavastatin 沒有 DDI」，正確框架為
> "Pitavastatin has low CYP3A4-dependent interaction liability"。完整交互作用矩陣見
> `ddi-matrix.md`；本節僅摘要機轉與 Evidence Hierarchy。

### 2.1 代謝機轉 — NEW_SOURCE_DISCOVERY, MECHANISTIC SUPPORT / DIRECT EVIDENCE（label 層級）

**主要來源：LIVALO（pitavastatin calcium）US FDA 藥品仿單**（DailyMed setid
44dcbf97-99ec-427c-ba50-207e0069d6d2），Section 7 Drug Interactions，逐字擷取：

> "There is only minimal metabolism by the cytochrome P450 system. Pitavastatin is marginally
> metabolized by CYP2C9 and to a lesser extent by CYP2C8."

此為 **INSTITUTIONAL PRACTICE / 官方 label 層級之 DIRECT EVIDENCE**（非 peer-reviewed 論文，但為
主管機關核准之權威來源）。label 原文**未使用**「no CYP3A4 metabolism」字樣，而是「minimal」——
與本專案要求的「low CYP3A4-dependent liability」框架一致，優於「no DDI」的過度簡化。

補充機轉證據（MODERATE 信心，來自綜述型文章片段，未逐字全文核對，標記 **MECHANISTIC SUPPORT**）：
- OATP1B1 據稱佔 pitavastatin 肝臟清除約 90%（多篇 pharmacology-profile 綜述引用此數字，本輪
  未能鎖定單一可逐字核對之原始來源 — 列入 `unresolved-questions.md`，建議下一輪指名搜尋原始
  transporter PK 研究）。
- BCRP：pitavastatin 據信為 BCRP 受質（與 rosuvastatin 共同），但本輪未取得具體 BCRP-inhibitor
  交互作用之 fold-change 數字 — **OPEN GAP**。
- Itraconazole（強效 CYP3A4 抑制劑）研究標題："Pitavastatin Concentrations Are Not Increased by
  CYP3A4 Inhibitor Itraconazole in Healthy Subjects"（PMID 27121674）——僅取得標題，未取得摘要
  逐字數字，若成立將是「低 CYP3A4-dependence」最直接的機轉驗證研究之一，**下一輪應優先全文
  核對**。

### 2.2 具體藥物交互作用 — 詳見 `ddi-matrix.md`

Cyclosporine（禁忌）、erythromycin（劑量上限 1mg/day）、rifampin（劑量上限 2mg/day）、
gemfibrozil（避免併用）、fenofibrate（無限制但有 AUC/Cmax 上升）之逐字 fold-change 數字，
全部來自 FDA label 直接引用，**Evidence Hierarchy: DIRECT EVIDENCE（regulatory label）**。
Clarithromycin 特異性交互作用數字本輪**未在擷取到的 label 段落中找到**（label 段落擷取可能不
完整，僅涵蓋 erythromycin 做為 macrolide 代表）— 列 `unresolved-questions.md`，非「無交互作用」
的結論，僅為本輪未查獲。

### 2.3 臨床應用情境（老年 + HTN + DM + CAD + CCB + 抗血小板/抗凝血）

本輪聚焦於藥品標籤與 pitavastatin 特異性資料，**尚未**針對「老年+HTN+DM+CAD+CCB+
抗血小板/抗凝血」的複合病例情境做整合寫作 — 此為敘事整合工作，留待 Wave 2/Synthesis 階段，
惟以下既有引用（LEGACY_VERIFICATION，已於 §5 全文列出）可直接支援該情境：
Fravel MA/Ernst M 2021（diltiazem/verapamil 為 CYP3A4 主要抑制來源）、Zanchi A 2012（腎功能與
降血糖藥物交互作用）、May M/Schindler C 2016（降血糖藥物交互作用風險分層）、Ehelepola NDB 2017
（statin+CCB 橫紋肌溶解案例報告）、Engell AE 2021（statin+warfarin INR 變化）、Harężlak T 2022
（Triple Whammy AKI 機轉）。

---

## 3. 2mg vs 4mg 劑量比較 + Add-ezetimibe vs Dose Escalation（Search Protocol item 5，與 trials-efficacy 共同）

### 3.1 Chou MT et al. 2022（1PC111，Taiwan/Australia/NZ）安全性資料 — **未能取得，NEEDS_ANALYST**

本輪透過 Crossref 確認全文作者名單與 DOI（10.1016/j.clinthera.2022.08.006：Ming-Ting Chou,
Anthony McGirr, Gwo-Ping Jong, Ting-Hsing Chao, I-Te Lee, Chun-Yao Huang, Ching-Pei Chen,
Chang-Hsun Hsieh, Chieh-Hsiang Lu, Wayne Huey-Herng Sheu），但**未能取得該試驗 AE/CK/肝功能表格
之逐字數據**（ScienceDirect/PubMed 本輪皆遇 403/付費牆）。搜尋片段中出現一組數字
「ADR 8.6%/6.1%/7.0%（三組）」，**來源為 AI 生成之搜尋摘要，非直接引用自原文** —
**`CONFIDENCE: LOW`，`FLAG = UNVERIFIED_SECONDARY`，`ACTION = NEEDS_ANALYST`，本表不予採用，
不得進入 40_SYNTHESIS 或任何 manuscript 草稿**，待 `research_hub`/`llamaparse` 或直接 PDF 存取
後重新查證。（另發現一篇可能佐證的 conference abstract：Chou MT, Atherosclerosis 2023;379(S1):
S43, DOI 10.1016/j.atherosclerosis.2023.06.803 — 尚未核對。）

### 3.2 K-924（Kowa, 日本）2mg/4mg ± ezetimibe 劑量比較 — NEW_SOURCE_DISCOVERY, **INDIRECT EVIDENCE**

> **重要區辨**：K-924 為日本 Kowa 藥廠之 pitavastatin/ezetimibe FDC 產品，**非** Chou MT 2022 的
> Taiwan/Australia/NZ 試驗，族群、地區、產品名稱皆不同。以下數據對 K-924 本身為 DIRECT EVIDENCE，
> 但對「pitavastatin/ezetimibe 一般化劑量策略」而言僅為 **INDIRECT EVIDENCE**（不同 FDC 產品，
> 相同藥理機轉類別）。

**12 週雙盲 RCT**：Tsujita K, Yokote K, Ako J, Tanigawa R, Tajima S, Suganami H. *J Atheroscler
Thromb.* 2023. PMID 36908150, PMC10627746. 四臂設計：pitavastatin 2mg (PS2) vs 4mg (PS4) vs
2mg/ezetimibe10mg (K-924 LD) vs 4mg/ezetimibe10mg (K-924 HD)。

| 指標 | PS2 | PS4 | K-924 LD (2/10) | K-924 HD (4/10) |
|---|---|---|---|---|
| LDL-C % change | −39.5% | −45.2% | −51.4% | −57.8% |
| 整體 AE | 16.7% (12/72) | 26.4% (19/72) | 25.0% (18/72) | 19.4% (14/72) |
| ADR | 2.8% | 6.9% | 5.6% | 6.9% |
| CK 上升事件 | 2.8% | 4.2% | 1.4% | 0% |
| CK Δ from baseline (wk12) | +14.9±64.6 U/L | +50.9±247.7 U/L | +19.6±48.2 U/L | +22.0±50.5 U/L |
| ALT 上升 | 0% | 5.6% | 2.8% | 5.6% |
| AST 上升 | 0% | 0% | 1.4% | 2.8% |
| HbA1c | 無明顯變化 | 微升 (≤0.11%) | 微升 | 微升 |

**Key finding：K-924 LD（pitavastatin 2mg + ezetimibe 10mg）的 LDL-C 降幅（−51.4%）已優於
PS4（pitavastatin 4mg 單用，−45.2%）**，直接支持「加 ezetimibe 優於劑量加倍」的臨床決策論述
（`pitavastatin topic.md` §4 第 77-78 行所述 "Add ezetimibe or double the statin?" 的直接數據
佐證之一，惟來自不同產品/族群）。無患者達到預先設定的 CK/AST/ALT 異常判定標準。無新診斷糖尿病
案例報告。**CKD/elderly 次族群安全性資料本篇未報告**。

**52 週開放性延伸研究**：Ako J, Yokote K, Tsujita K, et al. *J Atheroscler Thromb.*
2023;31(3):288-305. PMC10918028. 延續 K-924 HD/LD 組別。

- 52 週整體 AE 發生率 59.6%（65/109 病人，129 事件），ADR 0.9%；嚴重 AE 11.0%（12 病人，15
  事件）；因 AE 停藥 0.9%（1 病人）。
- 肌肉：ADR「blood creatine phosphokinase increased」1 例（K-924 HD 組），該病人 CK
  baseline 202 U/L → wk12 843 U/L，其後回復至 125–438 U/L；無病人達 ≥10×ULN CK。
- 肝功能：無病人於連續兩次追蹤達 ≥3×ULN ALT/AST。
- 血糖：blood glucose 113.6±17.8 → 116.1±22.1 mg/dL (p=0.049)；HbA1c 6.39±0.72% →
  6.55±0.85% (p<0.001) — 統計上顯著但變化幅度小，原文將其定性為「維持在/接近參考範圍內」，
  **非**新診斷糖尿病報告。
- **CKD/elderly 次族群安全性資料本篇亦未報告** — 列 BLOCKED_FOR_SOURCE 候選（見
  `unresolved-questions.md`）。

---

## 4. STS（Suboptimally Tolerable Statins）vs 正式 Statin Intolerance 定義

> 校準提醒：STS 為 GUIDELINE/CONSENSUS 層級之台灣本土概念，非 CV-outcome 證據（CLAUDE.md §7 已
> 明訂此陷阱）；本節僅描述其與正式定義的差異，不引申為療效聲明。

### 4.1 Taiwan STS 2026 共識 — NEW_SOURCE_DISCOVERY, GUIDELINE/CONSENSUS, `CONFIDENCE: MODERATE`

**Wu YJ, Yeh CF, Hsu CY, Lin CF, Huang CC, Tang SC, Huang YC, Lin CY, Yu CH, Huang CY, Wang CY,
Huang PH, Yeh HI, Li YH, Liu PY.** "2026 Taiwan Society of Lipids and Atherosclerosis consensus
statement for the identification and management of patients receiving suboptimally tolerable
statins." *J Formos Med Assoc.* 2026 Apr. DOI 10.1016/j.jfma.2026.04.111.

完整作者名單與 DOI 已經 Crossref 確認存在（**FOUND，非 NOT_FOUND** — 更正 Wave 0
`02_SOURCE-INVENTORY.md` T-005 列「Not yet located」之狀態，交由 Director 更新該檔案）。
**全文本身仍為付費牆，以下內容來自搜尋引擎摘要層級 synopsis，非逐字引用全文** — 建議下一輪嘗試
透過 台灣脂肪與動脈硬化學會（TAS）官網直接取得 PDF（該學會曾公開釋出過姊妹文件 PDF）。

內容摘要（非逐字，待全文核對）：STS 被描述為「a pragmatic concept that extends beyond the
traditional and restrictive definition of statin intolerance」，涵蓋「patients unable to
maintain recommended statin intensity because of real or perceived adverse effects, even when
formal [statin intolerance] criteria are not met」。治療演算法：high/very-high risk 以
ezetimibe 為第一線 add-on；extremely-high-risk 患者及早合併治療（ezetimibe + bempedoic acid），
LDL-C 未達 <55 mg/dL 則儘速升級至 PCSK9-based therapy。此與 `CLAUDE.md` §2.2/§5 item 2 對 STS
的描述高度一致。

### 4.2 前身文件（LEGACY_VERIFICATION）：2019 台灣脂肪與動脈硬化學會 statin intolerance 共識

**Chien SC, Chen PS, Huang YH, Tang SC, Li YH, Yeh HI.** "2019 Taiwan Society of Lipids and
Atherosclerosis expert consensus statement on statin intolerance." *J Formos Med Assoc.*
2019;118(10):1385-1392. DOI 10.1016/j.jfma.2018.11.017. PMID 30584005.

**重要更正**：`02_SOURCE-INVENTORY.md` 目前將此列為「Statin discontinuation outcomes」主題
（#23），經本輪核對，**其實際主題是 2019 年版 statin intolerance 正式共識**，是 2026 STS 共識的
直接前身文件 —— 屬本角色 Evidence Hierarchy: GUIDELINE/CONSENSUS，非 outcome 數據。已回報
Director 更新 `02_SOURCE-INVENTORY.md` 該列 topic 描述（本角色無該檔案寫入權）。

### 4.3 國際正式 statin intolerance 定義（對照基準）— NEW_SOURCE_DISCOVERY, GUIDELINE/CONSENSUS

- **NLA 2022**（Bays H et al., *J Clin Lipidol* 2022, PMID 35718660）：定義 statin intolerance 為
  「one or more adverse effects associated with statin therapy which resolve or improve with
  dose reduction or discontinuation」，分「complete inability」與「partial intolerance」。
  **`CONFIDENCE: MODERATE`**（來自二手摘要，原文付費牆未逐字核對）。
- **EAS 2015 Consensus Panel**（Stroes ES et al., *Eur Heart J* 2015;36:1012-1022）：以 CK
  倍數區分 myalgia（CK 正常或輕度升高 <4×ULN）vs myositis（CK 通常 >10×ULN），且該 panel
  刻意避免對「肌肉相關症狀」使用「statin intolerance」一詞，認為不夠精確。
  **`CONFIDENCE: MODERATE`**（同上，二手摘要）。

**淨比較（回應 CLAUDE.md §5 item 2 的核心問題）**：STS 依其自身摘要被定位為比 NLA
2022/EAS 2015 更寬鬆、更務實的概念 — 涵蓋「real or perceived」副作用與非正式 rechallenge/CK
門檻即可成立的不良反應驅動之不足量使用，這些情況未必符合 NLA/EAS 的正式 rechallenge 或 CK 門檻
標準。此為 GUIDELINE/CONSENSUS 層級的概念界定比較，**非**療效或結果證據 — 與 CLAUDE.md §7
已預先標註的「Taiwan STS 重新定位 ezetimibe 為第一線 add-on 屬 GUIDELINE/CONSENSUS，非 CV-outcome
DIRECT EVIDENCE」完全一致，撰寫時應維持此區隔。

---

## 5. Legacy citation 逐項驗證結果（LEGACY_VERIFICATION，`02_SOURCE-INVENTORY.md` #3–16, #23, #26）

全數 **16/16 VERIFIED_MATCH**，零 mismatch、零 not-found。逐字數字/DOI/PMID 完整列表見
`10_DATA/safety-pharmacology/extraction-table.csv`（rows tag=LEGACY_VERIFICATION）。重點：

- #1 Davies LE 2020（PMID 31926797）：polypharmacy systematic review of reviews（26 reviews, 230
  studies），對 hospitalization、inappropriate prescribing 證據最一致；ADE/disability 證據
  「conflicting」。
- #2 Borodo SB 2022：奈及利亞 polypharmacy 盛行率「up to 23.8%」。
- #3 Goldberg RM 1996（PMID 8765105）：n=205 急診病人，226 起潛在 ADI 見於 89 人（47%）；ADI 風險
  由 2 種藥物時 13% 升至 ≥7 種藥物時 82%。
- #4 Rai GS/Rozario CJ 2023：全文付費牆（Elsevier），依 CLAUDE.md §11 未進一步取得，僅確認書目
  資訊正確（vol 24, issue 4, pages 217-220，印刷引用省略頁碼非錯誤）。
- #5 Huang W 2025（PMID 40880653）：泛用型 DDI 綜述（AI-prediction、易感族群、法規），非
  statin 專一。
- #6 Kellick KA 2014（PMID 24793440，NLA Safety Task Force）：提出新的 statin-DDI 風險分級架構。
- #7 Fravel MA/Ernst M 2021（PMID 33666764）：diltiazem、verapamil 為降血壓藥中最強效之 CYP3A4
  抑制劑，「majority of significant drug interactions involving antihypertensives are
  attributable to these two agents」。
- #8 May M/Schindler C 2016（PMID 27092232）：降血糖藥物交互作用風險分層 —
  sulfonylurea/TZD/glinide 最高，metformin/DPP-4i（除 saxagliptin）低，SGLT2i/incretin
  極低。
- #9 Zanchi A 2012（PMID 22987488）：metformin 可用至 GFR 45 mL/min（無其他共病時）；GLP-1
  受體促效劑於中重度 CKD 禁忌。
- #10 Sica DA 2004（PMID 15470296）：腎功能不全藥物蓄積風險約於 GFR≈30 mL/min 顯現；
  ACEI/ARB（常合併利尿劑）為 CKD 病人降壓/降蛋白尿首選。
- #11 Ehelepola NDB 2017（PMID 28487744）：atorvastatin+diltiazem 併用致橫紋肌溶解案例報告，
  後續診斷出甲狀腺低能症（複合風險因子），levothyroxine 治療後恢復。
- #12 Engell AE 2021（PMID 32533893）：statin-warfarin 交互作用丹麥世代研究。simvastatin (n=1363)
  INR 平均變化 0.32 (95% CI 0.25–0.38)；atorvastatin (n=165) 0.27 (95% CI 0.12–0.42)；
  rosuvastatin (n=23) 0.30 (95% CI −0.09–0.69，此 CI 跨零，樣本數小)。作者結論：INR 上升幅度輕微，
  對多數病人「likely of limited clinical relevance」。
- #13 Harężlak T 2022（PMID 34845649）：「Triple Whammy」（ACEI/ARB+利尿劑+NSAID）致 AKI 之機轉/
  管理綜述，摘要無具體效應量數字。
- #14 Casiglia E/Tikhonoff V 2017（PMID 28559390）：**性質標記** — 此為對另一篇文章（Hypertension.
  2017;70(1):103-110）的 editorial comment/letter，非原始數據研究，本身無獨立數字結果，
  引用時不應當作原始研究處理。
- #15 Chien SC 2019（PMID 30584005）：見上方 §4.2，主題應更正為 2019 台灣 statin intolerance
  共識，非「statin discontinuation outcomes」。
- #16 Sydhom P 2024（PMID 39567875, PMC11577940，open access）：完整逐字數字見 §1.2 與
  `extraction-table.csv`；RCT-pooled 之 LDL/muscle-AE/liver-enzyme 數字為 DIRECT EVIDENCE
  （對「statin+ezetimibe combo vs high-intensity monotherapy」此一般化命題而言），
  observational-pooled 之硬指標/NODM 數字為 OBSERVATIONAL EVIDENCE；因非 pitavastatin 專一
  （納入 rosuvastatin 等其他 statin），對 pitavastatin/ezetimibe 專一聲明而言屬 **INDIRECT
  EVIDENCE**（與 CLAUDE.md §7 對 RACING 的既定處理原則相同 — 需在 40_SYNTHESIS 中比照辦理）。

## 5b. T-013 驗證（Wave 2）：Corsini A 2011 — VERIFIED_MATCH

**Corsini A, Ceska R.** "Drug–drug interactions with statins: will pitavastatin overcome the
statins' Achilles' heel?" *Curr Med Res Opin.* 2011;27(8):1551-1562. DOI 10.1185/03007995.
2011.589433. 經 Crossref 確認作者/期刊/年份/卷期頁碼與 `Tonvasca_2026.md` line 2792 引用完全相符
（該處引用格式省略作者，經核對確為此篇）。**Evidence Hierarchy: EXPERT INTERPRETATION**
（narrative review，非原始數據）。全文本身本輪未取得（付費牆，未嘗試 `download_paper` 因該工具
已被禁用），僅完成書目層級驗證，`CONFIDENCE: HIGH`（書目資訊）。

## 5c. T-012 全文取得（Wave 2）：Katzmann JL et al. 2022 — 開放取用，已合法下載並解析

經 Europe PMC 查證，`02_SOURCE-INVENTORY.md`/CLAUDE.md 中原引用的 Katzmann JL et al. 2022
（DOI 10.1007/s00392-020-01740-8，*Clin Res Cardiol* 111(3):243-252）實際 PMID 為 **32949286**、
PMCID **PMC8873069**，`is_open_access: true`，**CC BY 4.0** 授權。已透過 PMC 開放連結合法下載全文
PDF（21 頁）並以 LlamaParse 成功解析為 Markdown。完整 provenance（URL、下載時間、SHA-256、授權）
見 `30_METHODS/safety-pharmacology/fulltext-manifest.md`。**此篇屬 trials-efficacy 領域
（T-012，已由 Director 轉交），本角色僅完成合法取得與解析，內容延伸分析留給該角色**；順帶確認
原文本身指出其資料集**沒有 medication adherence 數據**（作者自陳為研究限制），故該篇不能作為
adherence 的直接定量證據來源，僅為 FDC 相對 SPC 之 LDL-C 療效證據。

## 6. Tonvasca_2026.md 內部一致性問題（回報 Director，非本角色可修正）

見 `search-log.md` §A 兩項 flag（citation-number 錯位、Chou MT 兩種引用格式並存）— 已於
`90_CROSS-SESSION-LOG/safety-pharmacology-log.md` 完整記錄，交 Director/trials-efficacy 後續
處理。
