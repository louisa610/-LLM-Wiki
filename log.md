# 操作與變更日誌 (Log)

本檔案為 append-only 格式之時間順序日誌，記錄知識庫之重要操作（文獻匯入 Ingest、專題研究 Synthesis、庫況稽核 Lint）。

---

## [2026-11-17] init | 台灣饒舌文化深度考據知識庫初始化
- 確立知識庫範圍：深度歷史與文化考據向，聚焦饒舌音樂、歌手、製作人、廠牌與作品。
- 確立技術方案：遵循 Karpathy LLM Wiki 架構，採用通用標準 Markdown 相對路徑導覽，由 Agent 負責網路調研採集原始資料並進行知識編譯。
- 完成 `AGENTS.md` 規範制定、目錄樹建立與 `index.md` 初始化。

## [2026-11-18] ingest | 顏社 KAO!INC. 創立與蛋堡爵士嘻哈（輕饒舌）風潮考據
- 原始文獻：`raw/20261118_kaoinc_and_jazz_hiphop.md`
- 建立實體頁面：`wiki/entities/Soft_Lipa.md` (蛋堡)、`wiki/entities/Dela_Fat.md` (迪拉胖)
- 建立廠牌頁面：`wiki/crews/KAO_INC.md` (顏社)
- 建立時代頁面：`wiki/eras/Underground_Golden_Era.md` (地下黃金年代與獨立萌芽期)
- 建立概念頁面：`wiki/concepts/Jazz_Hip_Hop.md` (爵士嘻哈與輕饒舌)
- 建立作品頁面：`wiki/works/Shou_Lian_Shui.md` (《收斂水》)、`wiki/works/Moonlight_Jabberloop.md` (《月光》)
- 同步更新：`index.md`

## [2026-11-18] ingest | 台灣早期饒舌風格論戰（學院派 vs 街頭派）與經典 Beef / Diss 事件考據
- 原始文獻：`raw/20261118_academic_vs_street_and_early_beefs.md`
- 建立實體頁面：`wiki/entities/TriPoets.md` (參劈)、`wiki/entities/MJ116.md` (頑童MJ116)
- 建立概念頁面：`wiki/concepts/Academic_School.md` (學院派 vs 街頭派)、`wiki/concepts/Beef_and_Diss.md` (Beef 與 Diss 文化)
- 建立作品頁面：`wiki/works/Rhyme_Beginning.md` (《押韻的開始》)、`wiki/works/30CM_Diss.md` (〈30CM〉)
- 建立事件頁面：`wiki/events/2008_The_Wall_Assault.md` (2008年 The Wall 參劈遭襲擊事件)、`wiki/events/2011_30CM_Beef_War.md` (2011年 頑童〈30CM〉Beef 大戰)
- 增修關聯：`wiki/eras/Underground_Golden_Era.md`
- 同步更新：`index.md`

## [2026-11-18] synthesis | 2000年代台灣饒舌的分流與碰撞：從學院派文字格律、街頭派衝擊到顏社爵士生活美學
- 深度論述產出：`wiki/synthesis/2000s_Taiwan_HipHop_Bifurcation.md`
- 橫向貫通「學院派雙押」、「街頭派衝突邊界與網路迷因」與「顏社爵士生活美學」三大歷史支柱，完成三足鼎立之跨維度歷史總結。
- 同步更新：`index.md`

## [2026-11-18] presentation | 台灣饒舌文化深度考據互動式投影片編譯完成
- 產出檔案：`taiwan_hiphop_slides.html`
- 遵循 Graph 流程：
  - Stage 1：完成 12 頁大綱架構規劃與 Human Gate 審查確認。
  - Stage 2：自動執行逐頁內容精寫與防爆版四重檢查（字數控制於 120-180 字、三卡片/矩陣排版、史實校核）。
  - Stage 3：自動編譯為自適應 16:9 深色街頭美學 HTML 單檔簡報，支援鍵盤左右鍵、Space、全螢幕與進度條切換。
- 核心焦點貫穿：第一單元顏社與爵士嘻哈（3 頁）、第二單元學院派雙押與 Beef 戰役底線（3 頁）、第三單元大嘻哈世代交替（3 頁），結構厚重完整。

## [2026-11-18] ingest | 2020年代《大嘻哈時代》世代交替與新星崛起考據
- 原始文獻：`raw/20261118_the_rappers_generation_shift.md`
- 補充與完善文獻庫：將前述兩篇原始文獻庫升級附帶完整媒體專訪網址、影音檢索連結與查核管道。
- 同步更新：`index.md`
