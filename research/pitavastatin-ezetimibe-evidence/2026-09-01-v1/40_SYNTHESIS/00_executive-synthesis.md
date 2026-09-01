# 00 執行綜合摘要（整合 zh-TW 實證簡報）— Pitavastatin/Ezetimibe FDC

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-09-01-v1`
Wave 3 Synthesis · Director 整合，來源：guideline-risk / trials-efficacy / safety-pharmacology
三角色 Wave 1（含大部分 Wave 2 attack/defense）之全部委託輸出，附加至 `2026-08-31-v1` 已通過
Wave 4 獨立稽核（Final Gate `PASS_WITH_MINOR_ISSUES`）之既有證據基礎，兩者互為 additive，不覆寫。

本文件同時作為 PI 要求之**整合 zh-TW 實證簡報**——藥物/技術名詞、統計量、試驗代號保留英文。

---

## 0. 如何閱讀本文件

每項論斷後方標註兩套標籤：
- **Evidence Hierarchy**（`CLAUDE.md` §7）：`DIRECT EVIDENCE` | `INDIRECT EVIDENCE` |
  `GUIDELINE/CONSENSUS` | `OBSERVATIONAL EVIDENCE` | `MECHANISTIC SUPPORT` |
  `INSTITUTIONAL PRACTICE` | `EXPERT INTERPRETATION` | `INSUFFICIENT EVIDENCE`
- **Claim-Safe Taxonomy**（本 run 新增，`01_RESEARCH-CHARTER.md` focus area 6）：`SUPERIORITY` |
  `NONINFERIORITY` | `LDL-C SURROGATE EFFICACY` | `OBSERVATIONAL SIGNAL` |
  `SUBGROUP/HYPOTHESIS-GENERATING` | `GUIDELINE/CONSENSUS` | `EXPERT INFERENCE`

**兩個必須貫穿全文的紀律，任何簡報/manuscript 引用本文件內容時不得移除：**

1. **RACING（rosuvastatin）、REPRIEVE/REAL-CAD（pitavastatin 單方，無 ezetimibe）、T-101（statin-
   agnostic 之 2026 ACC/AHA guideline）三者皆非 pitavastatin/ezetimibe FDC 專屬證據** —— 引用時
   必須明確標示其實際研究對象，不可用以直接支持 FDC 專屬的 CV outcome 優越性論斷。
2. **Taiwan STS 2026 共識「ezetimibe 作為首選加藥」之具體內容主張，本專案自 2026-08-31-v1 起持續
   `BLOCKED_FOR_SOURCE`，本 run 再次確認無法解除**（見第 6 節）。這是本專案「treat the target, not
   the dose」整體論述框架最大的一個未獨立驗證但具支撐性的主張——guideline-risk 本人的評估（見
   Decision 2026-09-01-11）——任何呈現本專案論述的場合都必須明確揭露此點，不可讓其與已驗證的
   T-101 內容處於同一信心層級。

---

## 1. 三層 Hard-Outcome 證據階層框架（延續 `pitavastatin topic.md` §6，本 run 更新）

| 層級 | 內容 | 狀態（本 run 更新後） |
|---|---|---|
| **Level 1 — LDL-lowering efficacy** | Pitavastatin+ezetimibe FDC 的 LDL-C 降幅證據 | **強，product-level，已跨國複現**（Taiwan/Australia/NZ 之 1PC111 [Chou 2022]；Japan 之 K-924 [Tsujita 2023, DOI 10.5551/jat.64006]；Korea/Taiwan 已知既有資料）。K-924 之 matched-dose LS-mean 差異本 run **已由 trials-efficacy 獨立對照原始全文核實**：combo 2/10 vs pitava 2mg = −11.9%（95% CI −15.2 to −8.7）；combo 4/10 vs pitava 4mg = −12.7%（95% CI −15.9 to −9.4）——取代先前未經證實的跨組並列（−51.4% vs −45.2%，已確認**從未是** prespecified 統計比較，已撤回）。`DIRECT EVIDENCE` / `LDL-C SURROGATE EFFICACY`。 |
| **Level 2 — Combination-strategy CV outcome evidence** | 「statin+ezetimibe 併用策略」之 hard-outcome 證據 | **強，但非 pitavastatin 專屬**——RACING（rosuvastatin 10mg+eze10mg vs 高強度單方，3-yr MACE 9.1% vs 9.9%，non-inferior）。`INDIRECT EVIDENCE` / `NONINFERIORITY`。**本 run 新增**：2026 ACC/AHA guideline（T-101，已 VERIFIED）本身之 ezetimibe 加藥建議（VHR: COR 1 LOE A；non-VHR: COR 2a LOE B-R）為 `GUIDELINE/CONSENSUS`，同樣是 statin-agnostic，不可轉引為 pitavastatin 專屬證據（見第 4 節）。 |
| **Level 3 — Pitavastatin/ezetimibe 專屬 hard-outcome superiority** | Pitavastatin+ezetimibe FDC 本身之 CV outcome 優越性 | **本 run 再次確認：尚未直接/充分證實。** HIJ-PROPER 整體 primary endpoint HR 0.89（95% CI 0.76–1.04, P=0.152，未達統計優越性）**仍是**唯一直接檢驗此問題的 RCT，本 run 搜尋確認無 2026-08-31 後發表之新試驗關閉此缺口。**新發現**：兩個 HIJ-PROPER 次族群分析（TE-016 sitosterol/absorber-phenotype 完整發表；TE-017 baseline-LDL-C 分層，interaction P=0.012）——皆為 `hypothesis-generating`／`SUBGROUP/HYPOTHESIS-GENERATING`，**不可**升級為已證實之 superiority 論斷，且兩者為概念上獨立的次族群切分方式，不可合併陳述（見第 5 節）。 |

---

## 2. 2026 ACC/AHA Guideline（T-101）—— 本 run 最重要的方法論成就：獨立驗證一份候選主要來源

### 2.1 驗證方法（可重複使用之範式）

T-101（`inbox/2026-acc-aha-drive/official/2026_ACC_AHA_Multisociety_Dyslipidemia_Guideline_
Circulation.{pdf,md}`——"2026 ACC/AHA/AACVPR/ABC/ACPM/ADA/AGS/APhA/ASPC/NLA/PCNA Guideline on the
Management of Dyslipidemia," *Circulation*. 2026;153:e1154–e1276, DOI
`10.1161/CIR.0000000000001423`）於 Wave 1 由 guideline-risk-intelligence 以三項獨立、外部可查證的
方式確認為真：(1) `doi.org` 302 重導向至真實 `ahajournals.org` 文章頁面；(2) Crossref 公開 API
metadata（標題/期刊/卷數/出版者/作者名單）與 PDF 內部自我引用完全相符，含獨立交叉核對之出版日期
（2026-04-28）與每頁頁尾一致；(3) 全文 123 頁系統性（非抽樣）內部一致性檢查——單位換算、已知文獻
數字、逐頁浮水印、COR/LOE 格式皆通過。**誠實保留之限制**：`ahajournals.org` 本身對本專案工具為
Cloudflare 阻擋，故此為「獨立佐證式驗證」而非逐位元組出版社重新下載比對。**Evidence Hierarchy:
GUIDELINE/CONSENSUS**（已驗證）。

**額外發現（Decision 2026-09-01-05）**：T-101 之 DOI（`10.1161`, Circulation）與前一 run 長期
`BLOCKED_FOR_SOURCE` 之 citation #28 DOI（`10.1016/jacc.2025.11.016`, JACC）經 Crossref 作者名單
核對，確認為**同一份 guideline 之真實雙期刊同步發表**（與 2018 前版相同模式：Circulation
2019;139:e1082–e1143 / JACC 2019;73:3168–3209，同見於本文件自身引用）——非引用錯誤。前一 run 之
T-028 紀錄本身不修改（已結案 run），但本 run 視其內容已透過 T-101 取得。

### 2.2 兩輪自我修正（透明記錄，非隱藏）—— 本專案 Numeric Integrity Rule 的實際示範

guideline-risk 之 Wave 1 初次萃取因 `pdftotext -layout` 之欄位錯位假影（column-merge artifact）
產生兩處錯誤，皆於後續交叉核對中主動發現並透明修正：

1. **COR 分級錯誤**：VHR（very-high-risk）ezetimibe/PCSK9 加藥建議，初次萃取誤植為 COR 2a，經
   intake bundle 交叉比對（`00_quick_reference_card.md` 顯示正確為 COR 1）與更寬萃取視窗重新核對，
   確認正確為 **COR 1, LOE A**——比原先回報更強的建議等級（Decision 2026-09-01-07）。
2. **Severe hypercholesterolemia non-HDL-C 目標值——來源自身之印刷不一致**（此為本 run 最重要、也
   歷經兩次修正才定案的發現）：Director 之 QA 發現「non-HDL-C <100 mg/dL (2.4 mmol/L)」與同一份
   guideline 其他位置之「<100 mg/dL (2.6 mmol/L)」不一致（100 mg/dL 之標準換算為 2.6 mmol/L，非
   2.4）。guideline-risk 以 `pdftotext -raw` 對照權威條列段落後，初步（錯誤地）認為 `2.4 mmol/L`
   完全不存在、是本專案自身萃取工具之欄位錯位假影——**此結論後經 PI 直接對 PDF 原始檔執行
   `pdftotext -layout`/`-raw` 獨立複查後推翻**：PDF 第 e1159 頁「Table 1. 2018 vs 2026」摘要比較表
   （section 4.2.4.3, Revised 欄）確實完整、連貫地印著「...achieve a goal of LDL-C <70 mg/dL
   (1.8 mmol/L) and non–HDL-C <100 mg/dL **(2.4 mmol/L)** is recommended...」；第 e1199 頁權威條列
   段落「Recommendations for Severe Hypercholesterolemia」編號建議 #4（COR 1, LOE B-R）則印著
   「...(2.6 mmol/L) is recommended...」——**兩處皆為完整、無斷裂、無拼接痕跡之正常句子，非欄位
   錯位假影**。Director 於採信 PI 回報前，先以第三套、與本專案先前使用之 `pdftotext` 及 intake
   `.md` 轉檔管線皆不同的獨立工具（PyMuPDF/`fitz`）直接重新解析原始 PDF，取得完全相同之結論並附
   精確頁碼與完整上下文，方才採納此更正（見 Decision 2026-09-01-14 完整記錄）。

   **結論**：這是 guideline 出版品**自身內部**的換算不一致（most plausibly 摘要比較表本身之 typo——
   100 mg/dL 之標準換算為 2.6 mmol/L，與權威條列段落及文件其他所有「<100 mg/dL」出現處一致），
   **並非**任何萃取工具之假影。LDL-C 目標值（<100 mg/dL）本身明確、不受影響、自始至終未變動；
   兩個 mmol/L 換算數字之間，**以 2.6 mmol/L（權威條列段落之數值，與文件其餘處一致）為準**，
   `2.4 mmol/L`（摘要比較表之數值）保留為明確標註之來源異常值，不予捨棄，亦不作為可替代之有效值
   使用。

| Severe Hypercholesterolemia（LDL-C≥190 mg/dL）三層結構（已修正，PDF 原始檔三套獨立工具交叉驗證） | LDL-C 目標 | non-HDL-C 目標 | COR/LOE |
|---|---|---|---|
| Tier 1：無 ASCVD/HeFH/subclinical atherosclerosis/其他風險因子 | <100 mg/dL (2.6 mmol/L) | <130 mg/dL (3.4 mmol/L) | 1, B-NR |
| Tier 2：合併 HeFH/subclinical atherosclerosis/其他風險因子，無 clinical ASCVD（**注**：guideline
自身之「Table 1. 2018 vs 2026」摘要比較表〔頁 e1159〕將此列 non-HDL-C 目標印為 **2.4 mmol/L**，與
本表所採用、來自權威條列段落〔頁 e1199〕之 **2.6 mmol/L** 不一致——來源內部換算不一致，LDL-C 目標
<70 mg/dL 本身兩處相符，不受影響） | <70 mg/dL (1.8 mmol/L) | <100 mg/dL (**2.6 mmol/L**；來源摘要表另印 2.4 mmol/L，見上注) | 1, B-R |
| Tier 3：合併 clinical ASCVD | <55 mg/dL (1.4 mmol/L) | <85 mg/dL (2.2 mmol/L) | 1, B-R |

**方法論教訓，已採納為本 run 後續原則（Decision 2026-09-01-14 完整記錄）**：guideline 之權威
「Recommendations for [topic]」條列段落優先於「Table 1. 2018 vs 2026」摘要比較表作為**目標數值的
主要依據**——但**當某一角色以「該數值不存在」作結論來解決兩處不一致時，這個「不存在」的結論本身
需要與原始的「不一致」發現同等嚴謹的獨立複查**（理想上以與先前不同的獨立工具，直接對照原始 PDF，
而非僅對照同樣可能有假影的 `.md` 轉檔或單一工具之單次萃取結果）——「數值不存在」是比「兩處印製不同」
更強、也更容易被證偽的主張，本 run 的教訓是：這類「不存在」結論在 Gate 3 與 Wave 4 稽核中都未被
以獨立工具重新對照原始 PDF 驗證，僅信賴同一調查角色的 `-raw` 模式結論與 `.md` 衍生檔案之 grep，
直到 Final Gate 之後才由 PI 親自對原始 PDF 執行獨立複查而發現。

---

## 3. Goal-Directed Absolute LDL-C/non-HDL-C 目標（Focus Area 1 核心發現）

T-101 明確以**絕對目標值**（非僅相對降幅百分比）建構整份 guideline，依風險分層區分**四種**不同
目標（非單一數字）：

| 風險分層 | LDL-C 目標 | non-HDL-C 目標 | COR |
|---|---|---|---|
| Diabetes，無 ASCVD，標準風險 | <100 mg/dL (2.6 mmol/L) | <130 mg/dL (3.4 mmol/L) | 1 |
| Diabetes，多重 ASCVD 風險因子 | <70 mg/dL (1.8 mmol/L) | <100 mg/dL (2.6 mmol/L) | 2a |
| Clinical ASCVD，非極高風險 | <70 mg/dL (1.8 mmol/L) | <100 mg/dL | 1 |
| **Clinical ASCVD，極高風險** | **<55 mg/dL (1.4 mmol/L)** | **<85 mg/dL (2.2 mmol/L)** | **1, LOE A** |
| CAC≥1000 AU | <55 mg/dL (1.4 mmol/L) | <85 mg/dL (2.2 mmol/L) | 1 |
| Severe hypercholesterolemia | 見第 2.2 節三層表 | 見第 2.2 節三層表 | 1 |

此表**逐字確認**`pitavastatin topic.md`／`CLAUDE.md` §2.2 原先「極高風險二級預防目標 <55 mg/dL」
之論斷——現已有明確 COR/LOE 溯源之逐字引用支持，非改寫轉述。**Evidence Hierarchy: GUIDELINE/
CONSENSUS**。**Claim-Safe Taxonomy: guideline recommendation**（COR/LOE 正式建議，非試驗結果本身）。

**重要否定性發現（不可被忽略或淡化）**：T-101 **未使用**「early combination therapy」或「upfront
combination」作為正式建議用語——其結構為**逐步式**（stepwise）：Class 1 建議先以 statin 單方
（依風險分層為中強度或高強度）治療，僅於「maximally tolerated statin therapy」仍未達目標時，才以
Class 2a（或極高風險族群之 Class 1）建議加用 ezetimibe/PCSK9 mAb/bempedoic acid。這與前一 run 透過
次級文獻（Katzmann & Laufs 2026 二手佐證，本身亦未經本專案直接主要來源驗證）歸因於 2025 ESC/EAS
Focused Update 之「upfront combination」立場形成**真實、可引用的跨大西洋 guideline 立場差異**——
不可將「guidelines 支持 early combination therapy」寫成跨大西洋共識性陳述；此僅是（若 ESC 立場屬實）
歐洲特有之立場，美國現行最大型、已驗證之 guideline **並未**採此立場。

**同時，2026 guideline 確實移除了一項實質障礙**：其 synopsis 明確指出，因 PCSK9 mAb 安全性資料
累積與成本大幅下降，「revised recommendations no longer require that ezetimibe be added to statin
therapy prior to initiating a PCSK9 mAb」——這是移除既有排序限制（sequencing requirement removed），
與「early/upfront combination」是概念上不同的兩件事，本文件刻意分開陳述，不可混為一談。

---

## 4. Ezetimibe 加藥定位——非極高風險三者同等，極高風險僅 ezetimibe/PCSK9 mAb 無偏好（POST-FINAL-GATE
   修正，2026-09-01，Focus Area 1 + 攻防要點）

**修正說明**：本節先前版本誤將 T-101 於極高風險（VHR）與非極高風險兩層級之加藥建議，籠統敘述為
「ezetimibe、PCSK9 mAb、bempedoic acid 三者同等 COR/LOE 地位」——經 PI 直接核對 T-101 權威條列段落
「Recommendations for Secondary ASCVD Prevention」（頁 e1208）後發現此為過度簡化，Director 已
獨立以 PyMuPDF 重新對照原始 PDF 確認 PI 之更正正確。**正確結構因風險分層而異，須分開陳述**：

- **非極高風險（建議 #2、#3）**：ezetimibe、PCSK9 mAb、bempedoic acid **三者確實同等**——皆為
  **COR 2a, LOE B-R**，"it is reasonable to add ezetimibe, a PCSK9 mAb, or bempedoic acid (selection
  depending on degree of LDL-C lowering needed and patient preference)"。此層級「三者無偏好」之
  陳述**成立**。
- **極高風險（建議 #5、#6、#7）——三者並非同等**：
  - 建議 #5（**COR 1, LOE A**）："ezetimibe and/or a PCSK9 mAb **should be added** (selected based
    on the degree of LDL-C lowering needed and patient preference)..."——ezetimibe 與 PCSK9 mAb
    並列於同一條建議、同一 COR/LOE，**兩者之間無偏好**，但用語為「should be added」（較強）。
  - 建議 #6（**COR 2a, LOE B-R**，較弱、獨立成一條）："it is reasonable to add bempedoic acid, with
    or without ezetimibe and/or PCSK9 mAb, to reach an LDL-C goal..."——bempedoic acid 在極高風險
    層級是**獨立、較低 COR 等級**的建議，並非與 ezetimibe/PCSK9 mAb 同列同等。
  - 建議 #7（**COR 2a, LOE B-R**，另有明確使用限制）：inclisiran"...in those **unable to tolerate
    or obtain** evolocumab or alirocumab **or have a strong preference for less frequent dosing**..."
    ——inclisiran 於極高風險層級亦為較低 COR，且明確**限定**於「無法耐受/取得 PCSK9 mAb，或明確偏好
    低頻給藥」之病人，非一般性同等選項。

**誠實、精確的結論**：極高風險層級，guideline **對 ezetimibe 相對 PCSK9 mAb 確實無偏好**（兩者
COR 1, LOE A 同列）——這仍是本專案任何「guideline 建議優先使用 ezetimibe（而非 PCSK9 mAb）」論述
必須揭露的限制，不可迴避。但**guideline 對 ezetimibe/PCSK9 mAb 相對 bempedoic acid/inclisiran
確有形式上的偏好**（COR 1 vs COR 2a）——先前「三者完全同等」之敘述在極高風險層級並不成立，過度
低估了 ezetimibe 於此層級之 guideline 地位。正確敘述應為：「無 ezetimibe 優於 PCSK9 mAb 之偏好，
但 guideline 於極高風險層級形式上偏好 ezetimibe/PCSK9 mAb（COR 1, LOE A）甚於 bempedoic
acid/inclisiran（COR 2a, LOE B-R，inclisiran 另有明確使用限制）」——非極高風險層級則三者確實同等
（COR 2a, LOE B-R）。詳見第 7 節攻防章節之對應修正。

---

## 5. HIJ-PROPER 與 Cholesterol Absorption Phenotype——精準降脂學的開放問題

HIJ-PROPER（Hagiwara 2017, *Eur Heart J*）整體 primary endpoint：32.8% vs 36.9%，HR 0.89（95% CI
0.76–1.04, P=0.152）——**未達統計優越性**，仍是唯一直接檢驗 pitavastatin+ezetimibe vs pitavastatin
單方 hard-outcome 的 RCT。本 run 確認無新試驗關閉此缺口（trials-efficacy 重新檢索，非假設前一 run
判斷仍然成立）。

**本 run 新發現、明確標示信心層級之兩個次族群分析**（不可合併陳述，兩者切分變數不同）：

- **TE-016**（Yamaguchi J et al. *Atherosclerosis* 2018;274:139-145, DOI
  10.1016/j.atherosclerosis.2018.04.036, PMID 29772482）——sitosterol/cholesterol-absorber
  phenotype 訊號（HR 0.71, 95% CI 0.56–0.91）之**完整專屬發表**（前一 run 僅見於母試驗論文之簡短
  提及）。**信心層級：MODERATE**——本 run 僅取得 WebSearch 聚合摘要，未獨立全文核實（ScienceDirect
  回傳 403，如實回報，非虛構內容）。**Evidence Hierarchy: hypothesis-generating /
  INSUFFICIENT EVIDENCE**。**Claim-Safe Taxonomy: `SUBGROUP/HYPOTHESIS-GENERATING`**。
- **TE-017**（*Scientific Reports* 2021, DOI 10.1038/s41598-021-87098-x, PMC8021554，開放取用）——
  statin-naive 子集（N=1429）依 baseline LDL-C 中位數（131 mg/dL）分層：低 LDL-C 組（N=686）HR
  1.13（95% CI 0.87–1.47, P=0.35，無顯著差異）；**高 LDL-C 組（N=743）HR 0.72（95% CI 0.56–0.91,
  P=0.007）**；**interaction P=0.012**（支持 baseline LDL-C 為真正的 effect modifier，非任意切分
  之巧合訊號）。**信心層級**：N/cutoff/endpoint 定義 = HIGH（雙管道交叉核對一致）；HR/CI/p-value
  具體數字 = MODERATE（僅單一 WebFetch 來源，PMC PDF 遭遇反機器人 challenge 未解，與前一 run 相同
  問題未解決）。**Evidence Hierarchy: DIRECT EVIDENCE**（僅限此 pre-specified 次族群本身，**不可**
  引申為「已證實 pitavastatin+ezetimibe 對高 LDL-C ACS 病人有效」之一般性論斷，母試驗整體
  primary endpoint 仍未達顯著）。**Claim-Safe Taxonomy: `SUBGROUP/HYPOTHESIS-GENERATING`**（因
  interaction p=0.012 之支持，方法論份量高於一般 post-hoc 次族群訊號，但**不等同**於已確認的
  superiority 論斷）。

---

## 6. Taiwan STS 2026——本專案最大的未獨立驗證但具支撐性主張（本 run 明確標示，非隱藏）

自 2026-08-31-v1 起，Taiwan STS（Suboptimally Tolerable Statins）2026 共識書目資訊已驗證存在，但
其「repositions ezetimibe as first add-on for high/very-high risk」之**具體內容主張**，本 run 再次
時間限制內確認**仍無法解除 `BLOCKED_FOR_SOURCE`**（`research_hub`/`google-scholar` 檢索無新管道，
同一組 DOI）。**新確認之獨立資訊**：Unpaywall 現已確認該來源為真正 Gold Open Access／CC BY
授權（解決前一 run「OA 標記未經證實」之矛盾——embargo 顯然已解除），但實際 ScienceDirect 頁面對
自動化擷取工具仍為 Cloudflare 機器人偵測阻擋，**與 OA 授權狀態無關**，故全文擷取本身依然
`BLOCKED_FOR_SOURCE`——僅 OA 狀態本身這個子問題已釐清，內容缺口未變。

**guideline-risk 本人之評估（Decision 2026-09-01-11，Director 完全同意並在此明確重申）**：這是
本專案整體「治療目標導向、而非劑量導向」框架論述中，**單一最大的未獨立驗證但具支撐性主張**——比
任何單一試驗層級的證據缺口都更關鍵，因為它是「treat the target, not the dose」整體敘事所仰賴的
組織性概念本身。**T-101（已驗證）之美國 guideline 內容不能、也不應被用來間接證實或掩蓋這個台灣
專屬缺口**——兩者是不同文件，本文件第 3、4 節之 T-101 相關發現雖然強健，但**不構成** Taiwan STS
內容主張的替代驗證。任何簡報/manuscript 引用「STS 重新定位 ezetimibe 為首選加藥」時，**必須**明確
標示此為 `GUIDELINE/CONSENSUS`（書目層級）但內容本身 `BLOCKED_FOR_SOURCE`，不可與 T-101 已驗證內容
並列於同一信心層級呈現。

---

## 7. Attack/Defense 章節——見獨立文件

三角色之攻防貢獻（guideline-risk 5 點、trials-efficacy 4 點、safety-pharmacology 3 大類）已整合為
獨立文件 `01_attack-defense.md`，對應 PI 六大焦點之第 5 項要求（product-specific MACE limitation、
indirect evidence、maximize-statin-first、diabetes/DDI claims、cost/adherence、何時
PCSK9/bempedoic/inclisiran 更適當）。**本節僅列出跨三角色皆需知悉之交叉重點**：

- **Inclisiran 目前沒有已發表之 hard-outcome trial**（僅 VICTORION-2 Prevent、ORION-4 設計/protocol
  論文）——與 bempedoic acid（CLEAR-Outcomes，已完成正向 CV outcome RCT）、PCSK9-targeting therapy
  （FOURIER、ODYSSEY OUTCOMES，皆已完成正向 CV outcome RCT）**不可視為同一等級之「hard-outcome-
  proven 替代方案」**——inclisiran 目前僅有 LDL-C surrogate 證據充分。任何「hard-outcome-proven
  替代方案」框架若涵蓋 inclisiran 而未加註此限制，即構成本專案核心紀律所警示之過度延伸錯誤。
- Pitavastatin/ezetimibe FDC 與高強度 statin 單方（atorvastatin/rosuvastatin 高劑量）之**直接
  頭對頭比較試驗不存在**——RACING 為 rosuvastatin 版本、K-924 為 pitavastatin 內部劑量比較，皆非
  「pitavastatin+eze vs. 高強度單方 statin」之直接對照。此為本專案安全性/耐受性定位論述之最大直接
  證據缺口，須誠實揭露。
- **REAL-CAD**（pitavastatin 4mg vs 1mg, HR 0.81, 95% CI 0.69–0.95, P=0.01）本身即為「先最大化
  statin 劑量」策略之正向 pitavastatin 專屬 hard-outcome 證據——證據完整度**優於** FDC 目前僅達
  次族群層級的 Level 3 證據。「先最大化劑量」並非單純歷史慣性，而是有其自身的直接證據支持，須誠實
  呈現此比較。

---

## 8. 台灣/亞洲族群、CKD、依從性——安全性定位三大支柱（本 run 更新，詳見 `01_attack-defense.md`
   與 safety-pharmacology `positioning-brief.md` 完整版）

**血糖側寫**（延續前一 run 已通過 Wave 4 稽核之完整證據）：「pitavastatin 相對其他常用高效能 statin
可能有較有利的血糖側寫」——**絕不**寫成「does not cause diabetes」。CAPITAIN 高劑量資料仍顯示 FPG
微升（+4%, p<0.05），此為誠實反駁點，不隱藏。

**低 CYP3A4-dependent interaction liability**（延續前一 run）：「low CYP3A4-dependent interaction
liability」——**絕不**寫成「no DDI」。**攻防重要區隔**：低 CYP3A4 依賴**不代表**低 OATP1B1 依賴——
cyclosporine（禁忌）、gemfibrozil（避免併用）之交互作用風險依然存在，此為對手最容易且最合理的
反駁切入點，須主動揭露而非迴避。

**東亞族群 guideline 層級佐證（本 run 新增，safety-pharmacology 已獨立逐字核對 T-101 第 2015–2018
行）**：「Certain populations (especially East Asian ancestry) may be more prone to side effects
due to inherited drug metabolism effects; thus, initial treatment should be with lower doses.」——
此為 statin **類別**一般性陳述，**非** pitavastatin 專屬，**不可**改寫為「guideline 建議東亞病人
優先使用 pitavastatin」。**Evidence Hierarchy: GUIDELINE/CONSENSUS**。

**CKD**：pitavastatin 單方於中重度 CKD/洗腎病人劑量上限（1mg 起始/2mg 上限）為所有已列表 statin 中
最保守——但 **FDC 本身之 CKD 專屬劑量資料，自前一 run 起持續缺乏**，本 run 未發現新資料解決此缺口，
維持 `BLOCKED_FOR_SOURCE`（`04_OPEN-QUESTIONS.md` Q7）。

**Adherence/RWE**：Katzmann 2022（FDC LDL-C 降幅 −28.4% vs SPC −19.4%, p<0.0001）——惟該研究**沒有
依從性直接測量資料**，「FDC 提升依從性」為合理推論鏈而非直接證實，須誠實揭露。**RWE 現狀**（本 run
新確認，Q5 已答）：pitavastatin+ezetimibe FDC 專屬 RWE **僅有 TE-013 一篇**（Lu 2026，Taiwan
post-PCI，N=120，單臂兩中心）——證據基礎仍薄弱，同類但非 pitavastatin 之 FDC（atorvastatin/
ezetimibe）RWE 正在其他藥物累積中，此不對稱應誠實呈現。

---

## 9. 本 run 未解決事項總覽（見 `04_OPEN-QUESTIONS.md` 完整版，Q1–Q10）

| # | 事項 | 狀態 |
|---|---|---|
| Q4 | Intake 自身證據標籤系統與本專案標籤如何整合 | 低優先，維持不採用 |
| Q6 | FDC vs 高強度 statin 單方之直接頭對頭試驗不存在 | 誠實限制，非搜尋失敗 |
| Q7 | FDC 專屬 CKD 劑量資料缺乏 | 延續前一 run，本 run 未解決 |
| Q8-2 | PCSK9/inclisiran DDI 機轉層級主張 | 部分升級（耐受性/適應症面向已 guideline-sourced），DDI 機轉面向仍 EXPERT INFERENCE |
| Q9 | TE-016/TE-017 全文獨立核實 | 待 Wave 2 工具連線恢復 |
| Q10 | Inclisiran 無已發表 hard-outcome trial | 確認缺口，須於攻防章節誠實揭露 |
| — | Taiwan STS content claim | 仍 BLOCKED_FOR_SOURCE，本專案最大未驗證支撐性主張（第 6 節） |
| — | 台灣健保 FDC 給付/自付額資訊 | 本 run 未查證，屬在地化資訊缺口 |

---

## 10. 结論：本 run 對整體專案的貢獻

本 run 的最大方法論貢獻，不是新增更多零散證據，而是：(a) 獨立驗證了一份高價值候選主要來源（T-101），
並建立了可重複的驗證範式（DOI 解析 + Crossref metadata + 內部一致性系統性檢查）；(b) 透過該驗證過程
的交叉核對，發現並透明修正了兩輪本專案自身的萃取錯誤（COR 分級、severe hypercholesterolemia 三層
結構），展示 Numeric Integrity Rule 在實務中如何運作；(c) 由三個角色各自誠實產出攻防章節內容，
特別是明確標示 Taiwan STS 內容缺口為本專案框架最大的未驗證支撐性主張，以及 inclisiran hard-outcome
證據缺口——這些誠實限制的呈現，本身就是本專案科學可信度的核心部分，而非需要淡化或隱藏的弱點。
