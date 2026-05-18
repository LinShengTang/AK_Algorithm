# AK_CTA_Master_Spec_v1.0
# CTA 主規格｜安全 + 轉化 + 教學 + 工具對接

**版本：** v1.0  
**建立日期：** 2026-05-18  
**基礎來源：**
- AK 教材 v7 Complete ULTRA MAX｜Chapter 3 CTA
- AK_CTA_Safety_Patch_v1.1
- AK CTA LM 23 Questions 深度輸出
- AK Course Evidence Protocol v1.0

**定位：**  
本文件不是學員手冊，也不是 Screenwriter 程式碼。  
它是 CTA 章節進入正式 HTML 手冊、Screenwriter 規則、v6.5 metadata 與後續 Performance Tracking 前的「主規格」。

---

## 0. 核心裁決

CTA 不是演算法推播訊號，也不是爆款保證器。

CTA 的正確定位是：

> **CTA = 轉化承接設計｜Conversion Handoff**

它的任務是把已經被 Hook / Script / Value 吸引的人，導向下一個低阻力行動。

CTA 不負責創造流量；CTA 負責承接意圖。

### 最終裁決

若只能設計一種 CTA，長期投報率最高的是：

> **C 類｜私訊承接型 DM Trigger**

但這個裁決只在以下條件成立：

1. 內容已經對準痛點或明確資訊缺口。
2. CTA 不使用機械式互動。
3. DM 第一段不是直接賣，而是診斷型提問。
4. 後端有可交付的 LFA / Micro Offer / 檢查表 / 模板。
5. 不把 DM、Messenger、社團、Live 說成官方 ranking factor。

---

## 1. 來源等級與框架來源

### 1.1 source_claim_level

| level | 定義 | CTA 章使用方式 |
|---|---|---|
| official | 平台官方文件、Help、Blog、Transparency Center | FB / YT Engagement Bait 邊界、YouTube fake engagement |
| high_confidence | 平台負責人公開說法、可信媒體直接引用 | IG Engagement Bait 限制、部分 IG 指標說法 |
| practical_inference | UX、行為科學、轉化實務、內容策略推論 | 安全 CTA 設計、Hook→CTA 對應、DM 承接 |
| first_party_experiment | 自己帳號 A/B Test，有具體數字 | CTA 類型效果、DM 轉化率、留言品質 |
| unsupported | 常見但沒有來源支撐 | 「留言+1 會加權」、「DM 是官方推播權重」 |

### 1.2 framework_origin

| origin | 定義 | CTA 章使用方式 |
|---|---|---|
| external_research | 外部研究、書籍、理論來源 | Cialdini、Loewenstein、Ziglar、Priestley |
| adapted_framework | AK 對外部框架的改編 | AK No Help 取代 Ziglar No Desire |
| first_party_framework | AK 自有整理與流程設計 | CTA 五層、DM 五步、失效診斷 |
| none | 非框架內容 | 平台規則、一般工具欄位 |

### 1.3 已裁決框架

| 框架 | 裁決 | source_claim_level | framework_origin | 教材寫法 |
|---|---|---|---|---|
| Ziglar 5 No’s 原版 | 可用 | high_confidence | external_research | No Need / No Money / No Hurry / No Desire / No Trust |
| AK 5 No’s 改編版 | 可用但需標改編 | practical_inference | adapted_framework | No Desire → No Help |
| Priestley 7-11-4 | 可用 | high_confidence | external_research | Daniel Priestley《Oversubscribed》框架 |
| Google ZMOT = 7-11-4 來源 | 不可用 | unsupported | none | 不可寫「Google 研究證明 7-11-4」 |
| Micro-Commitment Ladder | 可用 | practical_inference | first_party_framework | AK 轉化流程設計，引用 Cialdini 時需標為 practical inference |
| Information Gap | 可用 | practical_inference | external_research / first_party_framework | Loewenstein 1994 作為好奇心理論來源 |

---

## 2. v7 CTA 衝突修正

### 2.1 原衝突

v7 CTA Chapter 原本將下列語句作為低阻力 CTA 範例：

```text
留言 +1
```

但 CTA Safety Patch v1.1 已裁決：

```text
留言 +1 = Tier 1 Fatal Engagement Bait
```

### 2.2 修正原則

保留 Low Friction 概念，但重寫定義：

> **Low Friction ≠ Low Quality Engagement**  
> **低阻力 ≠ 低品質互動**

低阻力的正確定義：

1. 心理阻力低：觀眾知道為什麼要行動。
2. 行動成本低：不需要花太多力氣。
3. 非機械互動：不是打一個數字或單字換資源。

---

## 3. CTA 安全分級

### 3.1 Tier 1 Fatal｜硬性禁止

下列語句與變體應在 Screenwriter 中 hard fail：

```text
留言 +1
留言 1 / 留言 111
打「我」表示同意
按讚解鎖
按讚支持
按讚才更新
訂閱才繼續
分享給三個朋友
標記三個朋友
```

**處理：** 不允許直接發布；必須改寫。

### 3.2 Tier 2 Contextual Risk｜語境風險

下列語句不應直接 fail，應 warning 並要求人工判斷：

```text
留言領取
留言解鎖
留言換取
留言我發
留言拿模板
```

判斷邊界：

| 類型 | 判斷 | 說明 |
|---|---|---|
| 機械式換取 | 高風險 | 觀眾只需輸入無意義字詞即可換資源 |
| 情境式承接 | 相對安全 | 觀眾留言內容本身能幫助診斷或分流 |

安全改寫示例：

```text
你現在卡在選題、腳本還是發布？留言說一下，我再給你對應版本。
```

### 3.3 Tier 3 Weak CTA｜弱但不一定危險

```text
你覺得呢？
留言分享你的想法
有需要可以找我
```

這類不一定違規，但常因為過於空泛而低轉化。

---

## 4. 安全 CTA 四大類

### A 類｜真實問題型

**用途：** 留言品質、FB Discussion-Starter、受眾診斷  
**適合：** Facebook Feed / Reels、共鳴型內容、爭議型內容

模板：

```text
你現在卡在哪一步？
你比較常卡在選題、腳本，還是發布？
你遇過類似情況嗎？當時怎麼處理？
```

### B 類｜收藏型

**用途：** 教學內容、檢查表、步驟型內容  
**適合：** IG Reels、YouTube Shorts、教學短影音

模板：

```text
這份清單適合收藏，等你要拍片前再看。
先存起來，之後用得到。
```

### C 類｜私訊承接型

**用途：** 高意圖轉化、DM 診斷、LFA 承接  
**適合：** IG Reels、YouTube Shorts、痛點型內容、高客單服務

模板：

```text
如果你想要完整版本，可以私訊我「完整版」。
如果你也卡在這裡，私訊我你的狀況，我可以幫你看一下。
這份我可以給你，你要的話直接跟我說。
```

### D 類｜延伸觀看型

**用途：** 長內容導流、系列內容、留存延伸  
**適合：** YouTube 長影片、系列短影音

模板：

```text
下一支我會補第二步，想接著看的人可以先追蹤。
完整流程我另外做了一支，可以去看。
```

---

## 5. Hook → CTA 對應規則

| Hook 類型 | 主要心理機制 | 建議 CTA 類型 | 說明 |
|---|---|---|---|
| 痛點型 Pain | No Need / No Help | C 類私訊承接型 | 觀眾痛點被喚起，最適合導入診斷與解法 |
| 好奇型 Curiosity | Information Gap | B 收藏型 / D 延伸觀看型 | 保留缺口，導向完整流程或收藏 |
| 共鳴型 Relate | No Trust | A 真實問題型 | 先建立同理，再讓觀眾說出自己的狀況 |
| 爭議型 Controversy | Attention / Conflict | A 真實問題型 | 引導真實觀點，而不是機械表態 |
| 結果型 Result | Curiosity / Proof | B 收藏型 / C 私訊型 | 給出完整流程或診斷入口 |

### 核心原則

Hook 開什麼缺口，CTA 就要補什麼缺口。

若 Hook 與 CTA 不一致，容易造成：

```text
audience_mismatch
trust_gap
offer_gap
```

---

## 6. Platform → CTA placement 對應

| 平台 / 版位 | 建議 CTA 類型 | 建議位置 | 注意事項 |
|---|---|---|---|
| YouTube 長影片 | A 問題型 / D 延伸觀看型 | 中段 + 結尾 + 置頂留言 / end screen | 不要只押結尾，避免觀眾流失後才 CTA |
| YouTube Shorts | B 收藏型 / C 私訊型 | 畫面結尾 + description / pinned comment | 不支援長片 end screen |
| Instagram Reels | C 私訊型 / B 收藏型 | 畫面結尾 + Caption | Caption 可承接搜尋與私訊語境 |
| Instagram Stories | 問題貼紙 / Link / 回覆 | 中段 + 最後一張 | 使用官方互動元件，避免機械關鍵字誘導 |
| Facebook Reels | A 真實問題型 | 畫面結尾 + Caption | 以 Discussion-Starter 為主 |
| Facebook Feed | A 真實問題型 | 貼文最後一段 | 避免 Engagement Bait，鼓勵真實討論 |

### 跨平台裁決

> **核心 CTA 保持一致，版位與承接方式客製化。**

也就是：

```text
底層語句遵守三平台最大安全公約數
但 IG 可強化 DM，FB 可強化討論，YT 可強化延伸觀看
```

---

## 7. CTA → DM → Offer 鏈路

### 7.1 五節點鏈路

```text
影片 CTA
→ DM 開場
→ DM 診斷
→ 方案提出
→ 自然成交
```

### 7.2 每個節點的任務

| 節點 | 任務 | 常見斷點 |
|---|---|---|
| CTA | 低阻力引導下一步 | 踩 Engagement Bait / CTA 與 Hook 斷裂 |
| DM 開場 | 降低戒心，建立人感 | 直接丟連結、太像機器人 |
| DM 診斷 | 確認對方真正問題 | 沒聽懂需求、過早推銷 |
| 方案提出 | 對應問題給解法 | Offer 不吸引、價值不明 |
| 自然成交 | 消除最後阻礙 | No Trust / No Money / No Hurry 未處理 |

### 7.3 DM 第一則回覆規則

不建議：

```text
這是連結：xxxx
```

建議：

```text
沒問題，我可以給你。不過我想先確認一下，你現在主要是卡在選題、腳本，還是發布？
```

---

## 8. 不同產品類型 CTA 策略

| 產品類型 | 建議 CTA | 主要阻礙 | 說明 |
|---|---|---|---|
| 低客單產品 | 直接低阻力私訊 / 連結承接 | No Hurry | 決策短，重點是降低操作成本 |
| 中客單產品 | LFA / 檢查表 / 微課程 | No Trust / No Help | 先交付小價值，再追蹤轉化 |
| 高客單產品 | 一對一診斷 / 狀況回覆 | No Trust | 不直接賣，先診斷與建立信任 |
| 免費引流品 | 痛點導向 + 具體解法 | No Need / No Help | 不說資源多完整，而說能解什麼痛 |
| 服務型產品 | 診斷與人味 | No Trust | 強調理解與客製化 |
| 數位產品 | SOP、模板、效率 | No Help | 強調系統性與可立即使用 |

---

## 9. ManyChat / 自動化 / 人工回覆規格

### 9.1 裁決

ManyChat 不是問題，問題是機械式 CTA 與機器人式承接。

### 9.2 適合自動化的部分

```text
確認關鍵字
發第一句診斷型提問
提供初步分流選項
發送低風險資源
```

### 9.3 必須人工處理的部分

```text
高客單需求
非標準問題
反對意見處理
個人診斷
成交前信任建立
```

### 9.4 自動化風險

若 CTA 寫成：

```text
留言 111 自動發你
```

即使技術上能執行，也屬高風險。工具應提示改為情境式私訊承接。

---

## 10. CTA Post-check 診斷

### 10.1 失效原因分類

| diagnosis | 意義 | 修正方向 |
|---|---|---|
| cta_design | CTA 本身不清楚、不安全或摩擦過高 | 改寫 CTA 類型或語句 |
| content_value | 內容本身沒讓觀眾覺得值得行動 | 回頭修 Script / Value |
| audience_mismatch | Hook 吸來的人與 Offer 不一致 | 重寫 Hook 與受眾定位 |
| trust_gap | 信任不足，承諾要求太高 | 降低 CTA 層級，增加 Stories / 過程展示 |
| offer_gap | 引流品不吸引 | 重新設計 LFA / Micro Offer |
| timing | CTA 出現太早或太晚 | 調整位置與節奏 |

### 10.2 Post-check JSON

```json
{
  "cta_post_check": {
    "cta_used": "完整 CTA 語句",
    "cta_type": "question | dm_trigger | save | extend",
    "platform": "youtube | ig | fb",
    "publish_date": "YYYY-MM-DD",
    "expected_action": "comment | dm | save | click | watch_next",
    "actual_result": {
      "comments_total": 0,
      "comments_quality_ratio": 0.0,
      "dm_received": 0,
      "saves": 0,
      "clicks": 0,
      "reach_7d": 0
    },
    "failure_diagnosis": "cta_design | content_value | audience_mismatch | trust_gap | offer_gap | timing",
    "source_claim_level": "first_party_experiment",
    "next_fix": "",
    "notes": ""
  }
}
```

---

## 11. A/B Test 規格

### 11.1 禁止事項

不使用危險 CTA 作為新實驗組。

也就是，不測：

```text
留言 +1
留言 111
按讚解鎖
打「我」
```

舊內容可以作為 archive comparison，但不建議新上線測試。

### 11.2 建議三組安全對照

| 組別 | 類型 | CTA |
|---|---|---|
| A | 真實問題型 | 你現在卡在哪一步？留言告訴我。 |
| B | 私訊承接型 | 想要完整清單，可以私訊我「清單」。 |
| C | 收藏型 | 這份清單適合收藏，等你拍片前再看。 |

### 11.3 控制變量

A/B Test 應盡量控制：

```text
同主題
同 Hook
同 Script
同平台
相近發布時段
同類型受眾
只改 CTA
```

### 11.4 觀察指標

```text
comments_total
comments_quality_ratio
dm_received
dm_conversion
saves
clicks
reach_7d
watch_next
```

### 11.5 顯著性警告

沒有足夠樣本前，不得把單次波動寫成結論。

沒有實測前，所有轉化優劣都只能標：

```text
source_claim_level: practical_inference
```

跑出自有數據後，才可升級為：

```text
source_claim_level: first_party_experiment
```

---

## 12. 教學設計規格

### 12.1 學員必懂一句話

> CTA 不能無中生有，只能順水推舟。

### 12.2 5 分鐘測驗

給學員兩組數據：

```text
A：10萬觀看，2000 個「留言+1」，0 私訊，0 成交
B：3000 觀看，50 個私訊，10 單成交
```

問題：

```text
如果目標是下個月多賺 5 萬，你要哪一支影片的數據？
```

引導結論：

```text
高互動不等於高轉化；CTA 應服務轉化，不服務虛榮指標。
```

### 12.3 學員驗收標準

基礎：

```text
能刪除 Tier 1 Fatal CTA，並改寫成安全 CTA。
```

應用：

```text
能依 Hook 類型選對 CTA 類型。
```

進階：

```text
能根據 post-check 數據判斷失效原因並提出下一次修正。
```

### 12.4 畢業作品

產出一組：

```text
痛點型 Hook
→ Script
→ 安全 CTA
→ DM 診斷開場
→ CTA post-check 設計
```

---

## 13. Screenwriter Tool Mapping

### 13.1 應寫入位置

1. Quick Plan CTA 產出
2. Import Plan Prompt
3. Radar Plan CTA 建議
4. Script CTA 欄位
5. Review / Algorithm Claim Audit
6. AK Algorithm JSON 匯出
7. Plan Workspace metadata

### 13.2 必要欄位

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
    },
    "cta_platform_fit": {
      "platform": "youtube_long | youtube_shorts | ig_reels | ig_stories | fb_reels | fb_feed",
      "placement": "opening | middle | end | caption | sticker | pinned_comment | end_screen",
      "cta_type": "question | dm_trigger | save | extend",
      "risk_level": "low | medium | high",
      "source_claim_level": "practical_inference",
      "notes": ""
    },
    "cta_post_check": {
      "expected_action": "comment | dm | save | click | watch_next",
      "failure_diagnosis": "cta_design | content_value | audience_mismatch | trust_gap | offer_gap | timing",
      "source_claim_level": "first_party_experiment"
    }
  }
}
```

### 13.3 Hard banned 與 contextual risk 分離

```js
HARD_BANNED_CTA_PATTERNS = [
  "留言+1", "留言 +1", "打+1",
  "留言1", "留言111",
  "按讚解鎖", "按讚支持", "按讚才", "訂閱才",
  "分享給三個", "標記三個",
  "打「我」", "打我"
]

CONTEXTUAL_RISK_CTA_PATTERNS = [
  "留言領取", "留言解鎖", "留言換取", "留言我發", "留言拿"
]
```

---

## 14. v6.5 Tool Mapping

v6.5 不執行 CTA 審計，只接收與顯示 metadata。

應保存：

```text
cta_check
cta_platform_fit
cta_post_check
source_claim_level
framework_origin
expected_action
failure_diagnosis
```

不做：

```text
不重跑 CTA Safety Audit
不重寫 CTA
不重判演算法
不產生 Weekly Plan
```

---

## 15. 需補查 / 降級項目

以下內容不得在正式教材中寫成確定事實：

1. Safety Patch 會讓虛榮互動減少 20–40%。  
   - 等級：unsupported / first_party_experiment 待驗證

2. 平台必定用 NLP / 信息熵判斷留言品質。  
   - 等級：practical_inference，不可寫成官方機制

3. YouTube 長影片「中段 CTA 留存率必定高於結尾」。  
   - 等級：practical_inference，可寫成建議，不可寫成平台規則

4. ManyChat 風險細節。  
   - 等級：practical_inference，需後續補 Meta / ManyChat 官方文件或實測

5. DM 私訊數等於高價值 ranking signal。  
   - 等級：unsupported，不可使用

---

## 16. CTA Manual 建議目錄

正式 HTML 手冊建議目錄：

```text
1. CTA 是什麼
2. CTA ≠ 演算法推播訊號
3. v7 原衝突與 Safety Patch
4. 安全 CTA 四大類
5. 禁用語與語境風險
6. Hook → CTA 對應表
7. 三平台 CTA 策略
8. CTA → DM → Offer 鏈路
9. 不同產品類型 CTA
10. ManyChat / 人工回覆
11. CTA Post-check 診斷
12. A/B Test SOP
13. 學員練習與測驗
14. Screenwriter / v6.5 對接規格
15. 版本紀錄
```

---

## 17. 下一步

### P0｜已完成

```text
AK_CTA_Safety_Patch_v1.1
AK CTA 23 Questions LM Output
AK_CTA_Master_Spec_v1.0
```

### P1｜下一步

```text
產出 AK_CTA_Manual.html
```

### P2｜之後

```text
將 CTA Master Spec 轉成 Screenwriter 補強規格
確認 Screenwriter 目前 CTA Safety v0.5 是否完全對齊本文件
```

### P3｜接續章節

```text
Ch9 Performance Evidence Research
```

---

## 18. 最終一句話

> CTA 的最高標準，不是讓最多人動一下，而是讓對的人走下一步。

