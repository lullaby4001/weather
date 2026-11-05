# weather
# 🌤 溫度 · 濕度預測網站

一個純前端的天氣預測網頁：自動定位、搜尋任意地址或城市，並以圖表呈現未來一天到兩個月的溫度、體感溫度、濕度與降雨機率，還可以收藏地點或比較兩個地點。

🔗 **線上展示：** https://lullaby4001.github.io/weather/

## 功能

- 開啟時自動定位，並顯示目前的溫度、體感溫度、濕度、降雨機率
- 搜尋城市或完整地址，隨時更換地區
- 預測區間可選：一天、一週、兩週、三週、一個月、兩個月
- 四張圖表：溫度（含最高 / 最低）、體感溫度、相對濕度、降雨機率
- 攝氏 / 華氏切換
- 收藏常用地點（儲存在瀏覽器中）
- 選擇兩個地點進行比較

## 預測資料說明

| 預測區間 | 資料來源 | 性質 |
|---|---|---|
| 16 天內 | Open-Meteo 氣象模式預報 | 預報 |
| 超過 16 天 | 過去 3 年同期的歷史平均 | 氣候趨勢推估 |

超過 16 天的部分在圖表上以**虛線**表示。這是依歷史資料推估的趨勢，不是氣象預報，準確度有限，僅供參考。其中降雨機率是以過去 3 年同期前後各 3 天的「下雨日比例」估算。

## 使用的資源

**資料**
- [Open-Meteo](https://open-meteo.com/)：天氣預報與歷史資料 API（[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)）
- [OpenStreetMap Nominatim](https://nominatim.org/)：地址搜尋與反向地理編碼（© OpenStreetMap contributors）

**技術**
- HTML / CSS / JavaScript（無框架、無需建置）
- [Chart.js](https://www.chartjs.org/)：圖表繪製（MIT）
- 瀏覽器 Geolocation API：取得目前位置
- 瀏覽器 localStorage：儲存收藏地點與單位偏好
- GitHub Pages：網站託管

## 如何使用

### 線上使用
直接開啟上方的展示連結，並允許瀏覽器存取位置即可。

### 在本機執行
```bash
git clone https://lullaby4001.github.io/weather.git
cd weather
python -m http.server 8000
```
接著用瀏覽器開啟 `http://localhost:8000`。使用本機伺服器可以確保定位與收藏功能正常運作。

### 部署到 GitHub Pages
1. 將 `index.html` 放在 repository 根目錄
2. 到 **Settings → Pages**
3. Source 選 **Deploy from a branch**，Branch 選 `main`，資料夾選 `/ (root)`
4. 儲存後等待一到兩分鐘即可上線

## 限制

- 需要連網，天氣、地址搜尋與圖表套件皆從網路載入
- 超過 16 天的結果為歷史平均推估，不代表實際天氣
- Open-Meteo 的免費服務僅限非商業用途；Nominatim 有使用政策，不適合高流量場景。若要商業使用或公開給大量使用者，請改用付費方案或自行申請服務

## 致謝

天氣資料由 [Open-Meteo.com](https://open-meteo.com/) 提供，地點資料 © [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors。

## 授權

本專案程式碼以 MIT 授權釋出。第三方資料與套件請依其各自授權使用。
