# 50_MANUSCRIPT — 如何閱讀本專案的最終產出

本目錄有三份不同用途的文件，依讀者需求選擇：

| 檔案 | 用途 | 適合誰 |
|---|---|---|
| **`pitavastatin-ezetimibe-final-report.md`** | 一份完整、可從頭讀到尾的最終臨床實證回顧（zh-TW，英文藥名/技術詞保留），已獨立查證、不含研究過程雜訊（無 Decision 編號、無 git hash、無角色名稱） | 想完整了解全案結論與限制的讀者 |
| **`pitavastatin-ezetimibe-slides-deck.md`** | 實際可渲染的簡報投影片（Marp 格式：`marp: true` frontmatter + `---`分頁），約 16 頁，含講者註 | 需要製作/使用簡報者——可用 VSCode Marp 外掛、`marp-cli`、或線上 Marp 工具直接轉成 PDF/PPTX/HTML |
| `pitavastatin-ezetimibe-positioning-slides.md` | 較早期的簡報大綱草稿（保留作為過程紀錄與方法論註記，非最終渲染格式） | 想了解簡報內容如何逐步修正定案者 |

**若只想讀一份文件**：讀 `pitavastatin-ezetimibe-final-report.md`。
**若要做簡報**：用 `pitavastatin-ezetimibe-slides-deck.md`。

上述兩份最終文件由 workflow（草擬 + 獨立查證兩階段，共 4 個 subagent）產出：草擬階段各自基於
`../40_SYNTHESIS/`、`../20_EVIDENCE/`三角色證據檔獨立撰寫；查證階段由另一組 agent 重新對照原始
證據檔案逐項核對（未直接信任草稿），修正遺漏或錯誤後才定案。詳見
`../03_DECISION-LOG.md`（最後一筆決策記錄本次 workflow 產出）。

**完整研究過程與逐項可溯源證據**（若需要查核任何一個數字/COR-LOE 分級/引用出處的原始依據）：
`../40_SYNTHESIS/00_executive-synthesis.md`（整合版 zh-TW 實證簡報，含較多過程性註記）、
`../40_SYNTHESIS/01_attack-defense.md`、`../40_SYNTHESIS/02_evidence-traceability-table.md`、
`../20_EVIDENCE/<guideline-risk|trials-efficacy|safety-pharmacology>/`（各角色原始查證檔案）、
`../03_DECISION-LOG.md`（全部決策與兩輪 Final-Gate-後修正之完整記錄）。
