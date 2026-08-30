# unresolved-questions — trials-efficacy-intelligence / Wave 1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`

本檔案為本角色（trials-efficacy-intelligence）owned path 下的工作清單，供 Wave 2 延續或提報
Research Director 併入專案層級 `04_OPEN-QUESTIONS.md`（該檔案僅 Director 可寫，本角色不直接
編輯）。分類沿用 CLAUDE.md §6：`NEEDS_SOURCE` | `NEEDS_ANALYST` | `NEEDS_METHODS` | `NEEDS_PI`。

## Q1 [NEEDS_SOURCE] Chou 2022 Phase III FDC trial 的收案國家範圍

`pitavastatin topic.md` 描述 TE-001（Chou MT et al. Clin Ther 2022）為「多國多中心
（Taiwan/Australia/NZ）」試驗，但本角色透過 Crossref 取得的作者列（全數為台灣姓名模式，加一位
可能屬於跨國 CRO 的 "Anthony McGirr"）不足以獨立確認 Australia/NZ 收案中心是否存在。全文取得
失敗（見 `10_DATA/trials-efficacy/fulltext-manifest.md`）。
**需要**：Wave 2 取得全文（Methods/收案中心清單）或透過 ClinicalTrials.gov 登錄資訊核實。在此之前，
`40_SYNTHESIS/` 若要重複「多國」的描述，應標註為「PI-supplied，未經本角色獨立確認」。

## Q2 [NEEDS_SOURCE] TE-002（Tsujita 2023 K-924 4-arm 劑量比較）各劑量組的分項安全性數字

Abstract 層級僅有「AE/ADR 發生率在 FDC 與單方組間無顯著差異」的敘述性結論，沒有逐組
（2mg / 4mg / 2/10 / 4/10）的 CK、肝功能、肌肉相關 AE 分項數字。這正是
`pitavastatin topic.md` Search Protocol item 5 明確要求的比較維度（「muscle AE / liver enzyme /
CK / CKD / elderly / incremental benefit per dose increase」）。
**需要**：Wave 2 取得全文（J Atheroscler Thromb 可能為 open access，見 fulltext-manifest.md 建議
優先序）以完整回答 item 5。

## Q3 [NEEDS_METHODS] HIJ-PROPER 四篇 substudy 是否需要納入 Wave 2 萃取範圍

Wave 1 檢索過程中額外定位到 4 篇 HIJ-PROPER substudy（未逐一驗證數字，僅記錄存在，避免超出
Wave 1「先驗證既有引用」的範圍）：

- Ogiso M et al. Circ Rep 2020（PMID 33693218）— single-vessel vs multivessel disease 分層
- Arashi H et al. J Am Heart Assoc 2019（PMID 31390907）— baseline EPA/AA ratio 分層
- Yoshikawa M et al. Circ J 2024（PMID 39261090）— heart failure hospitalization 發生率
  （HR 0.47, 95% CI 0.27–0.81, P<0.005 — 依 abstract，此為 Level 3 證據中一個方向明確的正向訊號，
  可能值得 Wave 2 納入）
- Kawada-Watanabe E et al. J Jpn Coll Cardiol 2017（PMID 27349705）— trial design/rationale
  （背景用，非結果）

**需要**：Research Director 或本角色自行判斷，這些 substudy 是否對 40_SYNTHESIS 的 Level 3
論述有加值（尤其 heart-failure substudy 的正向訊號），若加值則納入 Wave 2 逐一驗證清單。

## Q4 [NEEDS_PI] Sydhom et al. 2024 meta-analysis 的 RCT vs observational 限定詞落差（SOURCE_CONFLICT 候選）

見 `20_EVIDENCE/trials-efficacy/evidence-map.md` Level 2 章節之詳述。摘要：`Tonvasca_2026.md`
（第 53 頁）以此文獻為據，寫「中強度statin+ezetimibe，效益超越高強度statin」，未附加限定詞；
但該文獻 abstract 原文明確區分「observational studies pooled 顯示效益（HR 0.76）」與
「RCT-pooled **未**達統計顯著差異」。

**需要**：Research Director 依 Decision Taxonomy（CLAUDE.md §8）裁決此為
`VERIFIED_NEW_SENSITIVITY`（保留原結論但補上限定詞）、`SOURCE_CONFLICT`（需要 PI 決定投影片
用語是否修正）、或其他分類，並記錄於 `03_DECISION-LOG.md`（本角色無寫入權限，僅在此提出並於
cross-session summary 中一併回報）。

## Q5 [NEEDS_SOURCE] CEPHEUS（citation #20）、DYSIS-II（citation #21）、Masana 2020（citation #25）三篇未能定位逐字相符原文

`02_SOURCE-INVENTORY.md` 中列出的三筆既有引用，本角色多輪嘗試（PubMed 與 Crossref 交叉查詢）
**未能找到與 `Tonvasca_2026.md` 引用字串完全逐字相符**的原始文獻：

- `Chiang CE, et al. J Atheroscler Thromb. 2016;23(5):567-587`（CEPHEUS study）—
  找到的是同一 CEPHEUS-Pan-Asian Taiwan cohort 之另外兩篇分析（Wang KF/Chiang CE，
  J Chin Med Assoc 2014，PMID 24332414 與 24882620），期刊/年份與引用字串不符，可能是
  `Tonvasca_2026.md` 引用了同一資料集的不同分析文章，或引用字串本身有誤植。
- `Gitt AK, et al. Atherosclerosis. 2017;266:158-166`（DYSIS-II study）— 找到多篇 DYSIS-II 相關
  文獻（分屬 Thailand/France/Europe 子分析，散見 Heart Lung Circ、Eur Heart J 摘要、
  Arch Cardiovasc Dis 等），但沒有一篇的期刊/卷/頁與引用字串完全相符。
- `Masana L, et al. Curr Cardiol Rep. 2020;22(8):66`（combination LLT mechanism synergy）—
  找到的是同作者較新的相關文章（Masana L et al. Pharmacol Res 2023;190:106738,
  "Lipid lowering combination therapy: From prevention to atherosclerosis plaque treatment"），
  但年份/期刊與引用字串不符。

**依 Numeric Integrity Rule（CLAUDE.md §9），本角色未對這三筆引用做任何猜測性修正**，維持
`Tonvasca_2026.md` 中的原始引用字串為 `SOURCE_VALUE`，狀態標記為 `FLAG = POSSIBLE_ERROR`，
`ACTION = NEEDS_ANALYST`（Wave 2 以期刊官網或更精確的 PMID 檢索重試）或 `NEEDS_PI`（若 Wave 2
仍找不到，需請 PI 確認原始投影片來源檔案或 Data-on-file 文件）。這三筆引用**目前不應在
`40_SYNTHESIS/` 中被當作已驗證來源引用**。
