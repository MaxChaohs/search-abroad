# 跨國搜尋比較台 · Search Terminal

輸入一個關鍵字,一次比較不同國家的人搜同一個字會看到什麼。純前端、單一 HTML,無需後端。

## 這是什麼

同樣搜「珍珠奶茶」,台灣、美國、日本跳出來的結果天差地遠。這個小工具幫你把帶有正確國家參數的 Google 搜尋網址組好,一鍵在新分頁打開各國視角。

- 內建 20 個國家,語言參數(`hl`)依國家自動帶好
- 可勾選多國、一鍵全開
- 選項:關閉個人化結果(`pws=0`),拿到較乾淨的基準

## 使用小技巧

- **搭配無痕視窗**:避免自己的搜尋紀錄影響結果。
- **關鍵字要換成當地人用的詞**:`gl`/`hl` 不會翻譯你的查詢。想看美國人的視角,要搜 `bubble tea` 而不是「珍珠奶茶」,否則結果會跟你原本的幾乎一樣。
- **限制**:`gl` 只調整「以哪國為主」,不會真的把你變成在當地。地圖、附近店家這類高度在地化的結果仍可能露出你實際所在地,要完全擬真需搭配該國 VPN。

## 本機執行

直接用瀏覽器打開 `index.html` 就能用,不需安裝任何東西。

或用靜態伺服器:

```bash
npm install
npm start
```

## 部署到 Railway

專案已附 `package.json`,用 `serve` 監聽 Railway 給的 `$PORT`。

**方式一:Railway CLI**

```bash
npm i -g @railway/cli
railway login
railway init
railway up
railway domain
```

**方式二:接 GitHub**

把本 repo 推上 GitHub → Railway → New Project → Deploy from GitHub repo → 選此 repo。之後每次 push 會自動重新部署。部署完到 Settings → Networking → Generate Domain 拿公開網址。

## 檔案結構

```
.
├── index.html      # 工具本體(所有 HTML/CSS/JS 都在這)
├── package.json    # 部署用,serve 監聽 $PORT
└── README.md
```
