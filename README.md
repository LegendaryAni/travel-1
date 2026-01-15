# 🗺️ 中山劍潭精準行程 (Trip Planner)

> **Ver 15.1 Romantic Edition**

這是一個專為「中山站文藝漫步」與「劍潭山追夕陽」設計的一日遊精準行程網頁應用程式 (Web App)。採用極輕量的單一檔案架構，無需後端，旨在提供優雅、流暢且資訊豐富的旅遊導覽體驗。

![Project Preview](https://img.shields.io/badge/Style-Romantic_Glass-ffc1cc?style=for-the-badge) ![Tech](https://img.shields.io/badge/Tech-HTML_Tailwind_JS-blue?style=for-the-badge)

## ✨ 特色功能

* **📱 響應式設計 (Mobile First)**
    * 針對手機體驗優化，搭載 **底部導覽列 (Bottom Tab Bar)**，單手即可切換分頁。
    * 電腦版自動切換為頂部選單，視覺寬敞舒適。
* **🎨 浪漫夕陽風格 UI**
    * 採用 `Playfair Display` 襯線字體與 `Noto Sans TC`，營造雜誌般的高級質感。
    * **磨砂玻璃特效 (Glassmorphism)** 與玫瑰金/晨曦漸層背景。
* **☀️/🌧️ 晴雨天模式切換**
    * 內建邏輯判斷，一鍵切換模式。
    * 雨天時自動隱藏戶外登山行程，並替換為室內備案（如美術館）。
* **🗺️ 智能導航整合**
    * 所有行程卡片、景點與備案皆內嵌 **Google Maps 搜尋連結**，點擊即導航。
* **📋 一鍵複製行程**
    * 內建剪貼簿功能，將複雜的網頁行程轉換為簡潔的文字列表，方便傳送至 Line 或 Notes。
* **🎒 互動式檢查清單**
    * 出發前裝備確認（現金、悠遊卡、水），支援點擊勾選互動。

## 🛠️ 技術棧 (Tech Stack)

本專案堅持 **Zero-Dependency** (無依賴) 哲學，無需 `npm install` 或編譯步驟：

* **HTML5**: 語意化標籤結構。
* **Tailwind CSS (CDN)**: 使用 CDN 引入，實現快速切版、RWD 與現代化樣式。
* **JavaScript (Vanilla ES6+)**: 
    * DOM 操作與動態渲染 (Rendering)。
    * `IntersectionObserver` API 實現滾動視差與淡入動畫 (Reveal Animation)。
* **Google Fonts**: 引入 Web Fonts 提升閱讀體驗。

## 🚀 如何使用 (Quick Start)

### 方法一：直接開啟
1. 下載本專案的 `index.html` 檔案。
2. 雙擊檔案，使用 Chrome、Safari 或 Edge 瀏覽器開啟即可瀏覽。

### 方法二：部署至 GitHub Pages (推薦)
1. 將 `index.html` 上傳至你的 GitHub Repository。
2. 進入 **Settings** > **Pages**。
3. 在 **Build and deployment** 下方將 Branch 設定為 `main` (或 master) 並儲存。
4. 等待約 1 分鐘，即可獲得專屬網址分享給朋友。

## ⚙️ 如何客製化行程

所有資料皆以 JSON 格式儲存於 `index.html` 底部的 `<script>` 區塊中，你可以輕易修改：

1.  **修改行程時間與地點**：編輯 `itineraryData` 陣列。
    * 支援 `type: 'hard'` (硬時點)、`mode: 'sunny'` (僅晴天顯示) 等參數。
2.  **修改推薦景點**：編輯 `spotsData` 陣列。
3.  **修改口袋名單**：編輯 `extrasData` 物件。

```javascript
// 範例：修改一個行程
{ 
  start: "11:00", 
  end: "11:10", 
  title: "集合地點", 
  loc: "中山站4號出口", 
  type: "prep", 
  action: "等人、買水", 
  rule: "準時勿遲到", 
  link: "Google地圖關鍵字" 
}
