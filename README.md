# stock-notes

盤後公開資料整理與個人筆記，以 GitHub Pages 發布的靜態頁面。

- 線上位址：https://howard102.github.io/stock-notes/
- 事實層資料取自證交所、櫃買中心與公開資訊觀測站；判斷層為個人意見，**非投資建議**。
- 所有頁面帶 `robots: noindex,nofollow`；repo 為公開，任何拿到網址的人都讀得到。

## 目錄結構

```
index.html            站台索引
4931/index.html       個股研究卡互動版 — 每檔一個目錄
4931/static.html      個股研究卡純靜態匯入版
journal/              每日筆記
  index.html          日期索引
  2026-09-09/index.html 每日筆記 — 保留原文段落與導覽
strategies/           策略研究
  index.html          策略索引
  disposal/index.html 處置股的五個交易日
```

## 頁面慣例

沒有建置步驟，直接開啟 HTML 就是最終樣子。

`4931/index.html` 是互動閱讀版：五張圖表由 JavaScript 繪製，提供滑鼠 tooltip、
浮動章節導覽、回到頂端按鈕，以及跟隨系統／淺色／深色三態主題切換。
`4931/static.html` 是給 WINWIN 等文章平台匯入的純靜態版，圖表直接內嵌 SVG，
不依賴 JavaScript。`4931/chart-data.json` 是互動圖表的資料正本；資料更新時，
`index.html`、`static.html` 與圖表資料必須同步，避免網站與平台快照顯示不同內容。
其他頁面維持各自的呈現方式。

WINWIN 等文章平台保存的是匯入快照。更新 GitHub Pages 後，仍須在平台重新匯入
`4931/static.html`，既有文章不會因來源檔更新而自動同步。

## strategies/disposal 的來源

該頁**不是手寫的**，由 `xq-strategies` 專案的研究管線產生：

```bash
cd ~/projects/xq-strategies
python3 research/disposal/publish_pages.py          # 產生 strategies/ 底下的檔案
python3 research/disposal/publish_pages.py --check  # 只檢查是否已過期
```

原始碼與可重算的 CSV 在 `xq-strategies/research/disposal/`。
**不要直接手改 `strategies/disposal/index.html`** —— 下次重跑會被覆蓋。

## 每日筆記

`journal/` 為每日筆記的靜態閱讀版，依日期建立目錄。保留原文的標題順序、清單、表格及螢光標記，提供段落導覽與右下角回到頂端。閱讀頁採固定暖白紙張與深褐文字配色。Obsidian Base 查詢區塊、YAML 管理欄位及隱藏註解不呈現在閱讀版。此頁為來源筆記的單次快照，後續編輯原文不會自動同步。
