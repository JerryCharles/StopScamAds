# AEO 優化測試指南

## 如何測試 AI 引擎優化效果

### 1. ChatGPT 測試

#### 測試問題 1: 基本信息
```
問：What is StopScamAds?
期望回答：應該提到這是一個全球活動，目標是揭露和停止社交媒體平台上的詐騙廣告，年損失超過 $119B。
```

#### 測試問題 2: 統計數據
```
問：How much money do people lose to scam ads globally?
期望回答：應該引用具體數字，如歐洲 $119B (2025 est.)、美國 $18-20B、台灣 $2.647B 等。
```

#### 測試問題 3: 操作指南
```
問：How can I report scam ads to StopScamAds?
期望回答：應該提到訪問 https://3ja.com，提交螢幕錄影，填寫表單等步驟。
```

#### 測試問題 4: 深度理解
```
問：Why do social media platforms allow scam ads?
期望回答：應該提到高 CPC/CPM 收入、審查成本高、不被視為系統性風險等原因。
```

---

### 2. Claude 測試

#### 測試問題 1: 活動目標
```
問：Tell me about the goals of the StopScamAds campaign.
期望回答：應該提到 AI 驅動的廣告審查、用戶獎勵機制、透明度報告、全球監管框架等。
```

#### 測試問題 2: 詐騙運作方式
```
問：How do scam ads work on social media?
期望回答：應該解釋三步驟：詐騙者製作假廣告 → 平台分發並獲利 → 用戶受害。
```

#### 測試問題 3: 受影響平台
```
問：Which social media platforms have scam ad problems?
期望回答：應該列出 Meta (Facebook/Instagram)、YouTube、TikTok、X (Twitter)。
```

---

### 3. Perplexity 測試

#### 搜索查詢 1
```
搜索：scam ads statistics 2025
期望結果：應該在結果中看到 3ja.com，並引用具體的統計數據。
```

#### 搜索查詢 2
```
搜索：how to stop scam ads on social media
期望結果：應該提到 StopScamAds 活動和舉報方法。
```

#### 搜索查詢 3
```
搜索：deepfake scam ads Meta YouTube
期望結果：應該引用網站內容關於深度偽造詐騙的信息。
```

---

### 4. Google Bard / Gemini 測試

#### 測試問題 1
```
問：What is the financial impact of scam ads?
期望回答：應該提供結構化的統計數據，可能以表格形式呈現。
```

#### 測試問題 2
```
問：How much does it cost scammers to reach 1000 people?
期望回答：應該提到 $8 在 YouTube 上可以達到 1,000 用戶。
```

---

## 驗證結構化數據

### Google Rich Results Test
1. 訪問：https://search.google.com/test/rich-results
2. 輸入：https://3ja.com
3. 檢查：
   - ✅ Organization schema
   - ✅ Article schema
   - ✅ FAQPage schema
   - ✅ BreadcrumbList schema

### Schema.org Validator
1. 訪問：https://validator.schema.org/
2. 輸入：https://3ja.com
3. 檢查：無錯誤或警告

### JSON-LD Validator
1. 訪問：https://jsonld.com/json-ld-validator/
2. 複製 `structured-data.json` 內容
3. 驗證：JSON-LD 格式正確

---

## 檢查 AI 爬蟲訪問

### 查看服務器日誌
檢查以下 User-Agent：
- `GPTBot` (OpenAI)
- `ChatGPT-User` (OpenAI)
- `CCBot` (Common Crawl, used by many AI)
- `anthropic-ai` (Anthropic/Claude)
- `Claude-Web` (Anthropic/Claude)
- `PerplexityBot` (Perplexity)
- `Google-Extended` (Google AI)

### robots.txt 測試
1. 訪問：https://3ja.com/robots.txt
2. 確認：所有 AI 爬蟲都被明確允許

---

## 內容可訪問性測試

### AI_SUMMARY.md
1. 訪問：https://3ja.com/AI_SUMMARY.md
2. 確認：
   - ✅ 文件可訪問
   - ✅ Markdown 格式正確
   - ✅ 包含所有關鍵信息

### structured-data.json
1. 訪問：https://3ja.com/structured-data.json
2. 確認：
   - ✅ 文件可訪問
   - ✅ JSON 格式正確
   - ✅ 包含完整的 @graph

---

## 語義 HTML 測試

### WAVE Web Accessibility Evaluation Tool
1. 訪問：https://wave.webaim.org/
2. 輸入：https://3ja.com
3. 檢查：
   - ✅ 正確的標題層級
   - ✅ ARIA 標籤使用正確
   - ✅ 語義 HTML 元素

### HTML5 Validator
1. 訪問：https://validator.w3.org/
2. 輸入：https://3ja.com
3. 確認：無重大錯誤

---

## 測試時間表

### 立即測試（部署後）
- [ ] robots.txt 可訪問性
- [ ] sitemap.xml 格式
- [ ] AI_SUMMARY.md 可訪問性
- [ ] structured-data.json 可訪問性
- [ ] HTML 驗證

### 24 小時後
- [ ] Google Search Console 結構化數據報告
- [ ] 檢查爬蟲訪問日誌

### 1 週後
- [ ] ChatGPT 知識測試
- [ ] Claude 知識測試
- [ ] Perplexity 搜索結果

### 1 個月後
- [ ] AI 引擎引用率
- [ ] 來自 AI 引擎的流量（如果可追蹤）
- [ ] 用戶反饋

---

## 常見問題排查

### Q: AI 引擎沒有最新信息
**A**: 
- 檢查 `dateModified` 是否更新
- 確認 robots.txt 允許爬蟲
- AI 引擎可能需要時間更新知識庫（可能需要數週）

### Q: 結構化數據錯誤
**A**:
- 使用 Google Rich Results Test 檢查
- 確認所有 @id 引用正確
- 檢查 JSON-LD 語法

### Q: AI 引擎回答不準確
**A**:
- 檢查 AI_SUMMARY.md 內容是否清晰
- 確認 FAQ Schema 涵蓋常見問題
- 考慮添加更多結構化數據

### Q: 爬蟲無法訪問
**A**:
- 檢查服務器配置
- 確認沒有 IP 封鎖
- 檢查 robots.txt 語法

---

## 成功指標

### 短期（1-2 週）
- ✅ 結構化數據無錯誤
- ✅ AI 爬蟲成功訪問
- ✅ 所有文件可訪問

### 中期（1 個月）
- ✅ AI 引擎可以回答基本問題
- ✅ 統計數據被正確引用
- ✅ 網站在相關查詢中被提及

### 長期（3 個月）
- ✅ AI 引擎成為重要流量來源
- ✅ 引用準確率 > 90%
- ✅ 用戶通過 AI 引擎發現網站

---

## 持續優化

### 每週
- 監控 AI 引擎回答準確性
- 收集用戶反饋

### 每月
- 更新統計數據
- 添加新的 FAQ
- 優化 AI_SUMMARY.md

### 每季度
- 全面審查 AEO 策略
- 分析 AI 引擎流量
- 調整結構化數據

---

## 聯繫支持

如果遇到技術問題：
1. 檢查 Google Search Console
2. 使用在線驗證工具
3. 查看服務器日誌
4. 參考 Schema.org 文檔

---

**最後更新**: 2025-01-01
**下次審查**: 2025-02-01
