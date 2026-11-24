# FolioVault 遠端機構與實物目錄（GitHub Pages）

本資料夾為 **FolioVault** App 的雲端機構與實物資產索引庫，純靜態託管於 GitHub Pages（無需 GitHub Actions 或後端 Worker）。

## 預設目錄網址
`https://wing9897zz.github.io/foliovault-catalog/catalog.json`

> App 內已預設綁定上述網址，開啟「設定 → 遠端機構目錄 (GitHub Pages)」即可直接同步；只有選取某個機構或實物時，手機端才會按需下載該項目的單張 Logo 並快取於本機。

## 資料夾結構
- `catalog.json`：機構（`providers`）與實物／其他資產（`assets`）索引（UTF-8 無 BOM）
- `logos/`：預下載的標準 `.png` / `.jpg` 官方圖示（共 113 個）
- `index.html`：靜態首頁資訊頁
- `.nojekyll`：停用 GitHub Pages 的 Jekyll 處理

## 欄位規格說明
- **`providers[].category`**：`wallet`（加密錢包）、`exchange`（CeFi 交易所）、`broker`（券商）、`bank`（銀行）、`pay`（支付 / 理財）、`insurance`（保險 / 退休）、`other`（其他）
- **`assets[].kind`**：`physical`（實物資產）、`other`（其他金融產品）、`crypto`、`stock`、`fiat`、`debt`
- **`aliases`**：繁體、簡體、英文別名陣列，方便跨語系即時搜尋
- **`logo`**：相對路徑（例如 `"logos/prov-linepay.png"`）或完整 `https://` 網址；若省略則會自動依 `domain` 抓取官網圖示
