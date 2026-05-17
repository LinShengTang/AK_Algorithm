# AK Course Evidence Protocol v1.0
**AK 教材證據協議｜Source-Based Master Course 底層規格**

版本：v1.0  
日期：2026-05-17  
定位：AK Creator Monetization Course / Toolkit 的底層研究、教材、工具化規格  
適用範圍：AK v7 → v8 教材升級、HTML 手冊、Screenwriter、v6.5 metadata、NotebookLM / Claude / GPT / Gemini 研究流程

---

## 0. 核心定位

`AK_Course_Evidence_Protocol_v1.0.md` 不是一般團員使用的教材，也不是獨立前端工具。

它是整套 AK 自媒體變現教材與工具的「底層研究規格」。

它的任務是：

1. 定義每個教材章節的證據等級。
2. 防止把官方訊號、實務推論、自有框架、平台功能、轉化承接工具混在一起。
3. 建立每章固定研究流程。
4. 規範 NotebookLM / Claude / GPT / Gemini 的 evidence research prompt。
5. 規範 HTML 手冊、Screenwriter、v6.5 metadata 的欄位命名。
6. 建立 `first_party_experiment`，讓團隊自己的 A/B Test 數據成為可追蹤證據。

核心原則：

> 先定義證據，再寫教材；  
> 先標註可信度，再輸出結論；  
> 先分清平台規則、內容策略與轉化工具，再進工具化。

---

## 1. 五級 source_claim_level

所有教材、手冊、工具欄位、AI 回答都必須標註 `source_claim_level`。

| level | 中文 | 定義 | 可用措辭 | 禁止措辭 |
|---|---|---|---|---|
| `official` | 官方來源 | 平台官方 Help、Blog、Transparency Center、Business Help、官方工程部落格、官方政策文件 | 官方文件指出、平台明確說明、官方政策列明 | 若不是官方，不得使用「官方證明」 |
| `high_confidence` | 高可信來源 | 平台負責人公開說法、可信媒體直接引用平台說法、有出版品與頁碼但未直接讀原始書頁 | 高可信來源指出、可信資料顯示、可作為高可信參考 | 不得寫成 official |
| `practical_inference` | 實務推論 | UX、行為科學、心理學、CRO、創作者實務、第三方研究、策略推論 | 實務上可作為、可作為操作策略、可作為內容設計依據 | 不得寫成官方推播權重 |
| `first_party_experiment` | 自有實驗 | 自己帳號、團隊帳號、學員帳號的 A/B Test 與實測數據 | 內部測試顯示、本帳號實測、第一方數據觀察 | 不得泛化成平台規則 |
| `unsupported` | 無支撐說法 | 常見說法、都市傳說、無來源結論、不可驗證框架 | 常見說法但未驗證、目前無來源支持 | 不得寫入正式教材當結論 |

---

## 2. framework_origin

`source_claim_level` 是證據等級；`framework_origin` 是框架來源性質。兩者必須分開。

| framework_origin | 中文 | 定義 |
|---|---|---|
| `external_research` | 外部研究 / 外部框架 | 來自書籍、研究、公開框架、第三方理論 |
| `adapted_framework` | AK 改編框架 | 由外部框架改寫、替換、在地化、知識變現化 |
| `first_party_framework` | AK 自有框架 | AK 自行建立的操作框架、比例、流程、分類 |
| `none` | 無框架 | 單一事實、平台規則、工具欄位，不屬於框架 |

欄位示例：

```json
{
  "source_claim_level": "practical_inference",
  "framework_origin": "adapted_framework"
}
```

---

## 3. 已裁決框架 Registry

### 3.1 Zig Ziglar 5 No’s 原版

| 項目 | 裁決 |
|---|---|
| 框架名稱 | Zig Ziglar 5 No’s |
| 原始來源 | Zig Ziglar, *Secrets of Closing the Sale*, 1984 |
| 原版五項 | No Need / No Money / No Hurry / No Desire / No Trust |
| source_claim_level | `high_confidence` |
| framework_origin | `external_research` |
| 可用說法 | Zig Ziglar 銷售框架中常見的五個購買阻礙為 No Need、No Money、No Hurry、No Desire、No Trust。 |
| 不可誇大 | 不可說成平台演算法訊號；不可說成官方 ranking factor。 |

### 3.2 AK 5 No’s 改編版

| 項目 | 裁決 |
|---|---|
| 框架名稱 | AK 5 No’s Adapted |
| 改編內容 | No Desire → No Help |
| 原因 | 知識變現、工具教學、顧問服務中，受眾常見阻力不是「沒有欲望」，而是「看不出這對我有幫助」。 |
| source_claim_level | `practical_inference` |
| framework_origin | `adapted_framework` |
| 可用說法 | AK 改編版把 Ziglar 原版 No Desire 轉換為 No Help，用於診斷知識型內容與轉化場景中的「沒幫助感」。 |
| 不可誇大 | 不可說 No Help 是 Ziglar 原版；不可說它是平台官方訊號。 |

### 3.3 Daniel Priestley 7-11-4

| 項目 | 裁決 |
|---|---|
| 框架名稱 | 7-11-4 |
| 來源 | Daniel Priestley, *Oversubscribed* |
| 內容 | 7 小時內容 / 11 個觸點 / 4 個場域或位置 |
| source_claim_level | `high_confidence` |
| framework_origin | `external_research` |
| 可用說法 | 7-11-4 可作為多觸點信任累積與內容承接設計框架。 |
| 不可誇大 | 不可說是 Google 官方研究證明；不可說是平台演算法加權公式。 |

### 3.4 Google ZMOT 與 7-11-4 的關係

| 項目 | 裁決 |
|---|---|
| 說法 | Google ZMOT 是 7-11-4 原始來源 |
| source_claim_level | `unsupported` |
| framework_origin | `none` |
| 裁決 | 不可在教材中說「Google 官方研究證明 7-11-4」。 |
| 可用方式 | Google ZMOT 可作為多來源、多觸點決策背景資料，但不得作為 7-11-4 的直接背書。 |

### 3.5 40/30/20/10 內容比例

| 項目 | 裁決 |
|---|---|
| 框架 | 痛點 40% / 共鳴 30% / 結果 20% / 爭議 10% |
| source_claim_level | `unsupported` 或 `practical_inference`，視語境 |
| framework_origin | `first_party_framework` |
| 可用說法 | 可作為 AK 建議起始配比。 |
| 不可誇大 | 不可寫成統計結論、平台規則或官方建議。 |
| 必加說明 | 實際比例應依帳號數據、受眾反應與轉化目標調整。 |

---

## 4. 每章研究前的四層分類判斷

每一章開始 Evidence Research 前，必須先判斷其主體屬於哪一類。

1. **官方平台訊號**：平台官方明確定義或追蹤的訊號。例：CTR、watch time、retention、recommendation eligibility、engagement bait policy。
2. **內容設計策略**：內容如何吸引、留住、建立信任的設計方法。例：Hook、Script、Information Gap、Storytelling。
3. **轉化承接工具**：引導觀眾進入下一步、DM、社團、Messenger、Link、Offer 的工具。例：CTA、DM、Messenger、Groups、Live、Lead Magnet。
4. **自有實驗假設**：需要用自己帳號測試才能確定的假設。例：不同 CTA 的 DM 率、Hook A/B Test、內容比例、發布節奏。

### 4.1 AK v7 十章初始分類

| 章節 | 主要類型 | 官方來源密度 | 主要 Evidence |
|---|---|---:|---|
| Ch1 Hook | 內容設計策略 + 自有實驗 | 低 | 注意力科學、廣告心理學、前 3 秒留存數據 |
| Ch2 Script | 內容設計策略 | 低 | 敘事心理學、信任建立、身份認同理論 |
| Ch3 CTA | 平台邊界 + 轉化設計 + 自有實驗 | 中 | Engagement Bait / Fake Engagement 官方文件、CRO、A/B Test |
| Ch4 Stories | 平台功能 + 信任建立 | 中 | IG Stories 官方功能、7-11-4、互動貼紙、信任累積 |
| Ch5 Strategy | 內容方向策略 | 低 | 市場研究、受眾分析、自有數據 |
| Ch6 Algorithm | 平台官方訊號 | 高 | Algorithm Database v1.1 |
| Ch7 Signal | 市場情報方法 | 低至中 | Autocomplete、趨勢分析、受眾問題、競品觀察 |
| Ch8 Conversion | 轉化心理 + DM / Offer 設計 | 低至中 | 5 No’s、行為經濟學、談判心理、first-party conversion data |
| Ch9 Performance | 數據分析 + 優化 | 高 | Analytics 官方指標、history_tracking、A/B Test |
| Ch10 Execution | 執行系統設計 | 低 | 習慣科學、生產力、first-party framework |

---

## 5. Evidence Research Agent Prompt

每章都必須使用以下 Prompt 生成 Evidence Pack。

```text
你是 AK Evidence Research Agent。

主題：【章節主題】

任務：
請幫我找出這個主題可用於教材的 evidence，並嚴格分成五類：

1. official：平台官方文件、Help、Blog、Transparency Center
2. high_confidence：平台負責人公開說法、可信媒體直接引用、可查出版品但未直接讀原書
3. practical_inference：UX研究、行為科學、心理學、CRO、第三方可信研究、創作者實務
4. first_party_experiment：適合自己帳號設計 A/B Test 的假設與指標
5. unsupported：常見但沒有來源支撐的說法

請特別回答：
- 這個主題主要是官方 ranking factor、平台功能、內容設計策略、轉化承接工具，還是自有實驗假設？
- 官方文件可以支持哪些說法？
- 哪些說法不能寫進正式教材？
- 哪些說法只能寫成 practical_inference？
- 哪些說法需要 first_party_experiment 驗證？
- 有哪些常見迷思必須排除？
- 有沒有使用外部框架？若有，請標注 framework_origin。
- 若有 AK 改編，請標注 adapted_framework，不可寫成原版。

輸出格式：
source_id｜來源名稱｜source_claim_level｜framework_origin｜可支持的說法｜不能誇大的說法｜教材可用句｜建議追蹤指標
```

---

## 6. LM / NotebookLM 深挖硬規則

1. 沒有具體來源，不得使用「研究證明」「科學顯示」「實驗發現」等字眼。
2. 若只有實務經驗或合理推論，只能標記 `practical_inference`。
3. 若無來源且無法驗證，標記 `unsupported` 或 `unverified`。
4. 提到外部框架時，必須標注 `framework_origin`。
5. 提到 AK 改編框架時，必須標注 `adapted_framework`。
6. 平台功能不可誤寫成官方 ranking factor。
7. 轉化承接工具不可誤寫成演算法加權。

### 6.1 必須標注來源的框架

| 框架 | 標注方式 |
|---|---|
| Cialdini 承諾與一致性 | Robert Cialdini, *Influence*, 1984；`practical_inference` / `external_research` |
| Loewenstein Information Gap | George Loewenstein, “The Psychology of Curiosity”, 1994；`practical_inference` / `external_research` |
| Ziglar 5 No’s | Zig Ziglar, *Secrets of Closing the Sale*, 1984；`high_confidence` / `external_research` |
| AK 5 No’s 改編版 | No Desire → No Help；`practical_inference` / `adapted_framework` |
| Daniel Priestley 7-11-4 | Daniel Priestley, *Oversubscribed*；`high_confidence` / `external_research` |
| 40/30/20/10 內容比例 | AK 起始配比；`unsupported` or `practical_inference` / `first_party_framework` |

---

## 7. 每章產出流程

```text
確認章節主題
↓
四層分類判斷
↓
Evidence Research Agent 跑一次
↓
LM / NotebookLM / Claude / GPT 深度挖掘
↓
缺口識別
↓
補官方來源 / 高可信來源 / 實驗設計
↓
建立章節 Evidence Pack
↓
產出章節 Patch / Manual Draft
↓
產出 HTML 手冊
↓
產出 Tool Mapping
↓
回填 Screenwriter / v6.5 metadata 規格
```

---

## 8. HTML 手冊格式

每個章節 HTML 手冊應採一致格式，方便未來 Overall Hub 收合整合。

### 8.1 建議檔名

```text
AK_Hook_Manual.html
AK_Script_Manual.html
AK_CTA_Manual.html
AK_Stories_Manual.html
AK_Strategy_Manual.html
AK_Algorithm_Manual.html
AK_Signal_Manual.html
AK_Conversion_Manual.html
AK_Performance_Manual.html
AK_Execution_Manual.html
```

### 8.2 必備章節

1. 主題定位
2. 核心定義
3. Evidence Map
4. source_claim_level 說明
5. framework_origin 說明
6. 實戰模型
7. 發布前檢查清單
8. 常見錯誤 / 迷思破解
9. 安全邊界 / 風險提醒
10. 模板與範例
11. first_party_experiment 設計
12. 數據追蹤欄位
13. Screenwriter / v6.5 對接
14. 版本紀錄

---

## 9. Tool Mapping 規格

### 9.1 Screenwriter 應吸收的內容

Screenwriter 不需要顯示完整 evidence database，但必須吸收以下欄位：

```json
{
  "source_claim_level": "",
  "framework_origin": "",
  "audit_warnings": [],
  "content_risk_notes": [],
  "platform_fit": {},
  "pre_check": {},
  "post_check": {},
  "first_party_experiment": {},
  "history_tracking": {}
}
```

### 9.2 v6.5 應吸收的內容

v6.5 不執行 Radar、不執行 Evidence Research、不重判演算法。v6.5 只保留：

```json
{
  "import_source": "screenwriter",
  "topic_radar": {},
  "content_plan": {},
  "platform_profile": {},
  "algorithm_tags": [],
  "source_claim_level": "",
  "framework_origin": "",
  "audit_warnings": [],
  "history_tracking": {},
  "post_check": {}
}
```

### 9.3 禁止事項

v6.5 禁止：

1. 重跑 Radar。
2. 重跑雙審。
3. 重判 source_claim_level。
4. 把 DM、Messenger、Groups、Live 寫成 ranking factor。
5. 把 practical_inference 寫成 official。
6. 把 first_party_experiment 泛化成平台規則。

---

## 10. first_party_experiment 規格

`first_party_experiment` 用於記錄團隊自己的實測資料。

### 10.1 基本欄位

```json
{
  "first_party_experiment": {
    "experiment_id": "",
    "topic": "",
    "hypothesis": "",
    "platform": "",
    "start_date": "",
    "end_date": "",
    "control_variables": [],
    "changed_variable": "",
    "sample_size": 0,
    "metrics": {},
    "result_summary": "",
    "confidence_note": "",
    "decision": "keep / revise / discard / retest",
    "source_claim_level": "first_party_experiment",
    "do_not_generalize": true
  }
}
```

### 10.2 CTA 實驗欄位示例

```json
{
  "cta_experiment": {
    "version": "A/B/C",
    "cta_text": "",
    "cta_type": "question | dm_trigger | save | extend",
    "platform": "IG / FB / YT",
    "publish_date": "YYYY-MM-DD",
    "metrics": {
      "comments_total": 0,
      "comments_quality_ratio": 0,
      "dm_received": 0,
      "dm_conversion": 0,
      "saves": 0,
      "reach_7d": 0
    },
    "source_claim_level": "first_party_experiment",
    "notes": ""
  }
}
```

### 10.3 實驗解讀規則

1. 樣本不足時，只能寫「初步觀察」。
2. 單一帳號結果不能直接泛化為平台規則。
3. 若只改 CTA，必須盡量控制 Hook、Script、主題、發布時間。
4. 若變因太多，不可做因果結論。
5. 實驗結果可影響團隊 SOP，但不可寫成 official。

---

## 11. CTA Safety Patch v1.1 對接規則

CTA 章節與 Screenwriter 必須遵守 `AK_CTA_Safety_Patch_v1.1`。

### 11.1 Hard Banned CTA

```text
留言+1
留言 +1
打+1
留言1
留言111
打「我」表示同意
按讚解鎖
按讚支持
按讚才
訂閱才
分享給三個
標記三個
```

### 11.2 Contextual Risk CTA

```text
留言領取
留言解鎖
留言換取
留言分享
你覺得呢？
有需要可以跟我說
```

判斷規則：

```text
Hard Banned → 直接 fail
Contextual Risk → warning，需要人工判斷
```

### 11.3 Screenwriter 應輸出

```json
{
  "audit": {
    "cta_check": {
      "passed": true,
      "engagement_bait_detected": false,
      "hard_banned_patterns_found": [],
      "contextual_risk_patterns_found": [],
      "cta_type": "question | dm_trigger | save | extend",
      "platform_fit_checked": true,
      "source_claim_level": "practical_inference",
      "framework_origin": "none",
      "notes": ""
    }
  }
}
```

---

## 12. Ch9 Performance Evidence Research 初始方向

Ch9 Performance 是 CTA 後建議優先研究章節，因為它可接 official Analytics 與 first_party_experiment。

### 12.1 研究重點

1. CTR
2. Impressions
3. Reach
4. Watch time
5. Average view duration
6. Average percentage viewed
7. Retention
8. Likes / Comments / Shares / Saves
9. DM received
10. Paid vs Organic
11. Post-check iteration
12. A/B Test interpretation

### 12.2 基本裁決

Performance 章應分成兩層：

```text
官方 Analytics 指標定義
+
AK 內容優化診斷邏輯
```

其中官方指標可標 `official`，但「數據低代表哪裡壞」多數是 `practical_inference` 或 `first_party_experiment`。

---

## 13. Overall Hub 延後規則

Overall Hub 不應在所有章節未穩定前製作。

建議至少完成：

1. AK Algorithm Manual
2. AK CTA Manual / Safety Patch
3. AK Performance Manual

再開始 Overall Hub。

原因：

1. 避免 Hub 收錄未審計章節。
2. 避免後續頻繁大改總入口。
3. 先讓 2–3 個章節形成穩定母版，再擴展其他章節。

---

## 14. 版本紀錄

### v1.0

- 建立五級 `source_claim_level`
- 建立 `framework_origin`
- 寫入 Ziglar 5 No’s / AK 改編 No Help 裁決
- 寫入 Priestley 7-11-4 / Google ZMOT Unsupported 裁決
- 定義四層分類判斷
- 定義 Evidence Research Agent Prompt
- 定義每章產出流程
- 定義 HTML 手冊格式
- 定義 Tool Mapping
- 定義 first_party_experiment
- 寫入 CTA Safety Patch v1.1 對接規則
- 建立 Ch9 Performance Research 初始方向
