# AK 三平台影音變現演算法實戰資料庫 v1.1 補丁文件

**基礎版本：** v1.0.2（Source Linked）
**補丁版本：** v1.1
**補丁日期：** 2026-05-15
**補丁目的：** 填補四類缺口——官方文件未收錄、數據基準線空白、架構設計補強、已棄用條目標記
**合併方式：** 本文件可獨立使用，亦可合併入 v1.0.2 母版對應章節

---

## 補丁索引

| 類型 | 項目 | 平台 | 可信度 | 狀態 |
|---|---|---|---|---|
| A 官方補充 | YouTube Inauthentic Content Policy（2025年7月） | YouTube | official | 🆕 新增 |
| A 官方補充 | YouTube Fake Engagement 官方懲罰機制 | YouTube | official | 🆕 新增 |
| A 官方補充 | Instagram Engagement Bait 觸及懲罰 | Instagram | high_confidence | 🆕 新增 |
| A 官方補充 | Instagram Aggregator Penalty（2025年12月） | Instagram | high_confidence | 🆕 新增 |
| A 官方補充 | Instagram Your Algorithm 聲明興趣功能 | Instagram | high_confidence | 🆕 新增 |
| A 官方補充 | Instagram Keyword-based Discovery | Instagram | high_confidence | 🆕 新增 |
| B 數據基準線 | YouTube Retention Rate 業界基準 | YouTube | practical_inference | 🆕 新增 |
| B 數據基準線 | YouTube CTR 業界基準 | YouTube | practical_inference | 🆕 新增 |
| B 數據基準線 | YouTube CPM / RPM 各領域對照 | YouTube | practical_inference | 🆕 新增 |
| D 架構補強 | history_tracking 欄位基準值對照表 | 三平台 | — | 🆕 新增 |
| D 架構補強 | audit_report 版本記錄格式 | 三平台 | — | 🆕 新增 |
| DEPRECATED | Instagram Hashtag 追蹤功能 | Instagram | — | ⚠️ 已棄用 |

---

## 補充 Source Registry｜新增來源網址

| source_id | 用途 | 來源 | 明確網址 | 可信度 | 可佐證因素 |
|---|---|---|---|---|---|
| `yt_fake_engagement_policy` | YouTube 假互動與 Engagement Bait 官方政策 | YouTube Help | https://support.google.com/youtube/answer/3399767?hl=en | official | 禁止人工增加 views、likes、comments；「內容唯一目的是誘導互動」列為違規；首次違規警告，90天內再犯頻道可能終止 |
| `yt_inauthentic_content_2025` | YouTube Inauthentic Content 政策更新（2025年7月） | YouTube Help + Flocker.tv 報導 | https://support.google.com/youtube/answer/1311392?hl=en | official | 2025/7/15 從 Repetitious Content 更名為 Inauthentic Content；執法範圍從「重複上傳」擴大為「缺乏真正人類創意」；2026年1月最大規模 AI 頻道終止潮 |
| `ig_engagement_bait_reach` | Instagram CTA 互動誘餌觸及懲罰 | Social Media Today（引用 Instagram 官方說法） | https://www.socialmediatoday.com/news/instagram-certain-ctas-impact-post-reach/717732/ | high_confidence | Instagram 明確說明特定詞彙、數字或表情符號的 CTA 會降低觸及，特別影響 Explore 和非粉絲推薦觸及 |
| `ig_aggregator_penalty_2025` | Instagram Aggregator Penalty（搬運帳號懲罰） | Sprout Social + Net Influencer（引用 Instagram 行為） | https://sproutsocial.com/insights/instagram-algorithm/ | high_confidence | 搬運帳號在推薦中被原創者版本取代；浮水印被系統偵測；December 2025 更新後搬運帳號觸及下跌 60-80%，原創者觸及上升 40-60% |
| `ig_your_algorithm_2025` | Instagram Your Algorithm 聲明興趣功能 | Net Influencer（引用 Instagram 官方聲明） | https://www.netinfluencer.com/instagram-algorithm-reset-clarifies-the-rules-but-raises-the-stakes-for-creators/ | high_confidence | 2025/12/10 推出 Your Algorithm 功能，用戶可查看並自訂主題；最近 9-12 篇貼文決定演算法分類；主題不一致觸發分發懲罰；首先在美國 Reels 推出 |
| `ig_keyword_discovery_2025` | Instagram Keyword-based Discovery 取代 Hashtag | Sprout Social + Net Influencer | https://sproutsocial.com/insights/instagram-algorithm/ | high_confidence | 用戶已無法追蹤 hashtag；hashtag 從主要發現工具降級；自然語言與描述性 metadata 成為搜尋排序主因；IG 越來越像搜尋引擎 |
| `retention_rabbit_2025` | YouTube Retention Rate 業界基準 | Retention Rabbit（Q1 2024–Q1 2025，10,000+ 影片） | https://www.retentionrabbit.com/blog/2025-youtube-audience-retention-benchmark-report | practical_inference | 平均留存率 23.7%；教育類 42.1%；Vlog 類 21.5%；只有 16.8% 的影片超過 50% 留存；5-10 分鐘影片留存率峰值 31.5% |
| `lenos_ctr_benchmark_2025` | YouTube CTR 業界基準 | Lenos Tube | https://www.lenostube.com/en/youtube-ctr-benchmark-average-good-best-practices/ | practical_inference | 目標 CTR 基準：4-6%；前15秒清楚說明價值主張可提升 18% 的1分鐘留存率 |
| `miraflow_cpm_rpm_2026` | YouTube CPM / RPM 各領域數字（2025-2026） | Miraflow + upGrowth（彙整多個來源） | https://miraflow.ai/blog/youtube-cpm-rates-by-niche-2026-how-much-youtubers-earn | practical_inference | 財經 CPM $25-$65；教育 $12-$30；科技 $8-$25；遊戲 $2-$5；YouTube 抽45%，創作者拿55%；Shorts 創作者拿45% |

---

---

# YOUTUBE 補充章節

---

## inauthentic_content_policy｜不真實內容政策（2025年7月）

**Source Layer**
- 可信度：`official`
- 來源：YouTube Help（answer/1311392）
- 補丁版本：v1.1（2026-05-15）
- 原文摘要：2025年7月15日，YouTube 將 Repetitious Content 政策更名為 Inauthentic Content，將執法範圍從「重複上傳相同內容」擴大為「內容缺乏真正人類創意」。AI 生成但有真實人類編輯投入的內容不在懲罰範圍；純 AI 模板化大量生產的內容屬於違規。

**Creator Action Layer**

這是什麼意思：
YouTube 明確表示平台不禁止使用 AI 工具，但禁止「用 AI 取代人類創意」。判斷標準從「是否重複」改變為「是否有真實人類的創作投入」。2026年1月，YouTube 對 AI 生成頻道進行了史上最大規模的終止行動。

內容該怎麼做：
- 即使使用 AI 輔助撰寫腳本或剪輯，也必須加入創作者自身的觀點、聲音、故事
- 每一支影片必須能夠回答：「這支影片有什麼是只有我這個創作者能說的？」
- 系列影片要有主題演進，不能是不同包裝的同一套模板

該注意什麼：
- 此政策已從 Monetization Policy 擴展，違規不只是停止分潤，而是頻道終止
- YouTube Studio 的「審核通知」是最早的警告信號，不要忽視
- 與 v1.0.2 中的 `ig_original_content_guidelines` 和 `ig_recommendations_originality` 精神一致，但 YouTube 的懲罰層級更高（直接終止頻道 vs. Instagram 的推薦降權）

**Tool Mapping Layer**
- Screenwriter tag：`Originality-Check`（腳本必須有創作者自身觀點標記）
- v6.5 欄位：`audit.inauthentic_content_check`（新增欄位）
- 教材定位：AI 工具使用的正確框架——輔助工具 vs. 創意替代品的本質差異

---

## fake_engagement_policy｜假互動政策（YouTube 官方懲罰機制）

**Source Layer**
- 可信度：`official`
- 來源：YouTube Help（answer/3399767）
- 補丁版本：v1.1（2026-05-15）
- 原文摘要：YouTube 禁止任何人工增加 views、likes、comments 的行為，以及「內容唯一目的是誘導觀眾互動」的內容。懲罰機制：第一次警告（90天有效期），同一政策90天內再犯警告不消除，頻道可能被終止或永久移除。

**Creator Action Layer**

這是什麼意思：
YouTube 的 Engagement Bait 政策和 Facebook 的同名政策性質相同，但懲罰更為嚴重——最嚴重情況直接終止頻道，不只是降低觸及。

內容該怎麼做：
- 鼓勵互動時，說明「為什麼這個問題對觀眾有意義」，而非直接要求互動
- 不要使用「按讚我才更新、留言我才繼續做」這類脅迫式 CTA

該注意什麼：
- YouTube 的 Fake Engagement Policy 和 Engagement Bait 是兩個不同政策，前者針對「購買刷量」，後者針對「誘導真實用戶做機械式互動」
- 本條目補充 v1.0.2 中 `engagement_bait_check` 在 YouTube 的官方依據（v1.0.2 僅有 Facebook 的官方文件，YouTube 部分原為缺口）

**Tool Mapping Layer**
- Screenwriter tag：`Engagement-Bait-Guard`（與 Facebook 共用同一標籤）
- v6.5 欄位：`audit.engagement_bait_check`（更新 source_claim_level 為三平台 official）
- 教材定位：三平台的 Engagement Bait 均有官方政策，懲罰程度 YouTube ≥ Facebook > Instagram

---

## benchmark_retention｜YouTube 留存率業界基準

**Source Layer**
- 可信度：`practical_inference`
- 來源：Retention Rabbit（2025年報告，Q1 2024–Q1 2025，10,000+ 影片，75+ 利基市場）
- 來源網址：https://www.retentionrabbit.com/blog/2025-youtube-audience-retention-benchmark-report
- 補丁版本：v1.1（2026-05-15）
- 重要標注：此為第三方付費工具數據，樣本以中小型創作者為主。官方 YouTube 未公佈留存率基準數字。

**Creator Action Layer**

這是什麼意思：
這是 v1.0.2 中 `history_tracking.retention_rate` 欄位缺少的基準參照數字。以下數字可作為判斷「自己的留存率是否正常」的參考。

| 指標 | 數值 | 說明 |
|---|---|---|
| 全平台平均留存率 | 23.7% | 你的基準線起點 |
| 超過 50% 留存的影片比例 | 16.8% | 只有六分之一的影片能做到 |
| 5-10 分鐘影片留存率峰值 | 31.5% | 最容易達到高留存的長度區間 |
| 教育類最高留存率 | 42.1% | 教學型內容的天花板參考 |
| Vlog 類平均留存率 | 21.5% | 低於全平台平均 |

使用方法：
- `history_tracking.retention_rate` 低於 20% = 嚴重問題，需要回頭檢查腳本節奏
- 20-30% = 正常範圍，持續優化
- 30%+ = 良好，檢視是哪些設計決策有效
- 50%+ = 優秀，屬於前 16.8%

該注意什麼：
- 留存率因內容類型差異極大，不能用單一標準評判所有內容
- 「前15秒清楚說明價值主張」可提升1分鐘留存率約18%（Retention Rabbit 數據）
- 台灣創作者的留存率基準與全球數據可能有差異，建議以自身頻道歷史數據為主要參照

**Tool Mapping Layer**
- v6.5 欄位：`history_tracking.retention_rate`（新增 benchmark 對照欄位 `benchmark.retention_rate`）
- 教材定位：把抽象的「留存率」轉化為創作者能理解的「及格線」概念

---

## benchmark_ctr｜YouTube 點擊率業界基準

**Source Layer**
- 可信度：`practical_inference`
- 來源：Lenos Tube（2025年10月），Focus Digital Research（2025年12月）
- 補丁版本：v1.1（2026-05-15）
- 重要標注：第三方研究數據，不同來源方法論不同，官方 YouTube 未公佈 CTR 基準。

**Creator Action Layer**

這是什麼意思：
這是 v1.0.2 中 `history_tracking.ctr` 欄位缺少的基準參照數字。

| CTR 範圍 | 評估 | 行動建議 |
|---|---|---|
| < 2% | 低於正常，需要立刻調整 | 縮圖和標題全面重做 |
| 2-4% | 正常但有改善空間 | 每次上傳時持續 A/B 測試縮圖 |
| 4-6% | 達到業界目標基準 | 維持現有策略，小幅優化 |
| 6-9% | 良好 | 記錄哪些設計決策有效並複製 |
| 9%+ | 優秀，屬於頂端表現 | 以當前標題縮圖風格為頻道品牌基調 |

該注意什麼：
- CTR 越高不一定越好。高 CTR 低留存率 = 標題黨，演算法會降低推薦
- 新頻道前期 CTR 通常較低，因為演算法還在學習受眾匹配，不要過早放棄
- CTR 在影片上傳後48小時內通常最高，後續下降是正常現象

**Tool Mapping Layer**
- v6.5 欄位：`history_tracking.ctr`（新增 benchmark 對照欄位 `benchmark.ctr`）
- 教材定位：CTR 是入口指標，必須搭配留存率一起看，單看 CTR 沒有意義

---

## benchmark_cpm_rpm｜YouTube CPM / RPM 各領域基準

**Source Layer**
- 可信度：`practical_inference`
- 來源：Miraflow（2025-2026），upGrowth（2025年Q1–2026年Q1，25個利基市場），Lenos Tube
- 補丁版本：v1.1（2026-05-15）
- 重要標注：以下數字為英語市場為主的全球數據。台灣繁中創作者的實際 CPM 大幅低於此，需以自身 YouTube Analytics 為準。

**Creator Action Layer**

**CPM（廣告商支付每千次展示的費用）by 利基市場：**

| 領域 | CPM 範圍（美元） | 創作者實拿 RPM（55%） |
|---|---|---|
| 財經 / 個人理財 | $25 – $65 | $14 – $36 |
| 保險 / 法律 | $12 – $38 | $7 – $21 |
| 教育 / 商業技能 | $12 – $30 | $7 – $17 |
| 科技評測 | $8 – $25 | $4 – $14 |
| 旅遊 | $6 – $20 | $3 – $11 |
| 健康 / 健身 | $5 – $12 | $3 – $7 |
| 娛樂 | $2 – $8 | $1 – $4 |
| 遊戲 | $2 – $5 | $1 – $3 |

**季節性規律（財經類為例）：**
- Q1（1-3月）：CPM 最低，$8-$15，廣告預算年初重置
- Q2（4-6月）：回升至 $12-$18
- Q3（7-9月）：夏季低谷，$10-$14
- Q4（10-12月）：全年最高，$18-$30+，廣告主花完預算

**YouTube 收入分潤說明（official）：**
- 標準廣告格式（display、overlay、skippable、non-skippable、bumper）：創作者 55%，YouTube 45%
- YouTube Premium 分潤：依 Premium 會員的實際觀看時間比例分配
- YouTube Shorts 廣告分潤：創作者 45%，YouTube 55%（與長影片不同）

該注意什麼：
- CPM ≠ RPM。RPM = CPM × 55% × 實際廣告展示率（通常 40-60% 的觀看次數有廣告）
- 實際月收入 = RPM × 月觀看次數 ÷ 1000
- 台灣市場繁中內容的 CPM 通常遠低於英語市場，若要提升 CPM，可考慮加入英文字幕吸引高 CPM 市場觀眾
- Shorts 的 CPM 和 RPM 遠低於長影片，Shorts 適合拉新訂閱者，不適合作為主要收益來源

**Tool Mapping Layer**
- v6.5 欄位：新增 `history_tracking.cpm` / `history_tracking.rpm`
- 教材定位：選擇內容領域時的收益框架，10倍 CPM 差距意味著同樣的觀看次數有10倍的收益差異

---

---

# INSTAGRAM 補充章節

---

## ig_engagement_bait_penalty｜Instagram Engagement Bait 觸及懲罰

**Source Layer**
- 可信度：`high_confidence`
- 來源：Social Media Today 引用 Instagram 官方說法（2024年6月）
- 來源網址：https://www.socialmediatoday.com/news/instagram-certain-ctas-impact-post-reach/717732/
- 補丁版本：v1.1（2026-05-15）
- 重要標注：Instagram 對 Engagement Bait 的懲罰說法目前無等同 Facebook Transparency Center 的官方文件，維持 high_confidence 而非 official。Facebook 有 official 文件，YouTube 有 official 文件，Instagram 在這個議題上透明度最低。

**Creator Action Layer**

這是什麼意思：
Instagram 確認使用特定詞彙、數字或表情符號的 CTA（如「留言數字1」「按讚支持」）會直接降低觸及率。此懲罰主要影響 Explore 和非粉絲推薦觸及，對現有粉絲的 Feed 觸及影響較輕。

內容該怎麼做：
- 避免任何要求觀眾做「機械式重複動作」的 CTA
- 若要使用 ManyChat 等自動化工具觸發關鍵字，需評估是否會被系統識別為 Engagement Bait
- 引導互動的正確方式：說明「為什麼這個問題對你的生活有意義」

該注意什麼：
- 與 Facebook 的 Engagement Bait 相比，Instagram 的懲罰說法來源等級較低（high_confidence vs. official）
- 業界普遍認為 IG 的 Engagement Bait 懲罰確實存在，但官方從未發布正式的技術文件說明懲罰機制

**Tool Mapping Layer**
- Screenwriter tag：`Engagement-Bait-Guard`（三平台共用標籤，但 IG 的 claim level 為 high_confidence）
- v6.5 欄位：`audit.engagement_bait_check`
- 教材定位：三平台對 Engagement Bait 的懲罰均存在，但 IG 的官方透明度最低，教材中需標注此差異

---

## ig_aggregator_penalty｜Instagram 搬運帳號懲罰（2025年12月）

**Source Layer**
- 可信度：`high_confidence`
- 來源：Sprout Social（引用 Instagram 官方更新），Net Influencer（引用 Instagram 聲明）
- 來源網址：https://sproutsocial.com/insights/instagram-algorithm/
- 補丁版本：v1.1（2026-05-15）
- 原文摘要：Instagram 現在在推薦中主動用原創者版本取代搬運內容；浮水印被系統偵測；2025年12月更新後，搬運帳號觸及下跌 60-80%，原創者觸及上升 40-60%。

**Creator Action Layer**

這是什麼意思：
這是對 v1.0.2 中 `ig_original_content_guidelines` 和 `ig_recommendations_originality` 的重大升級——系統不只是「不推薦搬運內容」，而是「主動在推薦結果中用原創者取代搬運者」。搬運帳號因此在推薦觸及上面臨結構性崩潰。

內容該怎麼做：
- 使用其他平台內容時，必須加入足夠的原創價值（旁白、分析、重新剪輯）
- 若要轉發或引用他人內容，使用 IG 的官方「轉發」功能，並給予原創者標注
- 建立自己的原創素材庫，減少對搬運內容的依賴

該注意什麼：
- 帶有浮水印（如 TikTok 的 logo）的影片會被系統直接識別
- 「重新上傳並加上自己的字幕」這類低努力改編仍屬於搬運，不構成原創
- 此更新對以「整合其他人內容」為主的帳號影響最大

**Tool Mapping Layer**
- Screenwriter tag：`Originality-Check`（更新說明：IG 的 Aggregator Penalty 現在是主動替換，非被動降權）
- v6.5 欄位：`audit.originality_check`（更新懲罰等級說明）
- 教材定位：2025年12月後，搬運帳號在 IG 已幾乎無法通過自然推薦獲得新受眾

---

## ig_your_algorithm｜Instagram 聲明興趣 / Your Algorithm 功能（2025年12月）

**Source Layer**
- 可信度：`high_confidence`
- 來源：Net Influencer（引用 Instagram 官方聲明），2025年12月22日
- 來源網址：https://www.netinfluencer.com/instagram-algorithm-reset-clarifies-the-rules-but-raises-the-stakes-for-creators/
- 補丁版本：v1.1（2026-05-15）
- 原文摘要：2025年12月10日，Instagram 推出 Your Algorithm 功能，讓用戶可查看並自訂 Instagram 認為他們感興趣的主題。初始在美國 Reels 推出，後續擴展至 Feed 和 Explore。用戶的最近 9-12 篇貼文決定帳號的演算法分類。

**Creator Action Layer**

這是什麼意思：
這是 Instagram 推薦系統的重大架構改變——推薦依據從純行為訊號（watch time、likes）加入了「用戶主動聲明的興趣」。創作者的內容必須與系統對用戶興趣的判斷高度吻合，才能持續進入推薦。

內容該怎麼做：
- 頻道定位必須高度一致，最近 9-12 篇貼文構成你在系統中的「興趣標籤」
- 不要在核心主題外頻繁試水溫，每次跑題都可能損壞系統對你頻道的分類
- 若要測試新主題，使用 Trial Reels 功能（先只推給非粉絲測試），不影響現有粉絲的 Feed 推薦

該注意什麼：
- 此功能讓 IG 的演算法更像 YouTube 的 interest-based 系統，而非過去純依賴社交關係的推薦
- 若帳號在此功能推出前主題已不一致，需要至少連續 9-12 篇貼文重新建立主題信號
- 「聲明興趣」功能讓用戶可以主動移除創作者，對主題飄移的帳號影響更直接

**Tool Mapping Layer**
- Screenwriter tag：`True-Interest-Fit`（更新說明：IG 的興趣匹配現在包含用戶聲明興趣層）
- v6.5 欄位：`script_design.target_audience`（加入主題一致性評估）
- 教材定位：2025年12月後，IG 頻道的主題一致性從「建議做」升級為「必須做」

---

## ig_keyword_discovery｜Instagram Keyword-based Discovery（取代 Hashtag）

**Source Layer**
- 可信度：`high_confidence`
- 來源：Sprout Social，Net Influencer（引用 Instagram 官方行為），2025年12月
- 來源網址：https://sproutsocial.com/insights/instagram-algorithm/ | https://www.netinfluencer.com/instagram-algorithm-reset-clarifies-the-rules-but-raises-the-stakes-for-creators/
- 補丁版本：v1.1（2026-05-15）
- 原文摘要：IG 用戶已無法追蹤 hashtag；hashtag 從主要發現工具降級；自然語言和描述性 metadata（caption、alt text、語音識別）成為搜尋排序的主要依據。

**Creator Action Layer**

這是什麼意思：
Instagram 的發現機制正在從「#標籤導向」轉向「關鍵詞導向」，行為越來越像搜尋引擎。Caption 現在扮演類似 YouTube 描述欄的角色，是內容被索引和發現的重要依據。

內容該怎麼做：
- Caption 要自然包含目標受眾會使用的關鍵詞和短語，而非單純用 hashtag 補充
- 開啟 Alt Text 功能，用自然語言描述圖片或影片內容，幫助系統理解
- 影片中的口說內容也會被語音識別索引，腳本中自然包含核心關鍵詞有助於被發現

該注意什麼：
- Hashtag 並非完全無用，但從「主要發現工具」降級為「輔助工具」
- 不建議在每篇貼文堆砌大量 hashtag，3-5個高度相關的 hashtag 比30個混雜的更有效
- 這個改變讓 IG 的 SEO 策略越來越接近 YouTube 的關鍵詞研究策略

**Tool Mapping Layer**
- Screenwriter tag：`Intent-Matching`（更新說明：IG 現在適用與 YouTube 相同的搜尋意圖對齊邏輯）
- v6.5 欄位：`script_design.search_intent`（從 YouTube-only 擴展為 YouTube + IG 共用）
- 教材定位：三平台的 SEO 邏輯正在收斂，關鍵詞研究能力對三平台均有效

---

---

# 架構補強章節

---

## history_tracking 欄位基準值對照表

**補丁版本：** v1.1（2026-05-15）
**用途：** 補充 v1.0.2 中 `history_tracking` 欄位缺少的「判斷這個數字是好是壞」的基準參照

| 欄位 | 警示（需立即處理） | 正常範圍 | 良好 | 優秀 | 數據來源 | claim_level |
|---|---|---|---|---|---|---|
| `retention_rate`（YouTube 長影片） | < 20% | 20-30% | 30-40% | 50%+ | Retention Rabbit 2025 | practical_inference |
| `avg_pct_viewed`（YouTube 長影片） | < 20% | 20-35% | 35-50% | 50%+ | Retention Rabbit 2025 | practical_inference |
| `ctr`（YouTube） | < 2% | 2-4% | 4-6% | 6%+ | Lenos Tube 2025 | practical_inference |
| `retention_rate`（YouTube Shorts） | < 60% | 60-80% | 80-95% | 95%+ | 業界推論 | unsupported |
| `sends_per_reach`（Instagram） | — | — | — | — | 無可靠公開基準 | 待驗證 |
| `back_and_forth_replies`（Facebook） | — | — | — | — | 無可靠公開基準 | 待驗證 |

**重要說明：**
1. 所有第三方研究數字均以英語市場數據為主，台灣繁中創作者請以自身頻道歷史數據為主要參照
2. 「優秀」門檻不代表一定能觸發更高推薦，只代表相對表現
3. `sends_per_reach` 和 `back_and_forth_replies` 目前無可靠公開研究，保持「待驗證」直到找到可信來源

---

## audit_report 版本記錄格式

**補丁版本：** v1.1（2026-05-15）
**用途：** 補充 v1.0.2 中 `audit` 欄位缺少的版本記錄結構

```json
{
  "audit_report": {
    "version": "1.0",
    "timestamp": "2026-05-15T10:00:00Z",
    "auditor": "creator_self / AK_system",
    "results": [
      {
        "check_id": "engagement_bait_check",
        "status": "passed",
        "tier": "Tier 1 - Fatal",
        "note": ""
      },
      {
        "check_id": "originality_check",
        "status": "failed",
        "tier": "Tier 1 - Fatal",
        "note": "腳本第三段引用第三方影片，需加入創作者自身分析"
      },
      {
        "check_id": "curiosity_trap_check",
        "status": "warning",
        "tier": "Tier 2 - High Risk",
        "note": "標題承諾在影片第8分鐘才兌現，建議提前至第3分鐘"
      }
    ],
    "override_reason": "",
    "final_decision": "hold_for_revision"
  }
}
```

**Tier 分級說明（v1.1 更新）：**

| Tier | 名稱 | 觸發後果 | 範例 |
|---|---|---|---|
| Tier 1 - Fatal | 致命違規 | 強制鎖定，不允許發布 | Engagement Bait、無浮水印搬運、Fake Engagement |
| Tier 2 - High Risk | 演算法毒藥 | 強烈警告，需勾選「我了解後果」才能發布 | Clickbait、標題與內容嚴重不符 |
| Tier 3 - Optimization | 效能折損 | 軟性建議，允許略過 | Hook 不夠精準、缺乏 CTA、主題邊緣偏移 |

---

---

# DEPRECATED 條目

---

## ⚠️ Instagram Hashtag 追蹤功能 [DEPRECATED]

**棄用版本：** v1.1（2026-05-15）
**棄用原因：** Instagram 已於 2025年下半年取消用戶追蹤 hashtag 的功能，hashtag 從主要發現工具降級為輔助工具。

**原 v1.0.2 相關說法需要更新的部分：**
- 任何描述「hashtag 是 IG 主要發現機制」的說法需調整為「keyword-based discovery 為主，hashtag 為輔」
- 建議在 Screenwriter 和教材中移除「大量 hashtag 策略」的建議

**替代條目：** `ig_keyword_discovery_2025`（本文件已補充）

---

---

## 版本控制說明

```
v1.0.2 → v1.1 變更摘要：

新增 source_id：8個
新增訊號條目：10個（YT×4, IG×4, 三平台架構×2）
更新架構：history_tracking 基準值對照表 / audit_report 格式定義
棄用條目：1個（IG Hashtag 追蹤）
待驗證保留：3個（IG/YT Engagement Bait 實測數字、跨平台搬運折損率、台灣市場 CPM）

下一版（v1.2）建議優先補充：
1. IG Engagement Bait 的 official 文件（目前仍為 high_confidence）
2. Instagram Audience Matching 可量化的操作指南
3. 台灣繁中市場 CPM/RPM 實際數字（需創作者社群調查）
4. 跨平台搬運的 A/B 實測留存率折損數字
```
