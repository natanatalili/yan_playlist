# 金色のコルダ 歌曲搜尋（PWA）

從 `Songlist.csv` 動態讀取，支援歌詞圖片瀏覽。

## 功能

- 自動讀取 `Songlist.csv`，右上角 ↻ 手動更新
- 搜尋／系列／聲優篩選、排序
- **歌詞**：CSV `lyrics` 欄填 keyword → 卡片出現「歌詞」掣
- 點掣後依序載入 `lyricpic/{keyword}_1.jpeg`、`_2.jpeg`…
- PWA 可安裝、離線快取

## 歌詞圖片規則

1. 在 CSV 最後一欄 `lyrics` 填 keyword，例如：`Heart_Killer`
2. 把圖片放到 repo 的 `lyricpic/` 資料夾，檔名：
   - `Heart_Killer_1.jpeg`
   - `Heart_Killer_2.jpeg`
   - `Heart_Killer_3.jpeg`
   - …
3. 支援副檔名：`.jpeg` / `.jpg` / `.png` / `.webp`（按此順序嘗試）
4. 從 `_1` 開始連續載入，缺檔即停止

## 部署

上傳**全部檔案**（含 `lyricpic/`）到 GitHub → Settings → Pages → `main` / root。

之後改 CSV 或加歌詞圖，push 後手機撳 ↻ 更新即可。

## 本地預覽

```bash
npx serve .
# 或
python3 -m http.server 8080
```

不要直接雙擊 `index.html`（CORS 會讀唔到 CSV）。
