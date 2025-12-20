# AEO 優化部署檢查清單

## 部署前檢查

### 文件完整性
- [x] `index.html` - 已添加 Schema、Meta 標籤、語義標記
- [x] `robots.txt` - 已添加 AI 爬蟲支持
- [x] `sitemap.xml` - 已增強元數據
- [x] `AI_SUMMARY.md` - 新建 AI 友好摘要
- [x] `structured-data.json` - 新建結構化數據文件
- [x] `AEO_OPTIMIZATION_SUMMARY.md` - 優化總結文檔
- [x] `AEO_TESTING_GUIDE.md` - 測試指南

### HTML 驗證
- [ ] 使用 W3C Validator 驗證 HTML
- [ ] 檢查所有 Schema.org 標記
- [ ] 確認 JSON-LD 語法正確
- [ ] 測試響應式設計未受影響

### 文件可訪問性
- [ ] 確認所有新文件可通過 URL 訪問
- [ ] 測試 CORS 設置（如需要）
- [ ] 檢查文件權限

---

## 部署步驟

### 1. 備份現有文件
```bash
# 備份當前版本
cp index.html index.html.backup
cp robots.txt robots.txt.backup
cp sitemap.xml sitemap.xml.backup
```

### 2. 上傳新文件
```bash
# 上傳修改的文件
# - index.html
# - robots.txt
# - sitemap.xml

# 上傳新文件
# - AI_SUMMARY.md
# - structured-data.json
# - AEO_OPTIMIZATION_SUMMARY.md (可選，僅供參考)
# - AEO_TESTING_GUIDE.md (可選，僅供參考)
# - DEPLOYMENT_CHECKLIST.md (可選，僅供參考)
```

### 3. 驗證部署
```bash
# 測試文件可訪問性
curl -I https://3ja.com/
curl -I https://3ja.com/robots.txt
curl -I https://3ja.com/sitemap.xml
curl -I https://3ja.com/AI_SUMMARY.md
curl -I https://3ja.com/structured-data.json
```

---

## 部署後立即檢查

### 基本功能
- [ ] 網站正常加載
- [ ] 所有視覺元素正常顯示
- [ ] 表單提交功能正常
- [ ] 語言切換功能正常
- [ ] 響應式設計正常

### 新增內容
- [ ] robots.txt 可訪問：https://3ja.com/robots.txt
- [ ] sitemap.xml 可訪問：https://3ja.com/sitemap.xml
- [ ] AI_SUMMARY.md 可訪問：https://3ja.com/AI_SUMMARY.md
- [ ] structured-data.json 可訪問：https://3ja.com/structured-data.json

### 結構化數據
- [ ] 使用 Google Rich Results Test 測試
  - URL: https://search.google.com/test/rich-results
  - 輸入: https://3ja.com
- [ ] 使用 Schema.org Validator 測試
  - URL: https://validator.schema.org/
  - 輸入: https://3ja.com

### 瀏覽器測試
- [ ] Chrome - 正常顯示
- [ ] Firefox - 正常顯示
- [ ] Safari - 正常顯示
- [ ] Edge - 正常顯示
- [ ] 移動瀏覽器 - 正常顯示

---

## 24 小時後檢查

### Google Search Console
- [ ] 提交新的 sitemap.xml
- [ ] 檢查結構化數據報告
- [ ] 查看索引覆蓋率
- [ ] 檢查是否有錯誤

### 服務器日誌
- [ ] 檢查 AI 爬蟲訪問記錄
  - GPTBot
  - ChatGPT-User
  - CCBot
  - anthropic-ai
  - Claude-Web
  - PerplexityBot
  - Google-Extended

### 性能
- [ ] 頁面加載速度未受影響
- [ ] Core Web Vitals 正常
- [ ] 無 JavaScript 錯誤

---

## 1 週後檢查

### AI 引擎測試
- [ ] ChatGPT 知識測試（參考 AEO_TESTING_GUIDE.md）
- [ ] Claude 知識測試
- [ ] Perplexity 搜索測試
- [ ] Google Bard/Gemini 測試

### SEO 影響
- [ ] Google 排名未下降
- [ ] 有機流量正常
- [ ] 點擊率正常

---

## 1 個月後評估

### 效果評估
- [ ] AI 引擎引用率
- [ ] 來自 AI 引擎的流量
- [ ] 用戶反饋
- [ ] 轉化率變化

### 數據更新
- [ ] 更新統計數據（如有新數據）
- [ ] 更新 dateModified
- [ ] 添加新的 FAQ（基於用戶問題）

---

## 回滾計劃

### 如果出現問題
```bash
# 恢復備份文件
cp index.html.backup index.html
cp robots.txt.backup robots.txt
cp sitemap.xml.backup sitemap.xml

# 刪除新文件（如果導致問題）
rm AI_SUMMARY.md
rm structured-data.json
```

### 常見問題及解決方案

#### 問題 1: 結構化數據錯誤
**解決方案**:
- 檢查 JSON-LD 語法
- 使用驗證工具找出錯誤
- 修正後重新部署

#### 問題 2: 頁面加載變慢
**解決方案**:
- 檢查新增的 Schema 大小
- 考慮將部分 Schema 移到外部文件
- 優化 JSON-LD 結構

#### 問題 3: AI 爬蟲被阻擋
**解決方案**:
- 檢查服務器配置
- 確認 robots.txt 語法正確
- 檢查防火牆設置

---

## 成功標準

### 必須達成（關鍵）
- ✅ 網站功能正常
- ✅ 無結構化數據錯誤
- ✅ 所有新文件可訪問
- ✅ SEO 排名未下降

### 應該達成（重要）
- ✅ AI 爬蟲成功訪問
- ✅ Google Search Console 無警告
- ✅ 頁面性能未下降

### 希望達成（優化）
- ✅ AI 引擎可回答基本問題
- ✅ 來自 AI 引擎的流量增加
- ✅ 用戶反饋正面

---

## 聯繫信息

**技術支持**: 參考 Google Search Console 和 Schema.org 文檔
**問題報告**: 記錄在項目文檔中
**更新頻率**: 每月檢查和更新

---

**部署日期**: _____________
**部署人員**: _____________
**檢查日期**: _____________
**檢查人員**: _____________

---

## 備註

記錄任何特殊情況、問題或觀察：

```
[在此記錄]
```
