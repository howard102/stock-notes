# stock-notes

盤後公開資料整理與個人筆記，以 GitHub Pages 發布的靜態頁面。

- 線上位址：https://howard102.github.io/stock-notes/
- 事實層資料取自證交所、櫃買中心與公開資訊觀測站；判斷層為個人意見，**非投資建議**。
- 所有頁面帶 `robots: noindex,nofollow`；repo 為公開，任何拿到網址的人都讀得到。

## 目錄結構

```
index.html            站台索引
4931/index.html       個股研究卡 — 每檔一個目錄
strategies/           策略研究
  index.html          策略索引
  disposal/index.html 處置股的五個交易日
```

## 頁面慣例

單檔自足 HTML：資料以內嵌 JSON 寫死、圖表由頁面自身 JS 繪製，
唯一外部依賴為 Google Fonts。沒有建置步驟，直接開檔就是最終樣子。

## strategies/disposal 的來源

該頁**不是手寫的**，由 `xq-strategies` 專案的研究管線產生：

```bash
cd ~/projects/xq-strategies
python3 research/disposal/publish_pages.py          # 產生 strategies/ 底下的檔案
python3 research/disposal/publish_pages.py --check  # 只檢查是否已過期
```

原始碼與可重算的 CSV 在 `xq-strategies/research/disposal/`。
**不要直接手改 `strategies/disposal/index.html`** —— 下次重跑會被覆蓋。
