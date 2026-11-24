# FolioVault 遠端目錄（GitHub Pages）

本資料夾為 **FolioVault** App 的雲端資料與圖示索引庫，純靜態託管於 GitHub Pages（無需後端伺服器）。

## 預設目錄網址
`https://wing9897zz.github.io/foliovault-catalog/catalog.json`

> App 內已預設綁定上述網址，開啟「設定 → 遠端機構目錄 (GitHub Pages)」即可直接同步；只有選取某個機構、實物、帳單或訂閱時，手機端才會按需下載該項目的單張 Logo 並快取於本機離線使用。

## 資料夾結構
- `catalog.json`：機構（`providers`）、實物／其他資產（`assets`）、銀行卡／U 卡配色（`cards`）、帳單供應商（`bills`）與訂閱服務（`subscriptions`）索引（UTF-8 無 BOM）
- `logos/`：預下載的標準 `.png` / `.jpg` 官方圖示（共 113 個）
- `index.html`：靜態首頁資訊頁
- `.nojekyll`：停用 GitHub Pages 的 Jekyll 處理

## 欄位規格說明
- **`providers[].category`**：`wallet`（加密錢包）、`exchange`（CeFi 交易所）、`broker`（券商）、`bank`（銀行）、`pay`（支付 / 理財）、`insurance`（保險 / 退休）、`other`（其他）
- **`assets[].kind`**：`physical`（實物資產）、`other`（其他金融產品）、`crypto`、`stock`、`fiat`、`debt`
- **`cards[]`**：1:1 擬真卡面配色（`region`、`theme`、`colors`、`finish`、`textColor`、`network`），純向量渲染無版權風險
- **`bills[]`**：帳單供應商（`billSubtype`：`esim`、`water`、`electricity`、`gas`、`internet`、`rent`、`insurance`、`tax`、`other`，可選 `logo` 或 `domain`）
- **`subscriptions[]`**：訂閱服務（`subSubtype`：`media`、`saas`、`cloud`、`vpn`，可選 `logo` 或 `domain`）
- **`aliases`**：繁體、簡體、英文別名陣列，方便跨語系即時搜尋
- **`logo`**：相對路徑（例如 `"logos/prov-linepay.png"`）或完整 `https://` 網址；若省略則會自動依 `domain` 抓取官網圖示
