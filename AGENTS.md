# AGENTS.md — 台灣饒舌文化深度考據知識庫 (Taiwan Hip-Hop LLM Wiki)

本文件是本知識庫的「憲章與架構規範（The Schema）」，規範 LLM Agent 如何維護、調研、編譯與查詢本專案中的台灣饒舌文化知識。
本系統基於 **Karpathy LLM Wiki** 典範建構，專注於**「台灣饒舌音樂、歌手、製作人、廠牌與歷史文化演進」**之深度歷史與文化考據。

---

## 核心哲學 (Core Philosophy)

1. **編譯優於檢索 (Compile, Don't Just Retrieve)**：
   知識庫不是單純的文件堆疊或動態 RAG，而是一座**持久、具複合積累性 (Compounding Artifact) 的網狀知識體系**。每次讀入新文獻，Agent 負責將新事實編譯更新至既有實體、時代、概念頁面中，保持全庫最新與相互關聯。
2. **客觀考據與歷史多重視角 (Rigorous Historical Scholarliness)**：
   台饒歷史充滿地下與主流激盪、廠牌合縱連橫、歷史 Beef 與世代風格轉向。所有論述必須有文獻佐證（來源引自 `raw/` 中的原始資料），遇到爭議觀點時記錄各方說法與時代脈絡，不做單一主觀評判。
3. **通用相容的超連結 (Universal Markdown Linking)**：
   本 Wiki 不依賴特定筆記軟體（如 Obsidian 專屬語法），一律採用**標準 Markdown 相對連結**（如 `[熱狗](../entities/MC_HotDog.md)`），確保在 VS Code、GitHub 及任何預覽器中皆能原生點擊導覽。
4. **零骨架自生長 (Zero-Stub Organic Growth)**：
   不預先建立缺乏實質內容的空殼頁面（No empty stubs）。知識庫從第一篇原始文獻匯入開始，逐步開枝散葉、有機長成。

---

## 系統三層架構 (Three-Layer Architecture)

```
LLMWiki專案黑屋for_10th/
├── raw/                 # 【層級一：原始來源庫】唯讀、不可竄改、不可抹除，調研產生的原始文獻
├── wiki/                # 【層級二：LLM 編譯知識庫】由 Agent 撰寫與更新之 Markdown 知識頁面
│   ├── entities/        # 饒舌歌手 (MC)、製作人 (Beatmaker/Producer)、DJ、廠牌主理人
│   ├── crews/           # 廠牌 (Labels)、廠牌同盟、音樂團隊 (Crews)
│   ├── eras/            # 歷史時期與編年史（如：萌芽期、地下黃金年代、金曲串流期、大嘻哈世代）
│   ├── concepts/        # 技術術語、押韻美學、文化現象（如：Flow、雙押、台語韻腳、Cypher、Beef）
│   ├── works/           # 里程碑專輯、經典單曲、代表性 Cypher / Battle 錄音
│   ├── events/          # 指標賽事、文化事件（如：《大嘻哈時代》、Diss 戰事、金曲獎里程碑）
│   └── synthesis/       # 深度跨維度研究、風格演變對比、文化專題論述
├── index.md             # 全庫分類導覽與條目總目錄（每次 Ingest 自動同步更新）
├── log.md               # 時間順序之操作日誌（Ingest、Query Synthesis、Lint 紀錄）
└── AGENTS.md            # 本規範手冊
```

---

## 核心操作流程 (Workflows)

### 流程一：調研與原始來源採集 (Research & Sourcing)
當使用者提出考據主題或提問尚未涵蓋的領域時，Agent 負責網路檢索並固化原始文獻：
1. **嚴選資料來源**：優先檢索具公信力之專題報導（如《Blow 吹音樂》、《BIOS monthly》、《GQ Taiwan》人物專訪、《關鍵評論網》、嘻哈龍虎門專訪、學術論文、深度 Podcast/節目逐字紀錄）。
2. **建立原始文獻**：在 `raw/` 建立以日期與主題命名之檔案（例如 `raw/20261118_kaoinc_early_history.md`）。
3. **文獻必備規格**：
   - 來源網址 (Source URL) 與 採集日期。
   - 原作者/訪談者、受訪對象、發佈日期。
   - 原文摘要與關鍵引言（保持原始陳述，不竄改）。

### 流程二：知識編譯與匯入 (Ingest)
當 `raw/` 存入新文獻後，Agent 執行嚴謹的知識編譯：
1. **深入研讀**：通讀 raw 文獻，萃取涉及之「人物、廠牌、時代事件、關鍵作品、技法概念」。
2. **跨頁更新與創建**：
   - 若提及之實體尚無頁面，建立該頁面，並填寫規範之 YAML Frontmatter。
   - 若已有頁面，依據新資訊補充內容（例如歌手新增經歷、音樂風格轉變、歷史訪談證言），並註明出處。
   - 建立相互參照的標準相對路徑連結。
3. **更新總目錄**：在 `index.md` 對應分類下加入新頁面條目與一句話精準摘要。
4. **登記日誌**：在 `log.md` 追寫一筆記錄（格式：`## [YYYY-MM-DD] ingest | 文獻名稱`）。

### 流程三：深度查詢與論述沉澱 (Query & Synthesis)
1. 使用者提問時，Agent 優先檢索 `index.md` 與 `wiki/` 既有條目進行整合論述。
2. **研究沉澱**：若回答產出具有長遠參考價值的「跨時代演進分析」、「派系/風格深度對比」、「押韻文本解構」，Agent 應主動將該論述整理成專題，存入 `wiki/synthesis/`，並反向連結至相關頁面。

### 流程四：庫況審查與健康檢查 (Lint & Audit)
定期或依使用者指令執行審查：
- **懸空參照 (Broken/Red Links)**：檢查是否有頁面連結到尚未建立的頁面，評估是否需立項調研。
- **史實矛盾 (Contradictions)**：檢視不同來源是否對同一歷史事件（如年代、Beef 起因）有出入，並於頁面中並列說明。
- **孤島頁面 (Orphans)**：確認每個頁面皆有被其他頁面或 `index.md` 正確引用。

---

## 頁面格式規範 (Page Conventions)

### 1. YAML Frontmatter 格式
每個在 `wiki/` 下建立的頁面均須具備標準頭部：

```markdown
---
title: 頁面中文全名 (例如: 蛋堡 Soft Lipa)
category: entities | crews | eras | concepts | works | events | synthesis
aliases: [杜振熙, Soft Lipa]
tags: [饒舌歌手, 爵士嘻哈, 顏社]
created: YYYY-MM-DD
updated: YYYY-MM-DD
sources:
  - raw/20261118_kaoinc_early_history.md
---
```

### 2. 內文結構規範
- **定義與簡介**：精準概括其歷史地位與核心特徵（2-3 句話）。
- **歷史演進與脈絡**：按照時間順序或生涯階段詳實記載。
- **代表作品 / 經典戰役 / 關鍵貢獻**：列舉作品並附上連結與解析。
- **文化考據與爭議/各方觀點**：客觀陳述爭議或演變過程。
- **關聯條目 (References & Cross-links)**：以標準 Markdown 連結列出關聯人物、廠牌、概念。
- **文獻來源 (Footnotes/Sources)**：明確標註引用之 raw 檔案。

---

## 語言與考據準則 (Scholarly & Cultural Tone)

- **深諳文化黑話但不流於俗套**：準確理解並運用台饒術語（如：Punchline、Flow 變奏、雙押/排押、Cypher、Battle、Real、Beef、OG、校長、學院派），解說需深入且具文化尊重。
- **嚴謹考證**：對重要作品發行年份、金曲/金音獲獎紀錄、節目賽事勝負等客觀數據務求精確，不憑空臆測。
