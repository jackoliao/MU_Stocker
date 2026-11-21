# MU 看盤終端

美光（Micron, MU）單頁看盤工具，純前端，部署在 GitHub Pages。

## 架構（為什麼能在公開網路上抓到資料）
- **Binance 即時看盤**（K 線、委託簿、成交、大戶多空比）：瀏覽器直接連 Binance，秒級更新。
- **現股報價、日 K、內部人 Form 4、13F 法人、分析師共識、公司買回**：瀏覽器直連常被 CORS 擋住，所以由 GitHub Actions（`.github/workflows/update-data.yml`）每約 10 分鐘在伺服器端抓取公開資料，寫入 `data/data.json`；頁面讀取這份資料，同時也會先嘗試直連與公開代理，失敗才用雲端資料。

## 部署
1. 建立公開 repository，上傳 `index.html`、`README.md`。
2. 在 repository 用 Add file → Create new file，檔名輸入 `.github/workflows/update-data.yml`，貼上同名檔案內容並 Commit。
3. Settings → Actions → General → Workflow permissions 選 **Read and write permissions**，Save。
4. Actions → update-data → Run workflow（第一次手動執行，之後每 10 分鐘自動）。
5. Settings → Pages → Deploy from a branch → `main` / `(root)`。

## 限制
- 雲端資料約每 10 分鐘更新（GitHub 排程可能延遲），非逐秒。
- Nasdaq.com、Yahoo 可能封鎖 GitHub 的伺服器 IP，Actions 日誌會顯示失敗項目，頁面狀態列也會標示。
- 13F 為季報；MUUSDT 為 Binance 合約價，與現股有價差。僅供參考，不構成投資建議。
