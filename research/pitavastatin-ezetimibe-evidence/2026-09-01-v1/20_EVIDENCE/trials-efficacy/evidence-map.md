# evidence-map — trials-efficacy-intelligence / Wave 1 (RUN 2026-09-01-v1)

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-09-01-v1`
Role: trials-efficacy-intelligence · Wave: 1（focus areas 2、3，並貢獻 focus area 5 trial-side 內容）

本檔案為本 run 新增內容，**不重複**前一 run（2026-08-31-v1）`20_EVIDENCE/trials-efficacy/
evidence-map.md` 已建立的 Level 1/2/3 完整框架、TE-001 到 TE-015 的詳細分析——那些結論在此視為
已確立的 baseline，僅在有新發現或需要修正時才會提及。每個論斷依 `CLAUDE.md` §7 標註 Evidence
Hierarchy，並依 `01_RESEARCH-CHARTER.md` focus area 6 新增 **claim-safe taxonomy** 標籤：
`superiority` | `noninferiority` | `LDL-C surrogate efficacy` | `observational signal` |
`subgroup-hypothesis-generating` | `guideline-consensus` | `expert-inference`。

---

## Focus area 2：Direct pitavastatin+ezetimibe 證據延伸 + RWE 搜尋（Q5 初步答案）

**Q5（04_OPEN-QUESTIONS.md）— pitavastatin/ezetimibe FDC 的 real-world evidence 是否存在？**

**答案（本 Wave 1 檢索結果）**：除前一 run 已找到並全文驗證的 **TE-013**（Lu YW et al. Acta
Cardiol Sin 2026——Taiwan 兩家醫學中心、N=120、post-PCI 真實世界世代，pitavastatin 4mg+ezetimibe
10mg）之外，本 Wave 1 **未發現**任何其他專屬於 pitavastatin+ezetimibe FDC 的 RWE（registry／
claims database／post-marketing observational study）。多輪不同關鍵字組合的 `research_hub`
檢索（real-world evidence、registry、claims database、post-marketing surveillance，交叉 Taiwan／
Korea／Japan／2026 等地區與年份限定詞）均未命中新結果。

- Evidence Hierarchy：目前 pitavastatin+ezetimibe FDC 的 RWE 證據基礎 = **僅 TE-013 一篇**
  （OBSERVATIONAL EVIDENCE，單臂、N=120、兩中心）。
- Claim-safe tag：`observational signal`——不應被詮釋或引用為比 TE-013 更廣泛、更具代表性的
  「RWE 已充分支持」的結論；目前的 RWE 證據基礎仍屬單一、小樣本、單一國家。
- **對照佐證（非 pitavastatin 專屬，但有參考價值）**：檢索過程中找到一篇**同類但非
  pitavastatin**的 FDC real-world 研究——"26-A-9768-ACC Real-World Lipid-Lowering Efficacy and
  Goal Attainment with Atorvastatin/Ezetimibe Fixed-Dose Combination Therapy"（ACC 2026 摘要，
  DOI 10.1016/j.jacc.2026.02.425，**本角色僅確認其存在與識別資訊，未做內容驗證，非本專案核心
  引用**）——顯示 statin+ezetimibe FDC 這個藥物類別的 RWE 證據正在其他藥物累積中，但 pitavastatin
  這個特定分子的 RWE 目前仍相對稀少，這本身是一個值得在 attack/defense 章節誠實揭露的限制
  （見下方 focus area 5 章節）。
- 2mg vs 4mg、2/10 vs 4/10、add-ezetimibe-vs-dose-escalation 這些前一 run 已透過 TE-002
  （Tsujita 2023 全文）、TE-015（Jeong 2022）徹底建立的資料，本 Wave 1 檢索**未發現**任何更新、
  更新的試驗補充或推翻既有結論——**維持前一 run 的所有數字與統計顯著性判讀不變**，包括前一 run
  Wave 3 已明確記錄的「K-924 LD (2/10) vs PS 4mg 單方」這項跨劑量比較**沒有正式統計檢定**的
  重要限定（見前一 run evidence-map.md Q6 章節）。

---

## Focus area 3：Level 3 hard-outcome 缺口再確認 + 兩篇新發現的 HIJ-PROPER substudy

### 缺口再確認（未關閉，維持前一 run 判斷）

依 Director 指示，本 Wave 1 不假設前一 run「Level 3 缺口尚未關閉」的結論仍然成立，而是**重新
檢索**。結果：**未發現任何 2026-08-31 之後發表、足以關閉此缺口的新試驗**——HIJ-PROPER
（Hagiwara 2017, Eur Heart J，整體 primary endpoint HR 0.89, 95% CI 0.76–1.04, P=0.152，**未達
統計優越性**）**仍是**唯一直接檢驗 pitavastatin+ezetimibe vs pitavastatin 單方 hard-outcome 的
RCT。Claim-safe tag（整體試驗結果）：`noninferiority`不適用（此非 noninferiority 設計）、
`superiority` 未達成——正確標籤為單純陳述「未達統計顯著」，不套用任何 claim-safe 正面標籤。

### TE-016（新發現）— Yamaguchi J et al. Atherosclerosis 2018（sitosterol/absorber-phenotype substudy 的完整發表）

前一 run 僅從 HIJ-PROPER 母試驗論文的簡短次族群提及取得 sitosterol 訊號（HR 0.71, 95% CI
0.56–0.91）。本 Wave 1 發現這個訊號其實有**專屬的完整發表**：Yamaguchi J, Kawada-Watanabe E,
Koyanagi R, et al. "Baseline serum sitosterol level as predictor of adverse clinical events in
acute coronary syndrome patients with dyslipidaemia: A sub-analysis of HIJ-PROPER." Atherosclerosis
2018;274:139-145（DOI 10.1016/j.atherosclerosis.2018.04.036，PMID 29772482）——身份已透過
research_hub/Crossref 交叉驗證。

- **重要方法論限制（誠實揭露）**：本篇的量化內容（sitosterol cutoff 2.2 μg/mL、「效果獨立於
  LDL-C 降幅」的敘述）僅來自 `WebSearch` 聚合摘要，**未經本角色獨立全文核實**——嘗試以
  `WebFetch` 讀取 ScienceDirect abstract 頁面遭遇 HTTP 403（正確回報為無法取得，非
  confabulation），亦未嘗試繞過。依 `CLAUDE.md` §9 tool-confabulation caution，本角色**不會**
  將這些數字視為與前一 run 其他全文驗證過的數字同等確定——標記信心度 MODERATE，非 HIGH。
- Evidence Hierarchy：**hypothesis-generating / INSUFFICIENT EVIDENCE**（與前一 run 對
  absorber-phenotype 次族群的既有標註一致——即使這是該訊號的「正式、完整」發表，仍不改變其
  次族群、非預先驗證為 primary 的本質）。
- Claim-safe tag：`subgroup-hypothesis-generating`。
- **建議**：列為 Wave 2 優先全文驗證項目（若 paper-search/llamaparse 恢復連線，或找到合法
  open-access 副本）。在此之前，`40_SYNTHESIS/` 若引用本篇，應同時揭露「數字尚待獨立全文核實」
  這個限定詞。

### TE-017（新發現）— HIJ-PROPER 依 baseline LDL-C 分層的 statin-naive 次族群分析

Scientific Reports 2021（DOI 10.1038/s41598-021-87098-x，PMCID PMC8021554，開放取用）——**這是
本 Wave 1 最重要的新發現**。透過合法 PMC 開放取用頁面直接 `WebFetch` 取得（非付費牆，非繞過機制；
嘗試下載 PDF 供 LlamaParse 解析時遭遇與前一 run 相同的 PMC 反機器人 challenge，未破解，故僅有
WebFetch 頁面內容而非全文 PDF 解析）：

- 收案：HIJ-PROPER 母試驗中的**statin-naive** 病人子集（N=1429），依 enrollment 時 baseline LDL-C
  中位數（131 mg/dL）分為兩組。
- **低 LDL-C 組**（<131 mg/dL, N=686）：HR 1.13, 95% CI 0.87–1.47, P=0.35——**無顯著差異**，加用
  ezetimibe 無臨床效益訊號。
- **高 LDL-C 組**（≥131 mg/dL, N=743）：HR 0.72, 95% CI 0.56–0.91, P=0.007——pitavastatin+
  ezetimibe **顯著優於**pitavastatin 單方。
- **Interaction P = 0.012**——這個交互作用 p 值本身有意義：支持「baseline LDL-C 是真正的效果
  修飾因子（effect modifier）」，而非單純在任意切分下找到的巧合性次族群訊號。
- Evidence Hierarchy：DIRECT EVIDENCE **僅限於**這個 pre-specified statin-naive／baseline-LDL-C
  次族群本身，但仍從屬於一個整體 primary endpoint 未達顯著的母試驗——**不可**被引用為「已證實
  pitavastatin+ezetimibe 在高 LDL-C ACS 病人中有效」這種一般性、settled 的論斷。
- Claim-safe tag：`subgroup-hypothesis-generating`（但因 interaction p=0.012 的支持，比一般
  post-hoc 次族群訊號更具方法論份量，這個區別值得在 synthesis 中保留，而非與 sitosterol
  次族群的證據強度完全劃上等號）。
- 信心度：N/cutoff/endpoint 定義 = HIGH（兩個獨立管道交叉核對一致）；HR/CI/p-value 具體數字 =
  MODERATE（僅單一 WebFetch 來源，未經第二管道或全文 PDF 交叉驗證）。

**⚠ 兩個次族群軸線不可混淆**：TE-016（依 sitosterol／cholesterol-absorber phenotype 分層）與
TE-017（依 baseline LDL-C 分層）是**兩個概念上獨立的次族群切分方式**，即使都指向「並非所有
HIJ-PROPER 病人都同等受益於加用 ezetimibe」這個大方向。`40_SYNTHESIS/` 引用時應分別標註，
不可合併為單一「HIJ-PROPER 次族群顯示效益」的籠統敘述，需明確指出是依哪個變數分層。

---

## Director 追加驗證任務：K-924 matched-dose LS-difference 數字獨立核實（2026-09-01）

Director 轉來 safety-pharmacology 的 positioning-brief 使用了「pitavastatin 2mg+ezetimibe10mg
(−51.4%) vs pitavastatin 4mg (−45.2%)」作為「add-ezetimibe 勝過 dose-doubling」的直接頭對頭論據，
並正確標記此為可疑（很可能不是 prespecified/formally tested 的跨組比較）；Director 轉知的替代
數字為「combo 2/10 vs pitava 2 = −11.9%（95% CI −15.2 to −8.7）」與「combo 4/10 vs pitava 4 =
−12.7%（95% CI −15.9 to −9.4）」，但這兩個數字當時**未經任何角色從原始來源獨立核實**——是透過
外部 QA relay 傳給 Director，非本專案任一 specialist 自己查核。

**本角色核實結果：Director 轉知的數字完全正確，且本角色早已從原始文獻全文獨立驗證過這組數字**
——這正是前一 run（2026-08-31-v1）Wave 2 由本角色親自下載 K-924 trial（Tsujita K et al.
J Atheroscler Thromb 2023;30(11):1580-1600，DOI 10.5551/jat.64006）的官方 J-STAGE 全文 PDF
（SHA-256 `afe6befc78a9084f95580e513568615618153abd45ddb20ff76ca5e9f4022c26`，見前一 run
`10_DATA/trials-efficacy/fulltext-manifest.md`）、以 LlamaParse 完整解析後，逐字記錄於前一 run
`10_DATA/trials-efficacy/wave2-fulltext-extraction.md` 的數字：

> 「K-924 LD vs. PS 2mg（primary comparison）：差異 −11.9%（95% CI −15.2% to −8.7%；p=0.000）」
> 「K-924 HD vs. PS 4mg（primary comparison）：差異 −12.7%（95% CI −15.9% to −9.4%；p=0.000）」
> （p 值依原文印刷方式如實保留為「0.000」，非本角色改寫）

統計模型為 MMRM，比較方式為**明確的同劑量配對比較**（K-924 LD vs 同為 2mg 的 pitavastatin；
K-924 HD vs 同為 4mg 的 pitavastatin），**不是** safety-pharmacology 原始引用的「2/10 跨組比較
4mg 單方」那種混合劑量對比。這也再次確認 Director 的判斷完全正確：「−51.4% vs −45.2%」是兩個
不同劑量分組各自的 LDL-C% 點估計相減，**並非**本研究正式檢定過的統計比較（此點已在前一 run
Wave 3 的 unresolved-questions.md Q6 詳細記錄並標記為 RESOLVED，結論相同）。

**結論**：`VERIFIED`（非 `BLOCKED_FOR_SOURCE`／`NEEDS_ANALYST`）——safety-pharmacology 可將
「Director-reported, not independently verified」的標籤升級為「trials-efficacy-intelligence
independently verified against primary full text (prior run, Wave 2)」。

---

## Focus area 5：Attack/Defense 章節 — Trial-side 貢獻（誠實、不軟化的對立觀點）

依 Director 指示，此為刻意要求的誠實反方論證工作，非需要淡化處理。

### 攻方論點 1：「product-specific MACE limitation」

Pitavastatin+ezetimibe FDC **沒有**自己專屬的、達統計顯著的 hard-outcome 優越性證據——
HIJ-PROPER 整體 primary endpoint HR 0.89（95% CI 0.76–1.04, P=0.152）未達顯著。目前所有支持
「combination 有 CV outcome 效益」的較強證據（RACING）都是**不同 statin**（rosuvastatin），
不能直接類推至 pitavastatin。這是本專案從第一個 run 就標註的核心誠實限制，本 Wave 1 的搜尋
**確認**此缺口至今未被任何新試驗關閉。Claim-safe tag：`observational signal`（RACING）＋
明確聲明 pitavastatin 專屬證據 = `subgroup-hypothesis-generating`（HIJ-PROPER 次族群）而非
`superiority`。

### 攻方論點 2：「Indirect-evidence conflation risk」

見上——RACING（rosuvastatin）、REPRIEVE（pitavastatin 單方 vs 安慰劑，HIV 族群）、REAL-CAD
（pitavastatin 劑量強度，無 ezetimibe）三者都不可被引用為「pitavastatin+ezetimibe FDC 的 CV
outcome 證據」。這是前一 run 已建立、本 run 延續維護的最高風險過度延伸點。

### 攻方論點 3：「Maximize statin first」反方立場（trial-side 論據）

反方合理立場的**證據基礎**：REAL-CAD（前一 run TE-012）本身就是「先把 statin 劑量推到最大」策略
的正向 hard-outcome RCT（pitavastatin 4mg vs 1mg，HR 0.81, 95% CI 0.69–0.95, P=0.01，日本次級
預防 CAD 族群）——這代表「單純提高 statin 劑量」這條路徑，在 pitavastatin 本身，**確實有**
達統計顯著的 hard-outcome 證據支持，比 pitavastatin+ezetimibe FDC 的 hard-outcome 證據（僅到
次族群層級）**證據等級更完整**。誠實的立場應該是：若病人能耐受劑量提升且尚未達到高劑量上限，
「先最大化 statin 劑量」這個策略本身有比 FDC 更直接的 pitavastatin 專屬 hard-outcome 證據支持
——FDC 的優勢主要在於 LDL-C 降幅更大（Level 1，強證據）與耐受性/依從性（RACING 提供的間接
strategy-level 證據），而非「FDC 本身已證實比最大化劑量更能降低 CV event」這個更強的論斷，
後者目前沒有直接證據。Claim-safe tag：REAL-CAD 部分 = `superiority`（達統計顯著，但範圍限定於
pitavastatin 單方劑量強度問題，非 FDC 問題）；FDC vs 最大化劑量的直接比較 = 目前無資料，
應標記 `expert-inference`（若要在簡報中做出建議，必須明確揭露這是專家推論而非直接證據）。

### 攻方論點 4：「何時 hard-outcome-proven 替代方案更站得住腳」（trial-side 論據）

本 Wave 1 確認並驗證三個替代方案各自的 hard-outcome 證據狀態，供 safety-pharmacology／Director
整合進 attack/defense 完整章節：

| 藥物類別 | 主要 hard-outcome trial | 證據狀態 | Claim-safe tag |
|---|---|---|---|
| Bempedoic acid | CLEAR-Outcomes（Nissen SE et al. NEJM 2023, DOI 10.1056/NEJMoa2215024） | **已完成、已發表的正向 CV outcome RCT**（statin-intolerant 高風險族群） | `superiority`（於其設計族群內） |
| PCSK9-targeting therapy（evolocumab） | FOURIER（NEJM 2017, DOI 10.1056/NEJMoa1615664） | **已完成、已發表的正向 CV outcome RCT** | `superiority` |
| PCSK9-targeting therapy（alirocumab） | ODYSSEY OUTCOMES（NEJM 2018, DOI 10.1056/NEJMoa1801174，post-ACS 族群） | **已完成、已發表的正向 CV outcome RCT** | `superiority` |
| Inclisiran | VICTORION-2 Prevent（Am Heart J 2026 **設計/protocol 論文**，DOI 10.1016/j.ahj.2026.107493）；ORION-4（ISRCTN registry, 2018，同樣僅為設計登記） | **⚠ 本 Wave 1 檢索範圍內未找到任何已完成、已發表的 inclisiran hard-outcome 結果論文**——目前只有試驗設計/protocol 層級的公開資訊 | 目前僅能標記 `LDL-C surrogate efficacy`（inclisiran 對 LDL-C 降幅的證據充分），hard-outcome 層級應標記 `INSUFFICIENT EVIDENCE`／不適用 `superiority` |

**這個不對稱性是 attack/defense 章節的一個重要、值得誠實呈現的論點**：當有人主張「與其用
pitavastatin+ezetimibe FDC（Level 3 證據薄弱），不如直接用 hard-outcome-proven 的新藥」時，
這個論點對 bempedoic acid 與 PCSK9-targeting therapy 是**站得住腳**的（兩者都有完整發表的正向
hard-outcome RCT，證據等級**優於** pitavastatin+ezetimibe FDC 目前僅達次族群層級的 Level 3
證據）；但對 inclisiran 而言，**這個論點目前站不住腳**——inclisiran 本身也還沒有已發表的
hard-outcome 證據，只是 LDL-C surrogate 證據充分（ORION 系列）與試驗設計已公開（VICTORION-2
Prevent、ORION-4 尚在進行或設計階段）。若 40_SYNTHESIS/attack-defense 章節要呈現「hard-outcome-
proven 替代方案」這個框架，**必須排除 inclisiran** 或明確加註「hard-outcome 資料尚未成熟」，
否則會犯下與本專案核心紀律相同性質的過度延伸錯誤（把 surrogate/尚在進行的證據講成已證實的
hard-outcome 證據）。

**建議 Wave 2 待辦**：若 Director／safety-pharmacology 需要，可再搜尋是否有更新的 inclisiran
hard-outcome 資料（本 Wave 1 檢索範圍未窮盡所有可能管道，尤其 paper-search／tavily down 的情況
下搜尋深度有限）；同時 bempedoic acid／PCSK9i 的族群適用範圍（如 statin-intolerant vs 一般族群、
primary vs secondary prevention）需要與 pitavastatin+ezetimibe FDC 的目標族群做更精確的
apples-to-apples 比較，本 Wave 1 僅完成主要試驗身份與整體結果確認，尚未做族群可比性的深入分析。
