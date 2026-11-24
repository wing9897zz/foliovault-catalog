# FolioVault GitHub Pages 上傳包

這個資料夾已經整理好所有需要上傳到 GitHub 的檔案，直接把**資料夾內的所有檔案與子資料夾**一起拖曳上傳到你的公開 GitHub Repo 即可，**不需要**設定 GitHub Actions 或任何 Worker 腳本。

## 資料夾內容
- `catalog.json`：機構（銀行、錢包、券商、支付等）與實物資產目錄索引
- `logos/`：自訂 Logo 圖片資料夾（可放 PNG，例如 `logos/prov-alipay.png`）
- `index.html`：首頁資訊頁（避免打開根網址出現 404）
- `.nojekyll`：告知 GitHub Pages 直接以純靜態檔案發布

## 使用步驟（免寫程式、直接上傳）
1. 在 GitHub 建立一個 **Public（公開）** Repository，例如 `foliovault-catalog`。
2. 點選 **Add file → Upload files**，把 `foliovault-github-pages` 裡面的所有檔案直接拖曳進去並 **Commit changes**。
3. 進入該 Repo 的 **Settings → Pages**：
   - **Source** 選 `Deploy from a branch`
   - **Branch** 選 `main` / `/ (root)`，按 **Save**
4. 等待約 30–60 秒後，你的目錄網址就是：
   `https://<你的GitHub帳號>.github.io/foliovault-catalog/catalog.json`
5. 打開手機 FolioVault App → **設定 → 遠端機構目錄 (GitHub Pages)**，貼上上述網址並點 **同步目錄**。

## 日後新增機構／圖示
- 只需在 GitHub 線上編輯 `catalog.json` 新增一筆資料（有自訂圖檔就同時上傳到 `logos/` 並填 `"logo": "logos/xxx.png"`；沒圖檔只需填 `"domain": "xxx.com"`，App 會自動抓取官網圖示）。
- 儲存後不用重新編譯 App，手機端按一次「同步目錄」即可搜尋到新項目。
