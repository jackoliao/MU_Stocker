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
