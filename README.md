# MU 看盤終端

美光（Micron, MU）單頁看盤工具，純前端、單一 `index.html`，無需後端或建置。

## 功能
- **即時看盤**：Binance MUUSDT 永續合約 K 線（1s～1d）、委託簿、最新成交、標記價、資金費率；手機可單指滑動、雙指縮放。
- **現股報價**：多來源抓取 MU 報價，每 30 秒自動更新，可手動更新；可選填 Finnhub 免費金鑰（只存在你自己的瀏覽器）。
- **內部人交易**：高層／董事賣出明細（SEC Form 4 整理）。
- **機構與大戶**：13F 法人買賣變動、Binance 大戶多空比、大單成交。
- **券商評等**：目標價與評等。

## 部署（GitHub Pages）
1. 建立公開 repository，上傳 `index.html` 與 `README.md`。
2. Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)` → Save。
3. 約 1 分鐘後網址：`https://<你的帳號>.github.io/<repo 名稱>/`

## 資料與限制
- 內部人、機構、券商資料為 2026-11-07 整理的靜態快照，不會自動更新，請以 SEC EDGAR 為準。
- 部分地區或網路無法連線 Binance；瀏覽器可能擋掉部分現股報價來源。
- MUUSDT 為 Binance 合約價格，與 NASDAQ 現股價可能有價差。
- 僅供參考，不構成投資建議。

## 即時更新範圍
- 每個分頁頂端都有狀態列與「⟳ 更新此頁」按鈕；頁面每 30 秒自動更新，也可按「全部更新」。
- 不需任何金鑰：Binance 看盤與大戶指標、現股報價與日 K（Yahoo / CNBC / Stooq 多來源）、Nasdaq.com 公開資料（Form 4 內部人買賣、13F 法人持股增減、分析師共識目標價）。
- 若瀏覽器或網路擋掉上述來源，狀態列會標示失敗，並顯示 2026-11-13 整理的快照。
- 選用：可在頁面設定免費 Finnhub 金鑰作為現股報價與 Form 4 的備援，金鑰只存在使用者自己的瀏覽器。
