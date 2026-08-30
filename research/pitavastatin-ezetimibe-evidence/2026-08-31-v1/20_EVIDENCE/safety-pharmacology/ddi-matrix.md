# ddi-matrix — pitavastatin drug-drug interaction 矩陣

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Owner: safety-pharmacology-intelligence · Activity: NEW_SOURCE_DISCOVERY

語言校準（CLAUDE.md §5 item 4）：本表僅支持「low CYP3A4-dependent interaction liability」的框架，
**不支持**「no DDI」的陳述——表中多筆交互作用機轉為 OATP1B1 transporter-mediated，而非 CYP3A4。

## 代謝/清除機轉總覽

| 機轉 | 描述 | 來源 | Evidence Hierarchy |
|---|---|---|---|
| CYP450 代謝 | "only minimal metabolism by the cytochrome P450 system"；marginal CYP2C9，更少量 CYP2C8；label 未使用 CYP3A4 一詞（即：無 CYP3A4 代謝路徑被 label 提及） | LIVALO US FDA label (DailyMed) | DIRECT EVIDENCE (regulatory label) |
| OATP1B1 transporter | 據稱佔肝臟清除約 90%（多篇綜述引用，原始定量研究尚未鎖定） | Pharmacology-profile 綜述（未逐一驗證來源） | MECHANISTIC SUPPORT, `CONFIDENCE: MODERATE` |
| BCRP transporter | Pitavastatin 為 BCRP 受質（與 rosuvastatin 共同） | 綜述片段，無具體 fold-change 數字 | MECHANISTIC SUPPORT, `CONFIDENCE: LOW`（缺具體交互作用數字，OPEN GAP） |
| CYP3A4 直接驗證 | Itraconazole（強效 CYP3A4 抑制劑）研究標題顯示 "Pitavastatin Concentrations Are Not Increased by CYP3A4 Inhibitor Itraconazole in Healthy Subjects"（PMID 27121674）— 僅取得標題，摘要數字待下一輪核對 | PubMed（標題層級） | DIRECT EVIDENCE（機轉驗證研究，惟本輪未完整核對）, `CONFIDENCE: MODERATE` — 待補強為 HIGH |

## 具體藥物交互作用（逐字 fold-change，來源：LIVALO US FDA label, DailyMed setid 44dcbf97-99ec-427c-ba50-207e0069d6d2, Section 7）

| 併用藥物 | 機轉（label 未必逐一說明，依藥理學推論標註於備註） | AUC 變化 | Cmax 變化 | Label 建議 | Evidence Hierarchy |
|---|---|---|---|---|---|
| Cyclosporine | OATP1B1 抑制（推論） | 4.6-fold ↑ | 6.6-fold ↑ | **CONTRAINDICATED** | DIRECT EVIDENCE (label) |
| Erythromycin（macrolide） | OATP1B1 抑制（推論） | 2.8-fold ↑ | 3.6-fold ↑ | Pitavastatin 劑量上限 **1 mg/day**（非禁忌，劑量限制） | DIRECT EVIDENCE (label) |
| Rifampin | 單次併服交互作用（label 未涵蓋長期誘導型給藥的相反效應 — 見下方備註） | ↑29% | 2.0-fold ↑ | Pitavastatin 劑量上限 **2 mg/day** | DIRECT EVIDENCE (label)，惟慢性給藥情境資料缺 |
| Gemfibrozil | OATP1B1 抑制（推論，機轉與其他 statin 之 gemfibrozil 交互作用一致） | ↑45% | ↑31% | **Avoid concomitant use** | DIRECT EVIDENCE (label) |
| Fenofibrate | 較弱之 OATP1B1 抑制（推論） | ↑18% | ↑11% | 無特別劑量限制 | DIRECT EVIDENCE (label) |
| Clarithromycin（macrolide） | 推論與 erythromycin 類似（同為 macrolide），惟本輪擷取之 label 段落**未包含**其獨立數字 | **NOT_FOUND（本輪未查獲，非「無交互作用」之結論）** | NOT_FOUND | 待補查 | OPEN GAP — 見 `unresolved-questions.md` |

**Rifampin 備註（重要，不得省略）**：上表 rifampin 數字反映的是「單次共同給藥」交互作用；
rifampin 作為強效 CYP450/transporter 誘導劑，在**長期慢性給藥**情境下對多數藥物常有相反（誘導、
降低血中濃度）效果，此一差異未見於本輪擷取之 label 段落，屬已知的文獻缺口，**若 manuscript 要
呈現 rifampin 交互作用，須註明本表數字僅代表急性單次併服情境**，不可推論至慢性合併治療。

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
