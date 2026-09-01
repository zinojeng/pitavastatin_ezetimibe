# 2026 血脂風險評估新思維：Beyond LDL（ApoB、Lp(a)、hs-CRP）與 Pitavastatin 之定位

**（本版為三方獨立查證後之最終版；所有修正處以「原稿……經查證修正為……」方式標示，不做無痕更動）**

## 查證層級聲明

- **第一部分（2026 ACC/AHA 之新規範）**：內容取自本專案已三重獨立驗證之 T-101 原始 PDF（DOI 解析＋Crossref metadata＋123頁系統性內部一致性查核），本次另由獨立查證代理以 PyMuPDF 直接對原始 PDF 逐頁全文檢索、確認頁碼與逐字引用。**結果：絕大多數內容逐字核實無誤，但發現一處確定性錯誤（§1.6 藥名，見下方修正說明）**——這也提醒即使是「三重驗證」層級的內容仍可能混入未經該次驗證管道確認的字句，故本次修正後方為可信賴之最終版本，而非原稿本身。
- **第二部分（台灣 2025 共識之對應內容）**：本次由獨立查證代理直接取得並逐頁讀完原始全文 PDF（內科學誌 2024;35:426-430，共5頁，含頁尾行進版權標示核對），確認引文逐字準確、且為該共識全文中關於 ApoB/Lp(a) 之全部內容。信心度由原稿之「單一管道擷取」上修為**已獨立驗證**。
- **第三部分（Pitavastatin 於 beyond-LDL 標記之文獻）**：本次查證改以 `search_pubmed`（直接回傳 PubMed 儲存之摘要文字的 metadata API，非由 LLM 摘要網頁內容）進行查核，並刻意避開 WebFetch 對 PubMed 頁面的摘要式擷取（該路徑實測僅返回 cookie-consent 頁面，證實此為必要的防呆措施，而非多餘步驟）。所有原稿引用之數字皆逐一核對通過，且新增五筆獨立查得、與本專案高度相關之文獻。**仍未取得任一篇全文**，僅為摘要層級查證，這點與原稿一致，未升級。

---

## 一、2026 ACC/AHA guideline：Beyond LDL 是這次改版的核心命名理由

### 1.1 guideline 改名理由（T-101 page e1163，收錄於「1.5. Scope of the Guideline」段落內）

> "This guideline is retitled from the '2018 Guideline on Management of Blood Cholesterol' to the '2026 Guideline on Management of Dyslipidemias' to reflect the evolving understanding of ASCVD risk associated with atherogenic lipoproteins beyond LDL particles, including TG and remnant particles, and Lp(a)."

逐字核實無誤。**原稿標示「T-101 Section 1.5」易讓讀者誤以為原文有一節標題即為「改名理由」，經查證修正說明：**該句實際上是「1.5. Scope of the Guideline」（範疇界定）段落內嵌的一句話，並非獨立標題節。頁碼 e1163 正確。

### 1.2 新的 LDL-C 計算方式（page e1166，Recommendation #3，**COR 1, B-NR**，逐字核實）

> "use of either the Martin/Hopkins equation or the Sampson/National Institutes of Health (NIH) equation is preferred over calculation by the Friedewald equation to estimate LDL-C."

### 1.3 Non-HDL-C 常規報告（page e1166，Recommendation #5，**COR 1, B-NR**，核實無誤）

### 1.4 進階脂蛋白次分類檢測 明文「不建議」（page e1166，Recommendation #6，**COR 3: No Benefit, B-NR**，核實無誤）

gradient gel electrophoresis、density gradient ultracentrifugation、NMR spectroscopy、ion mobility analysis 四種方法之列舉逐字核對相符，皆不建議常規使用。

### 1.5 ApoB（page e1166–e1167，核實無誤）

- **COR 2a, B-NR**（Rec #1）：on LLT 病人（尤其 ASCVD/CKM syndrome/type 2 diabetes/高TG）達 LDL-C/non-HDL-C 目標後，測 ApoB 評估是否需進一步強化治療。
- **COR 2b, B-NR**（Rec #2）：未用藥病人，測 ApoB 可能有助風險評估／起始治療決策／辨識遺傳性血脂疾病。

### 1.6 Lp(a)（Section 4.2.10，page e1234–e1235）

切點：**≥125 nmol/L 或 ≥50 mg/dL**（核實無誤）。

- **COR 1, B-NR**（建議#1，核實無誤）：所有 Lp(a) 升高者，積極控制其他可改變風險因子。
- **COR 1, B-R**（建議#2，核實無誤）：ASCVD + Lp(a)升高 + 未達LDL-C/non-HDL-C目標（最大耐受statin下）→建議加用有心血管效益證據之PCSK9 mAb。
- Statins 不降低 Lp(a)（"mean absolute difference, 1.1 mg/dL higher compared with placebo"——即較安慰劑組平均高 1.1 mg/dL，核實無誤）；PCSK9 mAb/siRNA 降Lp(a) "∼15% to 30%"（核實無誤）；apheresis 核准門檻 "Lp(a) ≥60 mg/dL (or 130 nmol/L) if they also have FH and CAD or PAD"（核實無誤）。

**新藥一句：原稿誤植具體藥名「pelacarsen類ASO、olpasiran類siRNA、口服小分子」，經查證修正。** 獨立查證代理以「pelacarsen」「olpasiran」為關鍵字對全文123頁逐字檢索，**兩個藥名在 T-101 全文中完全未出現，零命中**。T-101 於此處（page e1234，Section 4.2.10 Synopsis）的原文為：

> "Specific Lp(a)-lowering therapies that target Lp(a) production (eg, mRNA therapies or oral small-molecule inhibitors) are being investigated in randomized clinical outcomes trials."

正確修正為：**新一代 Lp(a) 標的療法（如 mRNA therapies 或口服小分子抑制劑）仍在隨機臨床結果試驗中進行研究**（逐字譯自 T-101，未指名特定藥物）。pelacarsen（一種 antisense oligonucleotide，非「mRNA therapy」）與 olpasiran（一種 siRNA）確為業界正在進行中的真實 Lp(a) 標的藥物，但**這是原稿由背景知識外加、並非 T-101 逐字內容**，且原稿的「ASO/siRNA」二分類法與 T-101 用語（統稱"mRNA therapies"）也不一致。若簡報中仍想點名這兩個藥物，應另行以 paper-search/PubMed 管道獨立查證後標註為外部來源，不可掛在「T-101 逐字」這一信心層級之下。

**章節性質（"全新獨立章節"）：原稿描述無法由本次查證完全證實，修正為謹慎表述。** 查證代理確認 page e1234 確有「4.2.10. Approach to Patients With Elevated Lp(a)」一節，內容與原稿描述相符；但單憑這份 2026 年版 PDF 無法比對 2018 年舊版目錄以確認是否為「全新」章節。故此處應表述為：Lp(a) 於本版guideline中列有專屬章節（4.2.10），**是否為相對 2018 年版新增的獨立章節待與舊版目錄比對確認**，不作為已驗證事實陳述。

### 1.7 hs-CRP／發炎（Table 13 Risk Enhancers，page e1188，核實無誤）

清單十項逐字核對相符：早發ASCVD家族史、高風險族裔、高多基因風險評分、慢性發炎疾病、Lp(a)≥125nmol/L或≥50mg/dL、hsCRP≥2 mg/L（>1次測量）、TG持續偏高、CKM症候群、LDL-C持續160-189/non-HDL190-219/apoB≥120、生殖相關風險標記。

**單位不一致問題：原稿提出之疑點經獨立查證，確認為真實、可重現之同文件內部不一致，且已定位到確切出處。**

原稿觀察「JUPITER敘述段落寫 hsCRP of ≥2 mg/dL，但Table 13寫 hsCRP≥2 mg/L」為真。查證代理進一步定位出**三個**同一切點的引用位置，其中兩處一致、一處為異常值：

| 位置 | 頁碼 | 原文 | 單位 |
|---|---|---|---|
| Risk Enhancers 正式建議文（COR 2a, B-R） | e1186 | "hsCRP is measured and is ≥2 mg/L on 2 successive occasions" | mg/L |
| Table 13 Risk Enhancers | e1188 | "hsCRP ≥2 mg/L on >1 occasion (if measured)" | mg/L |
| JUPITER試驗 supportive text（緊鄰Table 13上方，同頁） | e1188 | "elevated hsCRP of ≥2 mg/dL" | **mg/dL** |

即：guideline自身的正式建議文（e1186）與 Table 13（e1188）皆為 **mg/L**，唯獨與 Table 13 同頁、緊鄰其上的 JUPITER 試驗敘述段落寫成 **mg/dL**——這極可能是相對於 JUPITER 試驗實際入組標準（hsCRP ≥2.0 mg/L）的一個排印錯誤，但**依 T-101 原文逐字記錄，這確實是同一份文件內、同一數值切點的單位不一致**。

依本專案 Numeric Integrity Rule，記錄如下，不做調和統一：
`SOURCE_VALUE = "≥2 mg/dL"（page e1188, JUPITER supportive text）` vs. `SOURCE_VALUE = "≥2 mg/L"（page e1186 建議文 + page e1188 Table 13）`；`FLAG = POSSIBLE_ERROR`；`ACTION = NEEDS_ANALYST`。

JUPITER試驗：rosuvastatin 20mg，"RRR of 44% in MACE"（核實無誤）。Women's Health Study：hsCRP/LDL-C/Lp(a) 最高vs最低五分位校正後HR分別為 **1.70/1.35/1.33**（核實無誤，逐字對應 "adjusted hazard ratios for a first MACE were 1.70 for hsCRP, 1.35 for LDL-C, and 1.33 for Lp(a)"）。

---

## 二、台灣2025共識對應內容（逐字引用，已獨立驗證）

> 「此共識強調以LDL-C作為血脂管理路徑中的主要治療指標……Non-HDL-C的治療目標應高於LDL-C治療目標30 mg/dL……其他血脂指標如ApoB、Lipoprotein(a)亦具有獨立心血管風險預測的作用，可依目標對象臨床狀況、檢測可近性，納入做為進一步的血脂評估考量。」

（內科學誌 2024;35:426-430，DOI 10.6314/JIMT.202412_35(6).04，李貽恒、石崇良）

獨立查證代理直接讀完全部5頁原文（含頁尾行進版權標示核對確認真偽），確認：

- 引文逐字核對**完全相符**（僅有排版上「Lipoprotein (a)」多一空格之非實質差異）。
- **完整性聲明成立**：「ApoB」與「Lipoprotein」二詞在全文中各僅出現一次，均落在這段引文內；全文**無**獨立的 ApoB/Lp(a) 專節、**無**任何形式之COR/LOE分級（該共識全篇皆未使用正式分級系統）、**無**ApoB或Lp(a)之數字切點（相對地，LDL-C與non-HDL-C皆有明確mg/dL目標值表格），Figure 1、2 之非statin藥物路徑（ezetimibe、PCSK9 mAb/siRNA、ATP citrate lyase inhibitor）完全由LDL-C達標與否驅動，與ApoB、Lp(a)數值無關。
- 全文檢索確認：hs-CRP、多基因風險評分（polygenic）、CKM症候群（心腎代謝）**皆未出現**，包含摘要、風險分級表、兩張路徑圖、參考文獻列表在內。

原稿此段所有聲稱均獲獨立來源支持，可視為**已驗證**（GUIDELINE/CONSENSUS 層級，非DIRECT EVIDENCE），信心度由原稿之「單一管道」上修。

---

## 三、Pitavastatin 於 Beyond-LDL 標記文獻（PubMed摘要層級，經獨立查證）

以下五篇原稿引用數字，逐一經 `search_pubmed` 直接核對摘要原文，**全部確認無誤，無任何數字出入**：

| 文獻 | 查證結果 |
|---|---|
| PREVAIL US（Miller PE, Clin Ther 2016, PMID 26922296） | RLP-C −13.6[8.7] vs −9.3[9.5] mg/dL；IDL-C −9.5 vs −6.4（p<0.001）、VLDL3-C −4.1 vs −2.9（p<0.001）、ApoB/ApoA-I與TC/HDL-C比值皆p<0.001；HDL-C／Lp(a)-cholesterol無顯著差異 —— **確認逐字相符** |
| INTREPID（Joshi PH, AIDS 2017, PMID 28121706） | RLP-C −11.6 vs −8.5 mg/dL（p=0.01）；ApoB/ApoA-I、TC/HDL-C比值 p<0.05；HDL-C／Lp(a)無顯著差異 —— **確認逐字相符** |
| Tsimikas 2020（Eur Heart J, PMID 31111151） | 幾何平均比值1.11（95%CI 1.07-1.14, p<0.0001）；statin組+8.5%至+19.6%，安慰劑組−0.4%至−2.3% —— **確認逐字相符**；pitavastatin個別數字確認**摘要中確實未單獨列出**（摘要僅拆分出atorvastatin vs pravastatin一組數字：ratio 1.09, 95%CI 1.05-1.14）——原稿此處誠實承認資料不可得，經查證此為真，非迴避 |
| REPRIEVE Mechanistic Substudy（Lu MT, JAMA Cardiol 2024, PMID 38381407） | NCP volume校正後差異−4.3mm³（95%CI −8.6至−0.1, p=.04）；progression RR 0.67（95%CI 0.52-0.88, p=.003）；oxLDL −29%vs−13%（p<.001）；Lp-PLA2 −7%vs+14%（p<.001） —— **確認逐字相符，含原稿未附上之信賴區間** |
| Foldyna B PCAT substudy（JACC Cardiovasc Imaging 2026, PMID 41324519） | 高冠狀動脈負擔次族群 −1.7 vs +3.8 HU（p=0.016） —— **確認逐字相符** |

### 3.1 RLP-C（如上表，已驗證，不重複）

### 3.2 Lp(a)

PREVAIL US、INTREPID 兩篇：pitavastatin vs pravastatin，Lp(a)濃度變化無顯著組間差異（已驗證，見上表）。

Tsimikas 2020：6項RCT、5256病人統合分析，statin類別整體使Lp(a)上升（幾何平均比值1.11，各statin組+8.5%至+19.6%，安慰劑組−0.4%至−2.3%）；pitavastatin 2mg/day為納入的六治療組之一，但摘要未列出pitavastatin個別數字（已驗證為真）。

**新增（獨立查證代理新查得，原稿未收錄）：** Wang X et al., "Effect of different types and dosages of statins on plasma lipoprotein(a) levels: A network meta-analysis," Pharmacol Res 2021, PMID 33166736, DOI 10.1016/j.phrs.2020.105275 —— 20項RCT、n=23,605、11種介入之網絡統合分析。整體結論：statin類別對Lp(a)並無具臨床意義之類別效應；**摘要原文明確指出："Moderate-intensity pitavastatin tended to have the best effect on reducing Lp(a) levels; nevertheless, it was insignificant."**（中劑量pitavastatin在降低Lp(a)上呈現最佳趨勢，但未達統計顯著）。

這是目前查得最接近「pitavastatin對Lp(a)特異性影響」的證據，方向與Tsimikas 2020中atorvastatin/rosuvastatin/pravastatin呈現的「上升」訊號**相反**（此處為未達顯著之下降趨勢）。**證據強度定性：網絡統合分析之次要訊號、未達統計顯著、其摘要本身亦自陳有risk-of-bias疑慮**——屬 INSUFFICIENT EVIDENCE / hypothesis-generating 層級，不可作為「pitavastatin降低Lp(a)」之標題性結論，僅適合以謹慎措辭帶出、並標記待進一步分析（NEEDS_ANALYST）。

### 3.3 氧化壓力／發炎

REPRIEVE Mechanistic Substudy、Foldyna PCAT substudy：如上表，已驗證。

**原稿「3.4其他未深入查證」中的 Yoshida 2013，經獨立查證取得完整摘要數據，移入本節並詳列：**

Yoshida H et al., VISION trial, Atherosclerosis 2013, PMID 23174369, DOI 10.1016/j.atherosclerosis.2012.10.069 —— pitavastatin 2mg（n=21）vs atorvastatin 10mg（n=21）之小型head-to-head試驗，12週。**唯一達統計顯著之組間差異為 MDA-LDL/apoB 比值：pitavastatin −13% vs atorvastatin −0.7%（p=0.04）**，其餘組間比較皆未達顯著。值得注意的細節（原稿未提及、若簡化為「pitavastatin降低氧化壓力」會遺漏）：**OxPL/apoB 在兩組內皆顯著上升**；small-dense LDL、MDA-LDL、Lp-PLA2/apoB則兩組皆下降。證據等級：n僅21/21之小型RCT，單一組間指標達顯著，需謹慎解讀，不宜作為pitavastatin全面降低氧化壓力之定論。

**新增：** Lee SH et al., 韓國pitavastatin-vs-atorvastatin劑量滴定試驗, 2007, PMID 18158077 —— pitavastatin 2mg vs atorvastatin 10mg，8週，n=268隨機/222完成。**hs-CRP有測量，但組間變化百分比無顯著差異**（LDL-C達標率亦無顯著差異：92.7% vs 92.0%）。此為與Yoshida 2013方向一致的謹慎訊號（另一篇head-to-head試驗同樣未見pitavastatin在hs-CRP上顯著優於atorvastatin）。

**新增，銜接 Search Protocol 第5項（2mg vs 4mg劑量反應）：** Feng T et al., Clin Ther 2017, PMID 28185713, DOI 10.1016/j.clinthera.2017.01.013 —— pitavastatin劑量比較（2mg vs 4mg，n=60，48週），以3T MRI評估lipid-rich carotid plaque。**高劑量組於Lp(a)、hs-CRP、IL-6、homocysteine皆呈現顯著較大改善（均p<0.001）**，同時斑塊脂質核心亦有較大幅度縮小。此為原稿完全未收錄、但直接對應本專案Search Protocol第5項（2mg vs 4mg劑量比較）之beyond-LDL標記劑量反應證據，屬單一小型RCT，建議標記為DIRECT EVIDENCE（劑量比較層級）但樣本數小，待更多重複驗證。

### 3.4 台灣／糖尿病亞族群相關文獻（新增小節，摘要層級、待全文）

**新增，與本專案台灣族群／糖尿病角度高度相關：** Liu PY et al., PAPAGO-T Study, PLoS ONE 2013, PMID 24098467, DOI 10.1371/journal.pone.0076298 —— 台灣本土RCT，pitavastatin 2mg（n=112）vs atorvastatin 10mg（n=113），12週，其中糖尿病亞族群n=125。摘要指出兩組HOMA-IR/insulin皆同幅上升，**但HbA1c僅在atorvastatin組顯著上升（p=0.001），pitavastatin組未達顯著**；摘要未提供具體hs-CRP數字，**需取得全文方可引用定量發炎指標數據**。此文獻與本專案guideline-risk-intelligence/safety-pharmacology-intelligence兩部門所關注之台灣族群、糖尿病亞族群、glycemic profile角度高度相關，但目前為止全文未收錄於任何部門的Source Inventory，建議列入Wave 2待辦（BLOCKED_FOR_SOURCE，全文尚未取得）。

### 3.5 其他未深入查證（原稿保留部分）

Yoshida 2013 已移至§3.3（見上），此處不再重複列出。Chapman 2011 回顧文章；Koutsogianni 2026 高Lp(a)病人降脂藥物影響（未指名pitavastatin）——兩篇仍維持原稿之「未深入查證」狀態，本次查證未觸及。

---

## 四、修正與更新摘要（總結）

**本次查證共發現並修正 1 處確定性錯誤、2 處措辭精確度問題、確認 1 處真實的原文內部不一致，並新增 5 筆具引用價值之文獻。**

1. **確定性錯誤（已修正）**：§1.6 Lp(a)新藥句原稿列出「pelacarsen」「olpasiran」兩個具體藥名，T-101全文123頁逐字檢索**零命中**，非該來源內容，已改回逐字譯自T-101原文的「mRNA therapies 或口服小分子抑制劑」，並註明兩藥名如需引用應另行獨立查證、標示為外部來源。
2. **措辭精確度（已修正）**：§1.1 標題「Section 1.5」易誤導為獨立節名，修正說明其實際位於「Scope of the Guideline」段落內；§1.6「全新獨立章節」缺乏與2018舊版之直接比對佐證，已改為待驗證表述。
3. **原文內部不一致（已確認為真，非查證誤判）**：§1.7 hs-CRP切點單位在同一份T-101文件中確有 mg/L（正式建議文e1186＋Table 13 e1188）與 mg/dL（JUPITER敘述句，同頁e1188）並存的情形，已按Numeric Integrity Rule完整記錄兩處SOURCE_VALUE與頁碼，標記NEEDS_ANALYST，不做調和。
4. **信心層級上修**：第二部分（台灣共識）由「單一管道擷取」上修為「已獨立驗證」；第三部分五項原有引用數字全數逐一核對無誤，方法由潛在風險較高的WebFetch頁面摘要改為直接metadata API擷取。
5. **新增文獻（5筆）**：Wang X 2021 NMA（pitavastatin對Lp(a)之非顯著下降趨勢，§3.2，INSUFFICIENT EVIDENCE等級）、Yoshida 2013 VISION試驗完整細節（§3.3，含OxPL/apoB兩組皆上升之限制）、Lee SH 2007（hs-CRP無顯著組間差異，§3.3）、Feng T 2017（2mg vs 4mg劑量反應對Lp(a)/hs-CRP/IL-6之影響，§3.3，直接對應Search Protocol第5項）、PAPAGO-T（台灣DM亞族群，§3.4，全文未取得，列為待辦）。

**未變動之處**：凡三位獨立查證代理確認為準確者，本版維持原稿數字與描述,僅將原稿之保留式措辭（如「待查證」）在有充分佐證的段落中適度上修為更肯定的語氣;凡原稿誠實標示「摘要未列出」「未取得全文」而查證代理亦未能取得者（如Tsimikas 2020之pitavastatin個別Lp(a)數字、PAPAGO-T之具體hs-CRP數字），維持「資料不可得」之誠實表述，不以推測數字填補。
