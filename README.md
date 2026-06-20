# 釜山9日自由行 🏖️

> 2026/06/26 – 07/04｜9 天 8 夜釜山自由行 Web App

## 簡介

這是一個以**單頁 HTML** 打造的旅行行程管理工具，專為「釜山 9 日自由行」設計。整個應用程式僅靠一個 `index.html` 即可運行，無需後端伺服器。

提供行程規劃、旅費記帳、行李清單等一站式旅遊管理功能，支援**本地資料持久化**（localStorage），離線也能使用。

## 功能模組

| 模組 | 說明 |
|------|------|
| **行程** (Plan) | 9 天逐日行程時間軸，含航班資訊、Google Maps/Naver 導航連結、地址複製 |
| **記帳** (Wallet) | 韓幣消費記錄、匯率換算（KRW → TWD）、算式計算機 |
| **清單** (Lists) | 旅遊行李 & 購物清單打勾，支援自訂項目新增、長按刪除、個人備忘錄 |

## 技術棧

- **HTML5** — 單頁應用 (SPA)
- **Tailwind CSS** (CDN) — 響應式 UI 樣式
- **Font Awesome 6** (CDN) — 圖示
- **Google Fonts** — Zen Maru Gothic + Noto Sans TC
- **Vanilla JavaScript** — 路由、狀態管理、DOM 操作
- **localStorage** — 本地端持久化（匯率、消費紀錄、清單勾選、自訂項目）

## 行程概覽

| 天數 | 日期 | 星期 | 重點 |
|------|------|------|------|
| D1 | 06/26 | Fri | 抵達釜山、入住廣安里 Airbnb |
| D2 | 06/27 | Sat | 廣安里海灘散步 |
| D3 | 06/28 | Sun | 景點自由遊覽 |
| D4 | 06/29 | Mon | 景點自由遊覽 |
| D5 | 06/30 | Tue | 景點自由遊覽 |
| D6 | 07/01 | Wed | 景點自由遊覽 |
| D7 | 07/02 | Thu | 景點自由遊覽 |
| D8 | 07/03 | Fri | 最後購物與遊覽 |
| D9 | 07/04 | Sat | 返回台灣 |

## 使用方式

直接在瀏覽器中開啟 `index.html` 即可使用，建議以手機瀏覽並加入主畫面以獲得最佳體驗。

### 快速開始

1. **複製檔案**到本地
2. **雙擊 index.html** 或以瀏覽器開啟
3. **點選「行程」頁籤**查看詳細行程
4. **點選「記帳」頁籤**追蹤旅費開支
5. **點選「清單」頁籤**勾選行李與購物清單

## 專案結構

```
Busan-202606/
├── index.html                          # 主程式（含 HTML、CSS、JS）
├── README.md                           # 本文件
└── .git/
```

---

## 提示詞範本（以 index.html 為範本新增/修改旅遊行程）

以下提示詞可直接複製使用，請將 `{...}` 內容替換為你的實際資料。

---

### 一、以範本為基礎建立全新旅遊行程

```
請以 Busan-202606/index.html 為範本，在 {目標資料夾} 建立一個新的 index.html 旅遊行程頁面。
以下是新行程的資訊，請替換 tripData 中的所有資料：

旅遊主題： {例如：沖繩親子之旅 🌺}
英文副標： {例如：Okinawa Family Trip}
Header 圖示： {例如：fa-umbrella-beach}

航班資訊：
- 去程：{日期} / {航班編號} / {出發地} {時間} ➝ {目的地} {時間}
- 回程：{日期} / {航班編號} / {出發地} {時間} ➝ {目的地} {時間}

行程天數與日期：
- D1: {MM/DD} ({星期})
- D2: {MM/DD} ({星期})
- ...以此類推

每日行程明細（依以下格式填寫）：
D1:
- {時間} | {標題} | {描述} | 類型: {transport/flight/arrival/car/food/hotel/play/shop} | 連結: {URL或留空} | 是否重點: {是/否}
- ...

D2:
- ...

行李清單：
- {項目1}
- {項目2}
- {項目3}
...

其他自訂清單（可選）：
清單名稱：{例如：購物清單}
圖示：{例如：fa-bag-shopping}
顏色：{例如：text-pink-500}
項目：
- {項目1}
- {項目2}
...

主題色（可選）： 若不指定則沿用藍色海洋風，也可改為 {例如：紫色優雅風}
localStorage key prefix： {例如：busan0704}（避免與其他行程衝突）
```

---

### 二、在現有行程中新增/修改天數

```
請修改 {檔案路徑}/index.html，在行程中新增一天 D{X}（日期 {MM/DD}，星期{X}），插入在 D{Y} 與 D{Z} 之間。

這天的行程如下：
- {時間} | {標題} | {描述} | 類型: {type} | 連結: {URL或留空} | 重點: {是/否}
- {時間} | {標題} | ...

請同時更新 tripData.days 陣列的 key、date、week，以及 tripData.itinerary 中對應的資料。
```

---

### 三、修改某一天的行程內容

```
請修改 {檔案路徑}/index.html 中 D{X}（{日期}）的行程：
- 將「{原標題}」的時間從 {原時間} 改為 {新時間}
- 將「{原標題}」的描述改為「{新描述}」
- 在「{某項目}」之後新增一個行程：{時間} | {標題} | {描述} | 類型: {type} | 連結: {URL}
- 刪除「{某標題}」這個項目
```

---

### 四、新增/修改行李清單或購物清單

```
請修改 {檔案路徑}/index.html 的清單（Lists Module）：
- 在 tripData.checklist.luggage.items 中新增/刪除項目：
  - 新增項目: {項目名稱}
  - 刪除項目: {項目名稱}

或新增一個全新清單類別：
- key: {英文key}
- title: {清單名稱}
- icon: {FontAwesome class，如 fa-utensils}
- color: {Tailwind 顏色 class，如 text-blue-500}
- items: [{項目1}, {項目2}, ...]
```

---

### 五、修改主題配色

```
請修改 {檔案路徑}/index.html 的主題配色，從目前的藍色海洋風格改為 {例如：紫色優雅風}：
- ocean-blue: {新色碼，如 #7c3aed}
- ocean-light: {新淺色背景，如 #f3e8ff}
- Header 圖示改為: {新 FontAwesome icon，如 fa-crown}
- 頁面標題改為: {新標題}
```

---

### 六、修改航班資訊

```
請修改 {檔案路徑}/index.html 中的航班資訊：
- 去程航班：{日期} / {航班編號} / {出發地} {時間} ➝ {目的地} {時間}
- 回程航班：{日期} / {航班編號} / {出發地} {時間} ➝ {目的地} {時間}

請同時更新 tripData.flights 陣列中的 date、code、route。
```

---

### 附錄：type 類型對照表

| 欄位 | type 值 | 對應圖示 |
|------|---------|---------|
| 交通接送 | `transport` | 🚗 fa-car-side |
| 起飛 | `flight` | ✈️ fa-plane-departure |
| 抵達 | `arrival` | 🛬 fa-plane-arrival |
| 租/還車 | `car` | 🔑 fa-key |
| 餐飲 | `food` | 🍴 fa-utensils |
| 住宿 | `hotel` | 🛏 fa-bed |
| 景點/樂園 | `play` | 🎫 fa-ticket |
| 購物 | `shop` | 🛍 fa-bag-shopping |

---

## localStorage 數據結構

應用程式會自動儲存以下數據（可同時管理多個旅程，使用不同的 key prefix 區分）：

| Key | 用途 |
|-----|------|
| `{prefix}_rate` | 匯率（KRW → TWD） |
| `{prefix}_expenses` | 消費紀錄陣列 |
| `{prefix}_checklist` | 清單勾選狀態 |
| `{prefix}_custom_items` | 自訂清單項目 |
| `{prefix}_deleted_items` | 已刪除的項目 |
| `{prefix}_current_selection` | 目前選中的行程卡片 |

**預設 prefix：** `busan0704`

---

## 常見問題

### Q: 如何修改匯率？
A: 在「記帳」頁籤的藍色框框中輸入新的匯率，會自動儲存。

### Q: 如何清空所有資料？
A: 開啟瀏覽器的開發者工具 (F12)，進入 Console，執行：
```javascript
localStorage.clear();
location.reload();
```

### Q: 如何備份資料？
A: 在 Console 執行以下指令，複製輸出結果保存：
```javascript
console.log(JSON.stringify(localStorage));
```

### Q: 可以在桌面端使用嗎？
A: 可以，但建議以手機瀏覽獲得最佳體驗（介面針對手機寬度設計）。

---

## 授權

本專案為個人旅遊用途，非公開發行。
