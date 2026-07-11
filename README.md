# 말무리 · 韓語知識圖譜

把韓語單字、文法、句子記成互相連結的知識圖譜,內建 SRS 間隔重複複習、
選擇題測驗、韓語發音朗讀、Excel/CSV 匯入匯出、深淺色主題與亮度調整。
單一 HTML 檔,無後端,資料存在瀏覽器本機。

## 部署到 GitHub Pages(約 5 分鐘)

1. 註冊/登入 [GitHub](https://github.com),點右上角 **+ → New repository**。
2. Repository name 取一個名字(例如 `hangul-graph`),選 **Public**,按 **Create repository**。
3. 在新 repo 頁面點 **uploading an existing file**(或 Add file → Upload files),
   把這個資料夾裡的檔案**全部**拖進去:
   - `index.html`
   - `manifest.webmanifest`
   - `sw.js`
   - `icon-192.png`
   - `icon-512.png`
4. 按下方綠色 **Commit changes**。
5. 進 repo 的 **Settings → Pages**,在 Build and deployment 的 Source 選
   **Deploy from a branch**,Branch 選 **main**、資料夾選 **/(root)**,按 **Save**。
6. 等 1〜2 分鐘,重新整理 Pages 頁面就會出現網址:
   `https://你的帳號.github.io/hangul-graph/`

## 加入 iPhone 主畫面(變成 App)

1. 用 **Safari** 打開上面的網址。
2. 點下方 **分享** 按鈕 → **加入主畫面** → **加入**。
3. 主畫面會出現「말무리」圖示,打開就是全螢幕、沒有網址列的 App,
   而且因為有 Service Worker,**沒有網路也能開啟**。

## 注意事項

- **資料存在哪?** 存在該瀏覽器/該網址的 localStorage 裡。換手機、清除 Safari
  網站資料都會不見,請定期用選單的「匯出備份 (JSON)」保存。
- **拍照 AI 辨識**:GitHub Pages 版本無法連 Claude API 自動辨識,會自動切換成
  「照片對照 + 手動輸入」模式。想用全自動辨識,請在 Claude App 的 artifact 裡使用。
- **Excel 匯入/匯出** 第一次使用需要網路(載入解析元件);CSV 匯入則完全離線可用。
- 更新版本後如果畫面沒變,關掉 App 重開一次即可(Service Worker 會換新快取)。

## 檔案說明

| 檔案 | 用途 |
|---|---|
| `index.html` | 整個 App(HTML/CSS/JS 都在裡面) |
| `manifest.webmanifest` | PWA 設定(名稱、圖示、全螢幕) |
| `sw.js` | Service Worker,提供離線快取 |
| `icon-192.png` / `icon-512.png` | App 圖示 |
