# 臺中市外埔區馬鳴國小 115學年度學生獎助學金資訊網

本網站為馬鳴國小 115 學年度全校各類學生獎助學金與專案補助申辦資訊專區。提供各班級導師、家長一站式查閱各項獎助學金資格、金額、校內截止時程（提前一週），並可直接下載填寫 Word（`.docx`）格式之申請表件。

* 🌐 **校內專屬直通網址**：[https://s894041-prog.github.io/mmps-scholarship-115/?key=mmps](https://s894041-prog.github.io/mmps-scholarship-115/?key=mmps)
* 🔒 **通關密碼**：`mmps`、`mmps115` 或 `2683`

---

## 🛡️ 學生隱私與個資安全防護說明

本專區涉及弱勢學生關懷與歷史名冊，落實以下三道安全防護：
1. **防搜尋引擎爬蟲**：配置 `robots.txt` 與 `noindex`，Google / Bing 絕對無法檢索收錄。
2. **專屬網址與門禁鎖定**：使用專屬網址（帶 `?key=mmps`）可無感直接開啟；未帶 key 則會被全螢幕密碼門禁攔截。
3. **原始碼去識別化**：學生個資在原始碼中經過演算法加密，GitHub 上絕無任何學生全名明文。

---

---

## ⏳ 動態倒數計時與自動隱藏功能說明

網站內建純前端即時倒數計時與逾期自動隱藏機制：
1. **即時動態倒數**：
   - 剩餘天數 $\ge 3$ 天：顯示綠色標籤 `⏳ 倒數 X 天`
   - 剩餘天數 $1 \sim 2$ 天：顯示橙色警示標籤 `⚠️ 倒數 X 天 Y 小時`
   - 剩餘時間 $< 24$ 小時：顯示紅色動態呼吸燈標籤 `🔥 最後衝刺：剩餘 X 小時 Y 分`
2. **每日自動計算更新**：
   - 依瀏覽器當前日期時間每日自動換算剩餘天數，每分鐘自動刷新，無須手動維護。
3. **時間截止自動隱藏（防呆機制）**：
   - 只要超過校內截止時間（如 16:00），該獎學金卡片**自動從主畫面消失隱藏**，確保主頁只保留當前可申請之項目。
   - 工具列提供 `[☑ 顯示已截止項目 (N)]` 開關：勾選後可以淺灰虛線樣式展開已截止項目供行政備查，兼顧版面簡潔與透明度。

## 📁 目錄結構

```
獎助學金資訊網/
├── index.html                           # 網站主頁面（純前端 RWD，含安全門禁驗證）
├── README.md                            # 說明文件與新增獎學金操作指引
├── robots.txt                           # 防搜尋引擎爬蟲設定
├── .gitignore                           # Git 忽略設定
└── downloads/                           # 附件下載資料庫
    ├── 115-1臺中市原住民在校住宿生住宿及伙食費申請表.docx
    ├── 115-1補助經濟弱勢學生代收代辦費調查表.docx
    ├── 115-1教育部學產基金低收入戶助學金申請表及切結書.docx
    ├── 115-1臺中市原住民籍學生文具費印領清冊.docx
    ├── 115-1台中縣林賴足女士教育基金會國小助學金申請書.docx
    ├── 115-1財團法人賑災基金會助學金申請辦法及表格.docx
    ├── 115-1行天宮急難濟助個案轉介申請表與學校評估表.docx
    ├── 115-1行天宮資優學生長期培育獎助學金申請書與推薦表.docx
    └── ... (官方法規要點與實施辦法 PDF/ODT/ODS 原檔)
```

---

## 💡 如何新增一筆新的獎學金？（3 步驟快速擴充）

### 步驟 1：將該獎學金的 Word 申請表放入 `downloads/` 資料夾
例如將 `【申請表】115-1同濟兒童嘉元獎助學金.docx` 放入 `downloads/`。

### 步驟 2：打開 `index.html`，複製卡片樣板並貼到對應的分類區塊內：
```html
<div class="card" data-keywords="關鍵字1 關鍵字2 金額" data-category="gov 或 foundation 或 emergency 或 talent">
  <div class="card-top">
    <span class="card-category-badge">分類標籤（如：民間文教基金會）</span>
    <span class="card-amount-badge">補助金額（如：每生 2,500 元）</span>
  </div>
  <h3>獎助學金完整名稱</h3>
  
  <div class="card-details">
    <div class="detail-item">
      <span class="detail-label">申請資格：</span>
      （填寫申請身分、成績限制、推薦名額等）
    </div>
    <div class="detail-item">
      <span class="detail-label">應附文件：</span>
      1. 申請書　2. 成績單　3. 戶籍謄本或戶口名簿
    </div>
    <div class="deadline-box">
      <!-- 請務必將官方公文截止日提前 7 天填入校內截止日 -->
      <div class="deadline-urgent">⚠️ 校內收件截止：115 年 ○ 月 ○ 日 (○) 下午 16:00</div>
      <div class="deadline-official">（官方郵戳/系統截止日：115年○月○日）</div>
    </div>
  </div>

  <div class="card-actions">
    <a href="downloads/你的檔案名稱.docx" class="btn btn-word" download>
      📥 下載申請表 (Word .docx)
    </a>
  </div>
</div>
```

### 步驟 3：存檔並推上 GitHub：
```bash
git add .
git commit -m "feat: 新增 115-1 ○○○獎助學金"
git push origin main
```
