# 1151VIS-HW2-學號-姓名

程式語言熱度動態長條圖（Bar Chart Race），使用 **Vue 3 + D3.js v7** 製作。

## 1. 專案截圖

> 執行後截圖，放進 `images/` 資料夾，並修改下列檔名。

![畫面一：初始畫面](images/screenshot-1.png)
![畫面二：播放中排名變動](images/screenshot-2.png)
![畫面三：鎖定單一語言](images/screenshot-3.png)

## 2. GitHub 連結

https://github.com/你的帳號/1151VIS-HW2-學號-姓名

## 3. YouTube 連結

https://www.youtube.com/watch?v=影片ID

## 4. 製作流程與相關操作

### 4.1 專案概念
以示意資料呈現 2010–2025 年十大程式語言熱度。Vue 管理狀態（年份、播放、速度、鎖定語言），D3 負責 SVG 繪圖與轉場動畫。

### 4.2 技術
| 項目 | 用途 |
|---|---|
| Vue 3（CDN） | 響應式狀態、控制列、資訊文字 |
| D3.js v7（CDN） | `scaleLinear`、`scaleBand`、`selection.join`、`transition` |
| 純 HTML 單檔 | 不需建置，直接開啟即可執行 |

### 4.3 製作流程
1. 在 GitHub 建立 repository：名稱 `1151VIS-HW2-學號-姓名`，Public，`.gitignore` 選 **HTML**。
2. `git clone` 到本機，放入 `index.html` 與 `README.md`。
3. 以 `d3.scaleLinear` 把 4 個關鍵年份（2010/2015/2020/2025）的數值插值成每年資料。
4. 每年排序取前 10 名，`y` 軸用名次（`scaleBand`）決定位置，長條寬度用 `x` 比例尺。
5. 用 `selection.join` 處理進場、更新、離場；以 `transition` 讓長條長度與位置平滑移動，數字用 `tween` 逐步變化。
6. 用 Vue 的 `watch` 監聽 `year`、`picked`，狀態改變就呼叫 D3 重畫。
7. 加入播放／暫停、年份滑桿、速度選單，以及點擊長條鎖定語言。

### 4.4 操作方式
- **播放／暫停**：自動逐年前進，播到 2025 後可重播。
- **滑桿**：拖曳到任一年份。
- **速度**：慢、中、快。
- **點擊長條**：鎖定該語言，其他變淡，下方顯示其排名與數值；再點一次取消。

### 4.5 執行方式
直接用瀏覽器開啟 `index.html`（需要網路載入 Vue 與 D3 的 CDN）。

### 4.6 上傳 GitHub 與共享
```bash
git add .
git commit -m "HW2: Vue + D3 bar chart race"
git push origin main
```
Repository → Settings → Collaborators → Add people → `cchu.fju@gmail.com`

### 4.7 錄影
螢幕錄影 20–60 秒，內容包含：播放動畫、拖曳滑桿、切換速度、點擊鎖定語言。上傳到個人 YouTube 頻道後，把連結貼回第 3 節。

> 資料為課堂練習用示意數字，非官方統計。
