# log-viewer-web

CSV log viewer with xrequestId grouping and payload preview.

## 功能

- 一次載入多個 CSV log 檔
- 依時間排序
- 依關鍵字搜尋 xrequestId、API、Exception、Vendor、PO
- 依 Log Level 與 Container 篩選
- 只看問題資料（ERROR / WARNING / 常見異常關鍵字）
- 點選單筆 log 後，可查看：
  - 單筆內容
  - 或同一個 xrequestId 的全部 log
- 自動嘗試格式化 JSON / XML payload
- 匯出目前選取群組

## 支援輸入格式

此工具適合用於 CSV 類型的 log 匯出檔，包含 Azure 風格的 CSV log。

最佳情況是 CSV 至少能對應這些欄位概念：

- time
- container
- level
- message

工具也會嘗試從獨立欄位或 message 內容中解析 `xrequestId`。

## 使用方式

1. 開啟網站
2. 點 **載入 CSV**
3. 選擇一個或多個 CSV 檔案
4. 使用搜尋框與篩選器縮小範圍
5. 點左側 log 查看細節
6. 可搭配：
   - **點選後看同 xrequestId 全部**
   - **詳細區顯示 Pretty / Raw**
   - **只看問題資料**
7. 點 **這筆轉 JSON/XML** 檢視結構化 payload

## GitHub Pages 部署步驟

1. 建立一個公開 GitHub repository
2. 將以下檔案上傳到 repository 根目錄：
   - `index.html`
   - `README.md`
3. 到 **Settings** → **Pages**
4. 在 **Build and deployment** 設定：
   - Source: `Deploy from a branch`
   - Branch: `main`
   - Folder: `/ (root)`
5. 按下 Save
6. 等待幾分鐘後開啟 GitHub Pages 網址

## 注意事項

不要把正式環境的敏感 log 檔直接上傳到 GitHub repository。

建議只發布這個靜態工具頁面，實際 CSV log 檔則在本機瀏覽器中手動載入。

## License

No license specified.
