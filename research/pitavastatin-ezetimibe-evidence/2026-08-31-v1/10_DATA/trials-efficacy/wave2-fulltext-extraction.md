# Wave 2 full-text extraction — TE-002 (Tsujita 2023) and TE-003 (Ako 2024)

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Role: trials-efficacy-intelligence · Wave: 2（PI-authorized，Decision 2026-08-31-12）

本檔案為 `10_DATA/trials-efficacy/extraction-table.csv` 中 TE-002／TE-003 的 Wave 2 全文覆核附錄。
CSV 中原有的 abstract-level 摘錄維持不變（作為 provenance 對照），本檔案補上僅全文才有的細節。
全文取得方式、SHA-256、parse 狀態見 `fulltext-manifest.md`。所有數字均為全文逐字萃取，非轉錄自
二手來源。

---

## TE-002 — Tsujita K, Yokote K, Ako J, et al. J Atheroscler Thromb 2023;30(11):1580-1600.

### 收案與 disposition（解決 unresolved-questions.md Q6 的一部分：確認確切分組人數）

- Screening：483 名同意受試者 → 293 名符合資格並隨機分派至 4 組（PS 2mg n=73／PS 4mg n=73／
  K-924 LD n=73／K-924 HD n=74）。
- 給藥前脫落 5 名 → 288 名實際給藥（每組 n=72，因給藥前脫落調整後）。
- K-924 HD 組給藥後有 2 名因 AE 中途退出 → 286 名完成試驗。
- **Efficacy/Safety analysis set = 288 名（每組 n=72）**，非原始隨機分派的 293 名 — 這是
  extraction-table.csv 中 TE-002 population 欄位需要的精確化（原欄位僅寫「N=293 randomized into
  4 arms」，現補充：293 randomized → 288 efficacy/safety analysis set，each arm n=72）。
- Baseline characteristics（Table 1，4 組相近，無顯著組間差異）：平均年齡 56.1±9.0 歲；男性
  47.9%；BMI 23.4±3.7；Type 2 DM 11.1%（32/288）；高血壓 18.4%；baseline LDL-C 166.1±20.2 mg/dL。

### 主要 endpoint 的統計比較結構（**完整解決 Q6**）

原摘要僅列出四組各自的 LDL-C % change 點估計（−39.5% / −45.2% / −51.4% / −57.8%），未說明統計
比較設計。全文（Fig. 3 註腳與 Results 內文）明確給出：

- 統計模型：MMRM（mixed model for repeated measurements），以 treatment group、time point、
  treatment×time 交互作用、JAS 2017 risk category 為固定效應，baseline LDL-C 為共變量。
- **比較方式為明確的 pairwise（非 4 組聯合檢定、亦非 pooled FDC-vs-monotherapy 兩組檢定）**：
  1. **K-924 LD vs. PS 2mg**（primary comparison）：差異 −11.9%（95% CI −15.2% to −8.7%；
     p=0.000，文中列為 <0.01 顯著）。
  2. **K-924 HD vs. PS 4mg**（primary comparison）：差異 −12.7%（95% CI −15.9% to −9.4%；
     p=0.000，<0.01 顯著）。
  3. **K-924 HD vs. K-924 LD**（secondary/exploratory comparison）：差異 −6.4%（95% CI −9.6% to
     −3.2%；p≤0.001，顯著）。
- 樣本數估算（Methods）：預設 K-924 HD vs PS 4mg 及 K-924 LD vs PS 2mg 各自差異 10.1 個百分點、
  K-924 HD vs K-924 LD 差異 3.6 個百分點，two-sided α=0.05，分配比例 1:1:1:1。

**結論（供 `40_SYNTHESIS/` 直接引用）**：
- 「2mg+eze10 vs 4mg 單方」比較（K-924 LD −51.4% vs PS 4mg −45.2%）：**本研究未直接做此項統計
  檢定**（研究設計的正式比較是同劑量 pitavastatin vs 對應 K-924，而非跨劑量的 FDC-vs-高劑量單方
  比較）；此差異（−6.2 個百分點）僅為點估計相減，並非有 95% CI／p-value 支持的正式統計比較 —
  `pitavastatin topic.md`「Add ezetimibe or double the statin?」的框架若要引用本研究，應註明
  此點為**描述性觀察，非本研究的正式統計檢定結果**。
- 「2/10 vs 4/10」比較（K-924 LD −51.4% vs K-924 HD −57.8%）：**有正式統計檢定**，差異 −6.4%
  （95% CI −9.6% to −3.2%，p≤0.001），達統計顯著 — 可直接引用。

### 達標率

- LDL-C target attainment @ week 12：PS 2mg 100%／PS 4mg 98.6%／K-924 LD 97.2%／K-924 HD 100%
  （K-924 LD vs PS 2mg、K-924 HD vs PS 4mg 組間皆無顯著差異）。
- High-risk 病人（LDL-C 目標 <120 mg/dL）達標率：PS 2mg 100%／PS 4mg 94.1%／K-924 LD 100%／
  K-924 HD 100%。

### 安全性（**完整解決 Q2**：各劑量組分項 AE/ADR/CK/AST/ALT 數字）

**Table 3（Safety analysis set, n=72 each）**：

| | PS 2mg | PS 4mg | K-924 LD | K-924 HD |
|---|---|---|---|---|
| AE, n (%) | 12 (16.7) | 19 (26.4) | 18 (25.0) | 14 (19.4) |
| AE，P vs 對應組 | — | — | 0.305 (vs PS2mg) | 0.428 (vs PS4mg) |
| Serious AE, n (%) | 0 | 2 (2.8) | 0 | 0 |
| Discontinuation due to AE, n (%) | 0 | 0 | 0 | 2 (2.8) |
| ALT increased, n (%) | 0 | 4 (5.6) | 2 (2.8) | 4 (5.6) |
| AST increased, n (%) | 0 | 0 | 1 (1.4) | 2 (2.8) |
| Blood CPK increased, n (%) | 2 (2.8) | 3 (4.2) | 1 (1.4) | 0 |
| ADR, n (%) | 2 (2.8) | 5 (6.9) | 4 (5.6) | 5 (6.9) |
| ADR, P vs 對應組 | — | — | 0.681 (vs PS2mg) | 1.000 (vs PS4mg) |

（Fisher's exact test；K-924 LD vs PS 2mg、K-924 HD vs PS 4mg 之 AE 與 ADR 發生率**皆無統計
顯著差異**。）

- 無病人 AST/ALT/CK 達到預先設定的 cutoff（AST/ALT≥3×ULN 連續兩次、≥5×ULN、≥10×ULN；
  CK≥10×ULN 併肌肉症狀）。
- AST、ALT、γ-GT（肝功能）與 CK（肌肉標記）之平均值於治療後**顯著上升但仍在參考範圍內**，
  **唯一例外：PS 2mg 組的 CK**（原文明確寫「except for the case of CK in PS 2 mg」— 依 Numeric
  Integrity Rule 如實保留此措辭，本角色未能從 Table 3／內文取得 PS 2mg 組 CK 平均值超出參考範圍的
  確切數字，僅有此定性敘述，供全文之 Supplementary Table 7 若未來取得可再補）。
- 空腹血糖（PS 4mg 組）與 HbA1c（除 PS 2mg 組外的所有組）於治療後上升，但 HbA1c 平均值仍在參考
  範圍內。
- 嚴重 AE：PS 4mg 組 2 例（泌尿道結石、攝護腺癌），因果關係已排除。
- 因 AE 中止試驗藥物：K-924 HD 組 2 例（掌蹠膿疱病、ALT 上升 — 後者因果關係未能排除）。

### 與其他來源的交叉引用（新發現，供 synthesis 參考）

- 討論段落明確提及並與**本專案 TE-001（Taiwan Chou 2022 trial）直接比較**：「In a recent article
  from Taiwan, another formulation of a 2 mg pitavastatin/10 mg ezetimibe fixed-dose combination
  provided a 51% reduction in LDL-C from baseline to week 12, **which is similar to** that provided
  by a K-924 LD treatment in the current study.」— 兩個獨立試驗（台灣/日本）於 2mg pitavastatin+
  eze10 劑量下的 LDL-C 降幅高度一致（−51.04%／−50.5% vs −51.4%），跨族群一致性佐證強化 Level 1
  證據。
- 引用 REAL-CAD 試驗（日本 CAD 病人，pitavastatin 4mg vs 1mg，HR 0.81, 95% CI 0.69–0.95）作為
  「高劑量 pitavastatin 本身即有心血管結果證據」的背景 — **此為新識別到的潛在 Level 1/2 補充證據**
  （pitavastatin 劑量本身的 hard-outcome 證據，非 FDC 專屬），尚未獨立驗證，建議列入 Wave 2/3
  candidate（見 `unresolved-questions.md` 新增 Q8）。

---

## TE-003 — Ako J, Yokote K, Tsujita K, et al. J Atheroscler Thromb 2024;31(3):288-305.

### 收案與族群（精確化）

- Informed consent 130 名 → 110 名符合資格 → 1 名因給藥錯誤（誤給 K-924 HD）改分至 HD 組、
  1 名因缺乏臨床追蹤資料被排除分析 → **Efficacy/safety analysis set = 109 名（K-924 LD n=62,
  K-924 HD n=47）**，與摘要一致。
- Baseline：平均年齡 63.3±10.1 歲；男性 67.9%；T2DM 46.8%；FH 6.4%（7 名，3 heterozygous FH +
  4 unknown）；secondary prevention 44.0%。追蹤期 2020年3月–2021年8月。
- 治療期間：K-924 LD 組有 6 名於 week 24 後 up-titrate 至 K-924 HD（up-titration 後再降
  13.8±11.4%，from 96.3±12.6 to 83.6±19.3 mg/dL）；K-924 HD 組有 3 名因未達標而加用其他降脂藥。

### LDL-C 療效（全文精確數字，補充摘要層級數字）

| | Total (n=109) | K-924 LD (n=62) | K-924 HD (n=47) |
|---|---|---|---|
| Baseline LDL-C, mg/dL | 134.4±37.9 | 133.3±33.2 | 135.9±43.7 |
| Week 52 (LOCF), mg/dL | 91.3±23.8 | 92.7±22.1 | 89.4±26.0 |
| % change | −30.3±14.3 (p<0.001) | −29.5±11.7 (p<0.001) | −31.3±17.2 (p<0.001) |

- 排除 up-titrate／加藥病人後之敏感性分析：K-924 LD（排除 6 名 up-titrate 者）−28.9±11.8%
  （n=56, p<0.001）；K-924 HD（排除 3 名加藥者）−29.1±14.5%（n=44, p<0.001）。
- Baseline LDL-C 高低次族群：low-LDL-C 次族群（<中位數, n=54）−26.4±10.8%；high-LDL-C 次族群
  （≥中位數, n=55）−34.1±16.3%（皆 p<0.001）。
- FH 次族群（n=7）：−37.2±29.8%（p=0.016）；non-FH（n=102）：−29.8±12.7%（p<0.001）。

### 達標率（Table 3，精確補完摘要中的 91.8%/37.5%）

| Risk category | Target | Total n/N (%) | K-924 LD n/N (%) | K-924 HD n/N (%) |
|---|---|---|---|---|
| Primary prevention, overall | 依風險分層 | 56/61 (91.8) | 37/40 (92.5) | 19/21 (90.5) |
| — High-risk | <120 mg/dL | 44/49 (89.8) | 31/34 (91.2) | 13/15 (86.7) |
| Secondary prevention, overall | 依風險分層 | 18/48 (37.5) | 9/22 (40.9) | 9/26 (34.6) |
| — History of CAD | <100 mg/dL | 4/7 (57.1) | 3/5 (60) | 1/2 (50) |
| — CAD + high-risk conditions | <70 mg/dL | 14/41 (34.1) | 6/17 (35.3) | 8/24 (33.3) |

### 安全性（**大幅補完摘要層級的極簡描述**——摘要只寫「a single adverse drug reaction」，
未提及整體 AE 發生率，全文揭露如下）

| | Total (n=109) | K-924 LD (n=62) | K-924 HD (n=47) |
|---|---|---|---|
| AE, n (%) [事件數] | 65 (59.6) [129] | 36 (58.1) [70] | 29 (61.7) [59] |
| Serious AE, n (%) [事件數] | 12 (11.0) [15] | 6 (9.7) [8] | 6 (12.8) [7] |
| AE 導致停藥, n (%) [事件數] | 1 (0.9) [1] | 1 (1.6) [1] | 0 (0.0) [0] |
| ADR, n (%) | 1 (0.9) | 0 | 1 (2.1) |

- **本研究整體 AE 發生率高達 59.6%**（原摘要完全未提及此數字，僅稱安全性良好並提到單一 ADR）—
  **這是 abstract-level 萃取與全文之間的重大資訊落差**，`pitavastatin topic.md`／未來簡報若僅
  依賴 abstract 摘要「well-tolerated」的措辭，可能低估了 AE 發生率的量級（雖然多數 AE 為輕度且
  非藥物相關 — 見下）。
- 12 名病人共 15 件嚴重 AE（K-924 LD 6 名 8 件、K-924 HD 6 名 7 件），其中 1 件（肺腺癌）導致
  K-924 LD 停藥；**這 15 件嚴重 AE 中沒有一件被判定為 ADR**（即因果關係皆與研究藥物無關）。
- 唯一 ADR：K-924 HD 組 1 名病人（0.9%），blood CK 上升（week 0: 202 U/L → week 12: 843 U/L，
  參考範圍 40–150 U/L，判定為 ADR）；繼續投藥後 CK 逐漸恢復（week 24/32/40/52 分別為
  287/438/125/151 U/L）。
- 無病人 ALT/AST ≥3×ULN（連續兩次）或 CK≥10×ULN。
- 血糖與 HbA1c：全體由 113.6±17.8 升至 116.1±22.1 mg/dL（p=0.049）、6.39±0.72% 升至
  6.55±0.85%（p<0.001）於 week 52 (LOCF)；文中提及 T2DM 與非 T2DM 病人結果相似（原文於此處
  被截斷，本角色未讀到後續完整句子，見下方 unresolved 標記）。

**Numeric Integrity 註記（已核實，非截斷）**：複核 PDF 原文確認「The results were similar in
patients with or without T2DM」是該段落的完整結尾句（緊接 PDF 分頁，句尾句點疑似被 LlamaParse
解析時遺漏，屬解析 artifact，非內容缺漏）；原文**未提供** T2DM vs 非-T2DM 次族群各自的確切
HbA1c/glucose 數值，僅有這句定性敘述「結果相似」。故 T2DM 次族群量化數字為 INSUFFICIENT
EVIDENCE（本文獻未報告），非本角色遺漏萃取。
