# 旅旅醬 Lü-Lü — 智慧旅遊規劃展示版

以 React + Vite 建立的繁體中文互動式旅遊規劃網站，可免費部署至 GitHub Pages。

## 功能
- 設定目的地、日期、天數、人數、每人預算、交通方式與旅行步調
- 景點願望清單與同行者偏好記錄
- 收藏社群與旅遊網址、選擇本機照片（只顯示檔名）
- 規則式行程產生（每天 2、3 或 4 個景點）
- 編輯行程時間、名稱、備註、預估費用及新增／刪除活動
- 每人預算試算、複製行程、下載 TXT
- localStorage 本機儲存（不跨裝置同步）

**重要：** 這是規則式展示版，沒有串接生成式 AI、即時地圖、社群平台、餐廳資料或影音生成服務。旅遊費用與用餐內容為示範估算，交通與營業時間需另行確認。旅伴偏好只做記錄，尚未實作偏好最佳化。

## 本機啟動

需要 Node.js 20.19+ 或 22.12+（建議 Node.js 22）。

```bash
npm install
npm run dev
```

瀏覽終端機顯示的網址（通常是 http://localhost:5173）。

## 編譯測試

```bash
npm run build
npm run preview
```

## GitHub Pages 部署

1. 註冊或登入 GitHub，建立一個公開儲存庫，例如 `lulu-travel`，不要勾選自動建立 README。
2. 在專案資料夾執行：

```bash
git init
git add .
git commit -m "Initial Lü-Lü travel planner"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/lulu-travel.git
git push -u origin main
```

3. 把 `YOUR_USERNAME` 改成自己的 GitHub 帳號。如果儲存庫名稱不同，也請修改 URL。
4. 到 GitHub 儲存庫的 **Settings → Pages → Build and deployment**，將 **Source** 設為 **GitHub Actions**。
5. 到 **Actions** 查看 `Deploy to GitHub Pages` 是否成功（若首次沒有執行，可按 `Run workflow`）。
6. 完成後網站網址通常是 `https://YOUR_USERNAME.github.io/lulu-travel/`。部署可能需要幾分鐘。

專案使用 Vite 的 `base: './'`，可適應 GitHub Pages 專案子路徑。

## 專案結構

```text
lulu-travel/
├── .github/workflows/deploy.yml
├── .gitignore
├── index.html
├── package.json
├── vite.config.js
├── README.md
└── src/
    ├── main.jsx
    ├── App.jsx
    └── style.css
```

## 隱私與安全
- 資料只儲存在目前瀏覽器的 localStorage；共用電腦請自行清除資料。
- 不要把 API 金鑰寫入前端程式碼或提交到 GitHub。
- 網址收藏只允許 http/https 連結；使用者點擊後會開啟外部網站。
- 字型由 Google Fonts 載入；離線時會使用系統字型。

## 後續擴充方向
加入地理編碼／路線 API、即時景點資訊、安全的 AI 後端、多人共用資料庫、社群媒體授權串接，以及行程介紹影片製作。
