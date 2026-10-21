# NSSE DOS — 離線／網站單檔版

**線上使用：[開啟 NSSE DOS](https://h6rst0n.github.io/NSSE_dos/)**

**正式入口是 `index.html`。** 雙擊以新版 Chrome／Edge 開啟，再按「啟動 NSSE」即可。不需網路、Python、安裝 DOSBox 或啟動本機伺服器。同一份檔案也能直接放到 GitHub Pages。

在瀏覽器內執行原始 `NSSE.BAT`、`JCE.EXE` 與 `NUM-SOLN.EXE`。HTML 內嵌 DOSBox WebAssembly、原程式 ZIP、JavaScript、樣式及授權文字。原本的 DOS 介面、按鍵與數值程式均保留。

## 畫面自動調整

- 黑色外框配合瀏覽器可用空間。
- DOS 畫面固定 **4:3**，置中、不裁切，多餘空間留黑邊。
- 上限固定 **1600 × 1200 CSS px**，較小視窗自動縮小。
- 沒有尺寸設定按鈕或使用者可調整的上限。
- 視窗縮放、切換全螢幕及開關螢幕鍵盤不會重啟計算。
- 極矮視窗保留至少 180 px 高的顯示區，其他控制可垂直捲動查看。

CSS 像素會受到作業系統與瀏覽器縮放影響，並不一定等於實體螢幕像素。

## GitHub Pages 檔案

`dist/` 與 `nsse-github-pages.zip` 是正式靜態網站封裝，包含：

```text
index.html                 # 所有執行資源已內嵌；也是離線版
.nojekyll
THIRD_PARTY_NOTICES.md
```

將這些檔案放在網站根目錄即可。無需建置服務、套件安裝、外部 CDN、伺服器 API 或特殊 HTTP header。離線使用時只需 `index.html` 一個檔案，可以自行改名。

**本次沒有建立遠端 repository、推送或部署。**

## 原版操作

1. 啟動後，原版 JCE 開場畫面停留片刻，再進入主選單。
2. 點選 DOS 畫面，切換英文輸入法。方向鍵或畫面標示的字母／數字選擇，Enter 確認。
3. 主選單：`A` → BOXES_A，`B` → BOXES_B，`R` → RADIAL，`V` → VIBES。
4. 模組：`P` 選題、`R` 執行。輸入能量／參數後 Enter；需要預設值時直接 Enter。
5. 圖形頁：`S` 修改 Scale Factor、`Esc` 返回。`W` 顯示波函數平方；Radial 使用 `F` 顯示徑向分布。
6. 模組 `Q` 返回主選單；主選單 `Q` 結束到 DOS。網頁的「重新啟動」可重新開始。

網頁提供全螢幕、螢幕鍵盤、PNG 畫面下載與操作說明。重新啟動、重新整理與關閉網頁會清除本次參數；PNG 不是可重新載入的計算存檔。原 DOS 印表機與磁碟操作不會連到使用者實體設備。

## 版本保留

- `index.html`：目前正式版。
- `NSSE-responsive.html`：與正式入口完全相同的便捷副本。
- `NSSE.html`：較早、已認可的固定版，保留未改動；新使用請選 `index.html`。
- `versions/original-4x3-20261021/`：原版完整備份與 SHA-256。
- `versions/adjustable-responsive-20261021/`：先前可調整上限的測試版備份。

`versions/` 與 `work/` 是本機保留資料，已加入 Git 忽略清單，不是部署檔案。

## 開發與驗證

日常使用不需要以下指令。重新產生正式版及封裝時：

```bash
python scripts/build.py
python scripts/build.py --check
```

產生器以 `templates/offline-base/` 內納入版本控制的離線基底為基礎，套用 `experiments/responsive/layout.css` 與 `layout.js` 的固定版面；驗證內嵌 DOS 文件完全相同。`templates/index.html` 及 `build_standalone.py` 保留供舊版來源重建，與目前生成的根目錄 `index.html` 分開，避免重複嵌入。

完整程式已逐一執行四模組的 28 個題目。正式版另測試七種視窗尺寸、固定上限、全螢幕、螢幕鍵盤與離線直接開檔；詳見 `docs/fixed-responsive-validation.json`。瀏覽器測試使用已安裝 Playwright 的 Node 環境，與訪客執行無關。

計算由同一支原始 EXE 執行，未重新實作數值公式。驗證不代表已與 Windows XP 逐像素比較、驗證所有參數組合，或實測所有瀏覽器與實體手機。22 個原始檔案與引擎 checksum 仍保留。原程式版權與引擎授權見 `THIRD_PARTY_NOTICES.md`。
