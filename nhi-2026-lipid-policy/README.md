# Taiwan NHI 2026/9/1 降血脂藥物給付新制

獨立於 `research/pitavastatin-ezetimibe-evidence/` 之外的補充資料——此為 Taiwan 全民健康保險署
（NHI）2026/9/1 生效之降血脂藥物給付新制官方文件與臨床實務分析，非透過該研究專案之
Cross-session Research 治理流程（Wave/Gate、specialist 分工、Decision Log）產出，而是直接讀取
官方公告文件後以 workflow（3 個平行 extraction agent + 1 個 synthesis agent）產出，並經人工複核。

## 檔案

- `2026_健保降血脂新制_完整比較與臨床實務建議手冊.md` — **主要產出**：新舊制度完整比較、逐條
  2.6.1/2.6.2/2.6.3 條文對照、187 品項完整藥品給付狀態對照表、詳細臨床實務建議、常見誤解 QA。
- `2026_健保降血脂新制_臨床實務與品項適用詳解.md` — 原始來源文件之一（健保新制概覽）。
- `1150901_擴增statin、ezetimibe或複方之降血脂藥品清單.md` — 官方「擴增」清單（57品項）。
- `1150901_維持原給付規定之statin、ezetimibe或複方之降血脂藥品清單.md` — 官方「維持原給付規定」
  清單（130品項）。
- `附件1-全民健康保險藥品已收載項目異動明細表.md` — 官方支付價格異動明細。
- `附件2_藥品給付規定修訂對照表.md` — 官方 2.6.1/2.6.2/2.6.3 條文修訂對照表。

## 與 pitavastatin-ezetimibe-evidence 專案之關聯

主要產出文件已確認：**Tonvasca（pitavastatin 2mg/ezetimibe 10mg FDC，健保代碼 AC61165100）列於
「擴增」清單**，適用新制表一 ASCVD 風險分級目標導向給付；姊妹產品 LIVAZEBE HD（pitavastatin
4mg/ezetimibe 10mg）則維持舊制。這直接補上該研究專案 `04_OPEN-QUESTIONS.md` 原先標記為「本 run
未查證」之台灣健保給付/自付額資訊缺口——**惟本次補充尚未正式整合進該專案之 `40_SYNTHESIS/`
或治理文件（Decision Log／Open Questions）中，維持為獨立文件，是否要正式整合待 PI 決定。**
