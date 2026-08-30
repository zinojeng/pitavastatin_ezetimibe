# ddi-matrix — pitavastatin drug-drug interaction 矩陣

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Owner: safety-pharmacology-intelligence · Activity: NEW_SOURCE_DISCOVERY

語言校準（CLAUDE.md §5 item 4）：本表僅支持「low CYP3A4-dependent interaction liability」的框架，
**不支持**「no DDI」的陳述——表中多筆交互作用機轉為 OATP1B1 transporter-mediated，而非 CYP3A4。

> **Wave 2 更新（2026-08-31）**：以下 DDI 數字已由本角色本人直接重新查證 DailyMed 官方來源
> （非透過 subagent 二手轉述），回應 Director 的 Wave 2 task #3「直接對照官方來源驗證，非二次
> 轉述」。Label revision date（本次查得）：**2026-03-31**。cyclosporine/erythromycin/rifampin/
> gemfibrozil 數字位於 Section 7（Drug Interactions），fenofibrate 數字實際位於 **Section 12.3
> （Pharmacokinetics）Table 3**（"Pitavastatin 4 mg QD + fenofibrate 160 mg QD for 7 days" →
> AUC ↑18%, Cmax ↑11%），並非 Section 7 本身 — 修正先前版本未標明確切 section 位置之疏漏。
> Clarithromycin 經本次直接查證**確認未見於 label 全文任何段落**（非僅本輪查詢遺漏）——
> 升級為 CONFIRMED_ABSENT_FROM_LABEL，但這**不等於**「已證實無交互作用」，僅代表 FDA label
> 未特別著墨，因其藥理性質與 erythromycin（同為 macrolide）相近，仍建議臨床上比照 erythromycin
> 之審慎態度處理（此為本角色之 EXPERT INTERPRETATION，非 label 本身聲明）。另新增查得：
> fibrates 類別整體之肌肉毒性警語（非 gemfibrozil 專屬之定量數字）、niacin（≥1g/day 降脂劑量）
> 及 colchicine 之風險/效益權衡提示。

## 代謝/清除機轉總覽

| 機轉 | 描述 | 來源 | Evidence Hierarchy |
|---|---|---|---|
| CYP450 代謝 | "only minimal metabolism by the cytochrome P450 system"；marginal CYP2C9，更少量 CYP2C8；label 未使用 CYP3A4 一詞（即：無 CYP3A4 代謝路徑被 label 提及） | LIVALO US FDA label (DailyMed) | DIRECT EVIDENCE (regulatory label) |
| OATP1B1 transporter | 據稱佔肝臟清除約 90%（多篇綜述引用，原始定量研究尚未鎖定） | Pharmacology-profile 綜述（未逐一驗證來源） | MECHANISTIC SUPPORT, `CONFIDENCE: MODERATE` |
| BCRP transporter | Pitavastatin 為 BCRP 受質（與 rosuvastatin 共同） | 綜述片段，無具體 fold-change 數字 | MECHANISTIC SUPPORT, `CONFIDENCE: LOW`（缺具體交互作用數字，OPEN GAP，惟見下方 Wave 2 補充兩篇可信來源） |
| CYP3A4 直接驗證 | Itraconazole（強效 CYP3A4 抑制劑）研究標題顯示 "Pitavastatin Concentrations Are Not Increased by CYP3A4 Inhibitor Itraconazole in Healthy Subjects"（PMID 27121674）— 僅取得標題，摘要數字待下一輪核對 | PubMed（標題層級） | DIRECT EVIDENCE（機轉驗證研究，惟本輪未完整核對）, `CONFIDENCE: MODERATE` — 待補強為 HIGH |

## 具體藥物交互作用（逐字 fold-change，來源：LIVALO US FDA label, DailyMed setid 44dcbf97-99ec-427c-ba50-207e0069d6d2, Section 7）

| 併用藥物 | 機轉（label 未必逐一說明，依藥理學推論標註於備註） | AUC 變化 | Cmax 變化 | Label 建議 | Evidence Hierarchy |
|---|---|---|---|---|---|
| Cyclosporine | OATP1B1 抑制（推論） | 4.6-fold ↑ | 6.6-fold ↑ | **CONTRAINDICATED** | DIRECT EVIDENCE (label) |
| Erythromycin（macrolide） | OATP1B1 抑制（推論） | 2.8-fold ↑ | 3.6-fold ↑ | Pitavastatin 劑量上限 **1 mg/day**（非禁忌，劑量限制） | DIRECT EVIDENCE (label) |
| Rifampin | 單次併服交互作用（label 未涵蓋長期誘導型給藥的相反效應 — 見下方備註） | ↑29% | 2.0-fold ↑ | Pitavastatin 劑量上限 **2 mg/day** | DIRECT EVIDENCE (label)，惟慢性給藥情境資料缺 |
| Gemfibrozil | OATP1B1 抑制（推論，機轉與其他 statin 之 gemfibrozil 交互作用一致） | ↑45% | ↑31% | **Avoid concomitant use** | DIRECT EVIDENCE (label) |
| Fenofibrate | 較弱之 OATP1B1 抑制（推論） | ↑18% | ↑11% | 無特別劑量限制；**數字實際位於 Section 12.3 Table 3（藥動學交互作用研究），非 Section 7 DDI 表本身**（pitavastatin 4mg QD + fenofibrate 160mg QD x7 天） | DIRECT EVIDENCE (label) |
| Clarithromycin（macrolide） | 推論與 erythromycin 類似（同為 macrolide） | **CONFIRMED_ABSENT_FROM_LABEL**（2026-08-31 直接查證 label 全文，非僅本輪查詢遺漏） | 同上 | Label 未提及；不等於「無交互作用」，屬 label 未著墨而非陰性結果 | MECHANISTIC INFERENCE（本角色推論），非 label DIRECT EVIDENCE |
| Fibrates（類別整體，非 gemfibrozil 專屬） | 未特別說明機轉 | n/a（非定量數字，為肌肉毒性警語） | n/a | "Fibrates may cause myopathy when given alone. The risk of myopathy and rhabdomyolysis is increased with concomitant use of fibrates with statins, including LIVALO."（Section 7） | DIRECT EVIDENCE (label) |
| Niacin（降脂劑量 ≥1 g/day） | 未特別說明機轉 | n/a | n/a | "Consider if the benefit... outweighs the increased risk"（Section 7，風險效益權衡用語，非禁忌） | DIRECT EVIDENCE (label) |
| Colchicine | 未特別說明機轉 | n/a | n/a | "Consider the risk/benefit"（Section 7） | DIRECT EVIDENCE (label) |

**Rifampin 備註（重要，不得省略）**：上表 rifampin 數字反映的是「單次共同給藥」交互作用；
rifampin 作為強效 CYP450/transporter 誘導劑，在**長期慢性給藥**情境下對多數藥物常有相反（誘導、
降低血中濃度）效果，此一差異未見於本輪擷取之 label 段落，屬已知的文獻缺口，**若 manuscript 要
呈現 rifampin 交互作用，須註明本表數字僅代表急性單次併服情境**，不可推論至慢性合併治療。

## Wave 2 補充：OATP1B1/BCRP 機轉之較可信來源（取代先前「綜述片段」等級引用）

- **Schmith VD et al.** "The Effect of Ecopipam on the Pharmacokinetics of Concomitant
  Medications." 2026. PMID 41635062, PMC12868915（open access）。以 pitavastatin 作為 **OATP1B1
  probe substrate**（而非 BCRP probe——BCRP probe 用的是 rosuvastatin/atorvastatin），支持
  pitavastatin 臨床機轉以 OATP1B1 為主之定位；ecopipam 本身對 pitavastatin exposure「無顯著改變」
  （與此專案 DDI 焦點藥物 cyclosporine/erythromycin/rifampin/gemfibrozil 無直接關係，僅作機轉
  佐證）。**Evidence Hierarchy: MECHANISTIC SUPPORT**, `CONFIDENCE: MODERATE`（已讀摘要，非全文）。
- **Stäuble CK et al.** "Prevalence of substances with OATP1B1 inhibitory properties in individual
  case safety reports of suspected statin-associated myopathy." 2026. PMID 41731198,
  PMC12929307（open access）。瑞士藥物安全通報資料庫分析：54% 疑似 SAMS 通報案例併用至少一種
  OATP1B1 抑制劑物質。**非 pitavastatin 專一**（涵蓋所有 statin 類別），但為 OATP1B1 機轉之臨床
  相關性提供 real-world pharmacovigilance 層級佐證。**Evidence Hierarchy: OBSERVATIONAL EVIDENCE**
  （pharmacovigilance database analysis），`CONFIDENCE: MODERATE`。
- 仍未找到 pitavastatin 與具體 BCRP inhibitor 之定量 fold-change 交互作用數字 — **OPEN GAP 部分
  收斂但未完全解決**，維持於 `unresolved-questions.md`。

## Wave 2 重大新發現：Pitavastatin CKD 劑量調整（原列為 BLOCKED_FOR_SOURCE 之缺口，本輪解決）

**Tramontano D et al.** "Renal Safety Assessment of Lipid-Lowering Drugs: Between Old Certainties
and New Questions." *Drugs.* 2025. PMID 40106181, PMC12098426（open access, CC 授權待確認，已合法
下載並以 LlamaParse 解析全文，見 `fulltext-manifest.md`）。其 Table 1「Statin metabolism and
recommended doses in adults with CKD」逐字列出（引用來源 [17,18] = Bhatti H, Tadi P. Pitavastatin.
StatPearls, 2023；Bellosta S et al. Circulation. 2004;109(23 Suppl 1):III50-7）：

| Statin | 代謝機轉 | 腎臟排除比例 | 輕度 CKD (eGFR G1–G2) 劑量調整 | eGFR G3a–G5 劑量調整 (mg，非 mL/min，原表欄位標題可能誤植單位) |
|---|---|---|---|---|
| Atorvastatin | 主要肝臟 (CYP3A4) | <2% | 一般族群劑量 | 20 |
| Rosuvastatin | 肝臟(CYP2C9,2C19[minor])+腎臟 | 10% | 一般族群劑量 | 10 |
| Simvastatin | 主要肝臟 (CYP3A4) | 13% | 一般族群劑量 | 40 |
| Pravastatin | 主要腎臟 | 20% | 一般族群劑量 | 40 |
| **Pitavastatin** | **肝臟(CYP2C9/2C8[minor])+腎臟** | **15%** | 一般族群劑量 | **2** |

**Pitavastatin 在此表中於中重度 CKD (G3a–G5) 之建議上限（2mg）是所有列出 statin 中最低者。**

**已直接查證 FDA LIVALO label 官方原文，確認並補強（DIRECT EVIDENCE, regulatory label，優於
review-table 之 INDIRECT EVIDENCE 層級）**：
> "The recommended starting dosage for patients with moderate and severe renal impairment
> (estimated glomerular filtration rate 30–59 mL/minute/1.73 m² and 15–29 mL/minute/1.73 m²,
> respectively) and patients with end-stage renal disease receiving hemodialysis is LIVALO 1 mg
> once daily. The maximum recommended dose for these patients is LIVALO 2 mg once daily."
> "There are no dosage adjustment recommendations for patients with mild renal impairment."
> "Renal impairment is a risk factor for myopathy and rhabdomyolysis. Monitor all patients with
> renal impairment for development of myopathy."

**結論**：pitavastatin 單方（非 FDC）於中重度 CKD（eGFR 15–59）及洗腎病人之劑量上限為明確的
**1mg 起始、2mg 上限**，label 層級 DIRECT EVIDENCE，此為原先 Wave 1 標記
BLOCKED_FOR_SOURCE 的 CKD 缺口的**一部分**解決 —— **仍未解決**的部分是：pitavastatin/ezetimibe
FDC 併用於 CKD 病人之specific劑量調整建議（label 本身之 DDI/劑量章節未見專門處理 FDC 情境，
且 K-924、Chou MT 2022 兩篇劑量比較試驗皆未報告 CKD 次族群安全性，見 §3 與
`unresolved-questions.md`）。

## 臨床應用情境 — 老年 + HTN + DM + CAD + CCB + 抗血小板/抗凝血病例（部分證據，敘事整合待 Wave 2/Synthesis）

| 情境元素 | 相關證據 | Evidence Hierarchy |
|---|---|---|
| CCB（尤其 diltiazem/verapamil）為 statin-CYP3A4 交互作用主因 | Fravel MA/Ernst M 2021（PMID 33666764，`02_SOURCE-INVENTORY.md` #9） | DIRECT EVIDENCE（綜述層級） |
| Statin+CCB 併用致橫紋肌溶解案例 | Ehelepola NDB 2017（PMID 28487744，#11） | OBSERVATIONAL EVIDENCE（case report，單一案例，不可外推盛行率） |
| Statin+warfarin INR 影響 | Engell AE 2021（PMID 32533893，#12）— simvastatin/atorvastatin/rosuvastatin 皆有小幅 INR 上升，作者認為多數病人臨床意義有限 | OBSERVATIONAL EVIDENCE（丹麥世代研究） |
| DM 用藥交互作用風險分層 | Zanchi A 2012（#9）、May M/Schindler C 2016（#8） | GUIDELINE/CONSENSUS + MECHANISTIC SUPPORT |
| ACEI/ARB+利尿劑+NSAID 致 AKI（Triple Whammy） | Harężlak T 2022（#13） | MECHANISTIC SUPPORT |
| CKD 病人藥物蓄積風險界值 | Sica DA 2004（#10，GFR≈30 mL/min 為蓄積風險轉折點參考） | EXPERT INTERPRETATION（綜述型敘述，非正式臨界值指引） |

**重要**：本表中 pitavastatin 自身與 CCB/warfarin/降血糖藥物的**直接**交互作用數字（fold-change
等）本輪**未在 pitavastatin 專屬文獻中找到** — 上表所列多為「statin 類別一般性」或其他 statin
（atorvastatin 等）的交互作用證據，用於建構臨床情境的機轉背景，**不應誤植為 pitavastatin
專屬之定量交互作用數據**。如 manuscript 需要 pitavastatin 與 CCB/warfarin 的專屬 fold-change
數字，應標記為 BLOCKED_FOR_SOURCE 或於下一輪指名搜尋。
