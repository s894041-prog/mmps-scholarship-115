# 臺中市外埔區馬鳴國小 115學年度學生獎助學金資訊網

本網站為馬鳴國小 115 學年度全校各類學生獎助學金與專案補助申辦資訊專區。提供各班級導師、家長一站式查閱各項獎助學金資格、金額、校內截止時程（提前一週），並可直接下載填寫 Word（`.docx`）格式之申請表件。

---

## 📁 目錄結構

```
獎助學金資訊網/
├── index.html                           # 網站主頁面（純前端 RWD，內建即時搜尋與分類篩選）
├── README.md                            # 說明文件與新增獎學金操作指引
├── .gitignore                           # Git 忽略設定
└── downloads/                           # 附件下載資料庫
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

網站採用高度模組化的卡片式（Card）架構，未來若有新公文或新獎學金進來，只需 3 步驟：

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

### 步驟 3：存檔即可！
存檔後重新整理瀏覽器即可看到新卡片，即時搜尋與分類篩選會自動支援新卡片！

---

## 🚀 GitHub Pages 部署說明

本專案無任何打包依賴（Zero-config），若要部署至 GitHub Pages：
1. `git push origin main`
2. 在 GitHub Repo 的 `Settings` -> `Pages` 中，將 `Branch` 設為 `main`、路徑設為 `/ (root)`。
3. 儲存後即可直接取得專屬網址（如 `https://<帳號>.github.io/<專案名>/`）供全校同仁瀏覽。
