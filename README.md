# Web Tools

個人使用的網頁小工具與小遊戲集合。每個工具都是獨立的 HTML 頁面，首頁 `index.html` 只負責列出連結。

所有處理都在瀏覽器本機完成，照片不會上傳到任何伺服器。

## 內容

### 工具

| 名稱 | 路徑 | 說明 |
|---|---|---|
| 鏡頭分析器 | `tools/lens-analyzer/` | 拖入整個資料夾，統計最常用的焦段、光圈、快門與 ISO，可匯出統計圖 |
| 批次浮水印 | `tools/watermask.html` | 一次替多張照片蓋上浮水印，打包成 ZIP 下載 |
| 相框製作 | `tools/photoFrame.html` | 替照片加上邊框與拍攝資訊列 |
| 修圖 | `tools/editor.html` | RGB 通道與色相、飽和、亮度、對比調整，存成 JPG |

### 遊戲

| 名稱 | 路徑 | 說明 |
|---|---|---|
| 節日賀卡 | `games/card/` | 給 3–6 歲小朋友玩的貼紙賀卡，平板優先；可復原、存成圖片 |

## 使用方式

不需要安裝或建置，直接用瀏覽器開啟 `index.html` 即可。

也可以用本機伺服器開啟：

```sh
python3 -m http.server 8000
# 瀏覽 http://localhost:8000
```

## 目錄結構

```
index.html          首頁（工具與遊戲列表）
tools/              影像工具
  lens-analyzer/    鏡頭分析器
  fonts/            相框製作使用的內嵌字型
games/              小遊戲
  card/             節日賀卡
```

`tools/lens_analyzer.html` 與 `tools/card.html` 是舊網址的轉址頁，保留給既有書籤使用。

## 新增工具或遊戲

1. 在 `tools/` 或 `games/` 底下建立資料夾，主頁面命名為 `index.html`，例如 `games/<名稱>/index.html`。
2. 在首頁 `index.html` 對應的區塊加上連結。連結要寫到 `.../index.html`，直接雙擊檔案（`file://`）開啟時才能正常跳轉。
3. 盡量維持單一 HTML、免建置；需要外部函式庫時從 CDN 載入。

如果之後某個遊戲需要 npm、打包工具，或素材變得很大，再把它拆成獨立的 repo，首頁只保留連結。

## 外部資源

以下資源需要網路才能載入：

- 字型：Google Fonts（Noto Sans TC、Barlow Condensed、Chiron GoRound TC）。離線時會退回系統字型。
- 函式庫：[exif-js](https://github.com/exif-js/exif-js)（鏡頭分析器）、[JSZip](https://stuk.github.io/jszip/)（批次浮水印），皆從 CDN 載入。
