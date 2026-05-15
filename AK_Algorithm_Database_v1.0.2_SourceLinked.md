# AK 三平台影音變現演算法實戰資料庫 v1.0.2（Source Linked）
**定位：** 演算法官方訊號 × 創作者行動 × 工具化欄位的整合母版
**來源：** YouTube Help / YouTube Blog / Instagram Creators / Meta Transparency Center / Meta Engineering / Facebook Newsroom
**可信度分級：** official / high_confidence / practical_inference / unsupported
**後續用途：** 從此母版拆出→ 實戰總表 / 教材版 / Facebook Page 補充章 / Screenwriter+v6.5+JSON 規格版 / PPT 來源附錄

---

## 總覽索引表

| 平台 | 核心推播邏輯 | 官方核心訊號 | 實務承接訊號 | 工具主軸 |
|---|---|---|---|---|
| YouTube | 搜尋意圖 × 觀看體驗 × 滿意度 | watch time、CTR、survey responses、engaged views | 下一支影片、播放清單路徑 | Intent-Matching / Retention-Bridge / Satisfaction-Proof |
| Instagram | Reels 拉新 × 分享 × 原創性 | watch time、retention、shares、likes、comments、originality | Profile visits、DM、Stories 回覆 | Watch-Time-Hook / Send-Worthy / Originality-Check |
| Facebook | 真實興趣 × 關係互動 × 社群信任 | UTIS、watch time、retention、satisfaction、MSI | Groups、Messenger、Live | True-Interest-Fit / Discussion-Starter / Group-Ready |

---

## 閱讀說明

每個訊號分三層：

- **Source Layer：** 官方來源、可信度、原文摘要
- **Creator Action Layer：** 創作者意義、內容做法、注意事項
- **Tool Mapping Layer：** 對應 Screenwriter tag、v6.5 欄位、教材定位

欄位命名統一規則：
```
history_tracking.[指標名稱]   → 發布後成效追蹤
script_design.[設計項目]      → 腳本生成前設計依據
audit.[檢查項目]              → 發布前審核檢查
```

---

# Source Registry｜來源網址總表（v1.0.1 補充）

**用途：**  
本區是給 NotebookLM、PPT、教材、審計使用的來源附錄。  
v6.5 / Screenwriter 工具本體不需要顯示完整網址；工具內只需保留 `source_claim_level`、`algorithm_tags`、`audit.warnings` 即可。

**使用原則：**

- `official`：官方文件、官方說明中心、官方工程部落格、官方透明中心。
- `high_confidence`：平台負責人公開說法或可信媒體直接引用平台說法。
- `practical_inference`：可用於內容策略與變現承接，但不可寫成官方推播權重。
- `unsupported`：來源未支持，不應寫入正式報告或教材。

---

## A. YouTube 官方／半官方佐證網址

| source_id | 用途 | 來源 | 明確網址 | 可信度 | 可佐證因素 |
|---|---|---|---|---|---|
| `yt_help_recommendation_system` | YouTube 推薦系統總說明 | YouTube Help | https://support.google.com/youtube/answer/16533387?hl=en | official | watch history、search、likes、shares、comments、not interested、survey responses、影片被展示後的 click / watch / positive engagement |
| `yt_blog_recommendation_system` | YouTube 推薦系統與滿意度 | YouTube Blog | https://blog.youtube/inside-youtube/on-youtubes-recommendation-system/ | official | clicks、views、watchtime、user surveys、shares、likes、dislikes、viewer satisfaction |
| `yt_search_discovery` | YouTube 搜尋與發現／Shorts 指標 | YouTube Help | https://support.google.com/youtube/answer/11914225 | official | choose to watch、ignore、not interested、average view duration、average percentage viewed、topic interest、competition、seasonality |
| `yt_shorts_views_update` | Shorts views 計算方式更新 | YouTube Help Community / TeamYouTube | https://support.google.com/youtube/thread/333869549/a-change-to-how-we-count-views-on-shorts?hl=en | official | 2025/3/31 起 Shorts views 只要開始播放或重播即計算；無最低觀看時間要求 |
| `yt_shorts_engaged_views` | Shorts views / Engaged views | YouTube Help | https://support.google.com/youtube/answer/10059070?hl=en | official | Shorts views 與 engaged views 差異；YPP / 分潤仍看 engaged views |
| `yt_how_youtube_works_recommendations` | YouTube 官方推薦系統入口 | YouTube How YouTube Works | https://www.youtube.com/howyoutubeworks/product-features/recommendations/ | official | 推薦系統目的：幫觀眾找到想看的內容，並個人化推薦 |

---

## B. Instagram 官方／Mosseri／可信媒體佐證網址

| source_id | 用途 | 來源 | 明確網址 | 可信度 | 可佐證因素 |
|---|---|---|---|---|---|
| `ig_ranking_explained` | Instagram 排名系統總說明 | Instagram 官方 | https://about.instagram.com/blog/announcements/instagram-ranking-explained | official | IG 不是單一演算法；Feed、Stories、Explore、Reels、Search 各自有不同排序系統 |
| `ig_how_instagram_works` | Instagram 舊版排名說明 | Instagram 官方 | https://about.instagram.com/blog/announcements/shedding-more-light-on-how-instagram-works | official | Feed、Explore、Reels 各自使用不同 ranking；使用者行為影響排序 |
| `ig_search_works` | Instagram Search 運作 | Instagram 官方 | https://about.instagram.com/blog/announcements/break-down-how-instagram-search-works | official | IG 搜尋會看文字輸入、使用者活動、結果人氣等 |
| `ig_creators_breakthrough` | Reels 訊號與突破新受眾 | Instagram Creators | https://creators.instagram.com/blog/helping-creators-of-all-sizes-break-through | official | Reels 訊號包含 watch time、retention、shares、likes、comments、audience matching |
| `ig_original_content_guidelines` | 原創內容指南 | Instagram Creators | https://creators.instagram.com/original-content-guidelines | official | 原創性、低努力修改、浮水印、速度變更、只標註原作者等不算高品質原創 |
| `ig_recommendations_originality` | 推薦與原創性 | Instagram Creators | https://creators.instagram.com/blog/recommendations-and-originality | official | 原創內容在推薦中會取代複製版本；平台鼓勵原創創作者 |
| `ig_recommendation_eligibility` | 推薦資格與最佳實務 | Instagram Creators | https://creators.instagram.com/blog/instagram-recommendations-eligibility-tips-creators | official | 內容要符合推薦資格；避免不利推薦的低品質或不合規內容 |
| `ig_verge_views_sends` | IG 指標：views / sends per reach | The Verge | https://www.theverge.com/2024/8/7/24215398/instagram-primary-metric-views | high_confidence | 報導 Mosseri 說 views 成為主要指標，並建議創作者看 sends per reach |
| `ig_verge_trial_reels` | Trial Reels | The Verge | https://www.theverge.com/2024/12/10/24317762/instagram-trial-reels-test-feature-availability | high_confidence | Trial Reels 可先推給非粉絲測試，觀察 views、likes、shares、comments |
| `ig_reels_chaining_ai` | Instagram Reels Chaining AI system | Meta Transparency Center | https://transparency.meta.com/features/explaining-ranking/ig-reels-chaining/ | official | IG Reels Chaining AI system 會預測使用者最可能感興趣的 Reels 並排序 |

---

## C. Facebook / Meta 官方、透明中心、工程部落格佐證網址

| source_id | 用途 | 來源 | 明確網址 | 可信度 | 可佐證因素 |
|---|---|---|---|---|---|
| `meta_ranking_overview` | Meta Ranking 總入口 | Meta Transparency Center | https://transparency.meta.com/features/explaining-ranking/ | official | Meta 多個產品版位使用 AI 系統排序內容 |
| `fb_reels_ai_system` | Facebook Reels AI system | Meta Transparency Center | https://transparency.meta.com/features/explaining-ranking/fb-reels/ | official | Facebook Reels AI system 會決定哪些 Reels 顯示、順序如何，依據預測使用者最可能感興趣的內容 |
| `fb_video_ai_system` | Facebook Video AI system | Meta Transparency Center | https://transparency.meta.com/features/explaining-ranking/fb-video/ | official | Facebook Video AI system 會決定 Video tab 中哪些影片出現與排序 |
| `fb_feed_ai_system` | Facebook Feed AI system | Meta Transparency Center | https://transparency.meta.com/features/explaining-ranking/fb-feed/ | official | Facebook Feed AI system 會預測使用者覺得最有價值、最相關的貼文並排序 |
| `fb_feed_recommendations_ai` | Facebook Feed Recommendations AI system | Meta Transparency Center | https://transparency.meta.com/features/explaining-ranking/fb-feed-recommendations/ | official | Facebook Feed Recommendations 會預測哪些未追蹤內容可能對使用者有興趣 |
| `fb_feed_ranking_content` | Facebook Feed Ranking 方法 | Meta Transparency Center | https://transparency.meta.com/features/ranking-and-content/ | official | Facebook Feed 使用機器學習為大量使用者個人化排序內容 |
| `meta_user_control_recommendations` | 使用者控制推薦內容 | Meta Transparency Center | https://transparency.meta.com/features/user-control-shape-your-experience-on-meta-platforms/ | official | 使用者可用 Interested / Not interested 影響 Reels、Feed、Explore、Search 推薦 |
| `fb_engineering_utis` | Facebook Reels UTIS 模型 | Meta Engineering | https://engineering.fb.com/2026/01/14/ml-applications/adapting-the-facebook-reels-recsys-ai-model-based-on-user-feedback/ | official | User True Interest Survey、interest matching、likes、shares、watch time、retention、satisfaction、niche high-quality content |
| `fb_msi_newsroom` | Facebook Meaningful Social Interactions | Meta / Facebook Newsroom | https://about.fb.com/news/2018/01/news-feed-fyi-bringing-people-closer-together/ | official | Facebook 調整 News Feed，重視人與人之間有意義互動、留言、分享、朋友互動 |
| `fb_public_comments_ranking` | Facebook 公開留言排序 | Meta / Facebook Newsroom | https://about.fb.com/news/2019/06/making-public-comments-more-meaningful/ | official | 公開留言排序會考慮留言品質、相關性、integrity、engagement bait 等 |
| `meta_ai_ranking_newsroom` | Meta 如何用 AI 排序 Facebook / Instagram 內容 | Meta Newsroom | https://about.fb.com/news/2023/06/how-ai-ranks-content-on-facebook-and-instagram/ | official | Meta 說明 AI 如何影響 Facebook、Instagram 的內容排序 |
| `fb_content_distribution` | Facebook 內容分發官方說明 | Meta Business Help | https://www.facebook.com/business/help/718033381901819 | official | Facebook 內容分發與排名訊號概觀；適合作為粉專營運建議來源，不應寫成單一演算法公式 |
| `fb_improve_reach` | 提升 Facebook / Instagram 觸及官方建議 | Meta Business Help | https://www.facebook.com/business/help/1424020861341537 | official | 提升觸及的官方建議；重視內容品質與受眾想看的內容 |
| `fb_engagement_bait_help` | Facebook Engagement Bait Help Center | Meta Business Help | https://www.facebook.com/business/help/259911614709806 | official | 互動誘餌與避免方式；可搭配公開留言排序來源使用 |

---

## D. 最建議優先閱讀的 10 個網址

若只要先掌握核心，建議先讀以下 10 個：

1. YouTube Recommendation System  
   https://support.google.com/youtube/answer/16533387?hl=en

2. YouTube Blog：On YouTube’s recommendation system  
   https://blog.youtube/inside-youtube/on-youtubes-recommendation-system/

3. YouTube Search & Discovery  
   https://support.google.com/youtube/answer/11914225

4. YouTube Shorts views update  
   https://support.google.com/youtube/thread/333869549/a-change-to-how-we-count-views-on-shorts?hl=en

5. Instagram Ranking Explained  
   https://about.instagram.com/blog/announcements/instagram-ranking-explained

6. Instagram Creators：Helping creators break through  
   https://creators.instagram.com/blog/helping-creators-of-all-sizes-break-through

7. Instagram Original Content Guidelines  
   https://creators.instagram.com/original-content-guidelines

8. Facebook Reels AI system  
   https://transparency.meta.com/features/explaining-ranking/fb-reels/

9. Facebook Reels UTIS / True Interest Model  
   https://engineering.fb.com/2026/01/14/ml-applications/adapting-the-facebook-reels-recsys-ai-model-based-on-user-feedback/

10. Facebook Feed Ranking  
    https://transparency.meta.com/features/ranking-and-content/

---

## E. 重要佐證對應

### YouTube 可明確佐證的因素

可佐證因素：

- 觀看歷史
- 搜尋行為
- 訂閱
- likes
- shares
- comments
- not interested
- survey responses
- clicks
- watch time
- average view duration
- average percentage viewed
- Shorts engaged views

主要來源：

```text
https://support.google.com/youtube/answer/16533387?hl=en
https://blog.youtube/inside-youtube/on-youtubes-recommendation-system/
https://support.google.com/youtube/answer/11914225
https://support.google.com/youtube/answer/10059070?hl=en
```

### Instagram 可明確佐證的因素

可佐證因素：

- 不同版位不同 ranking
- watch time
- retention
- shares
- likes
- comments
- audience matching
- send rate / sends per reach（high_confidence）
- 原創性
- 推薦資格
- 低品質 / 搬運內容不利

主要來源：

```text
https://about.instagram.com/blog/announcements/instagram-ranking-explained
https://creators.instagram.com/blog/helping-creators-of-all-sizes-break-through
https://creators.instagram.com/original-content-guidelines
https://creators.instagram.com/blog/recommendations-and-originality
https://creators.instagram.com/blog/instagram-recommendations-eligibility-tips-creators
https://www.theverge.com/2024/8/7/24215398/instagram-primary-metric-views
```

### Facebook 可明確佐證的因素

可佐證因素：

- AI 排序
- 個人化推薦
- 使用者興趣預測
- watch time
- likes
- shares
- retention
- satisfaction
- UTIS / true interest
- meaningful social interactions
- comments / discussion
- Interested / Not interested
- Feed / Reels / Video 個別 AI system

主要來源：

```text
https://transparency.meta.com/features/explaining-ranking/
https://transparency.meta.com/features/explaining-ranking/fb-reels/
https://transparency.meta.com/features/explaining-ranking/fb-video/
https://transparency.meta.com/features/explaining-ranking/fb-feed/
https://transparency.meta.com/features/ranking-and-content/
https://engineering.fb.com/2026/01/14/ml-applications/adapting-the-facebook-reels-recsys-ai-model-based-on-user-feedback/
https://about.fb.com/news/2018/01/news-feed-fyi-bringing-people-closer-together/
https://about.fb.com/news/2019/06/making-public-comments-more-meaningful/
```

---

## F. NotebookLM / PPT 使用規則

若使用本母版產出 PPT 或教材，必須遵守：

1. 每一個 `[official]` 或 `[high_confidence]` 說法，簡報附錄需能回到本 Source Registry。
2. 主投影片不必塞滿網址，但附錄必須保留網址。
3. `practical_inference` 可作為實務策略，不可寫成官方推播權重。
4. `unsupported` 不應寫入正式教學內容，除非是放在「迷思破解」頁。
5. `Profile visits / DM / Messenger / Groups / Live` 應標示為變現承接或實務推論，不可寫成官方 ranking factor。
6. `sends per reach` 應標示為 high_confidence，來源為媒體引用 Mosseri 說法，不是官方文件。

---


---

# YOUTUBE

---

## watch history｜觀看歷史

**Source Layer**
- 可信度：`official`
- 來源：YouTube Help（support.google.com/youtube/answer/16533387）
- 原文摘要：watch history 列為觀眾個人化訊號，YouTube 推薦系統據此判斷觀眾興趣並進行個人化推薦

**Creator Action Layer**

這是什麼意思：
YouTube 系統記錄每位觀眾過去看過什麼，用來推測他接下來可能想看什麼。你的影片能不能被推薦給某人，很大程度取決於那個人過去看過的內容，而不只是你的影片本身有多好。

內容該怎麼做：
- 頻道主題要清晰一致，讓系統能把你的影片推薦給「看過類似內容的人」
- 跨主題太雜的頻道，系統難以判斷要把你推給誰
- 系列影片比單支影片更容易累積「同類觀眾的觀看歷史」

該注意什麼：
- 不要為了追熱點而大幅偏離頻道定位，短期播放量可能上升，但受眾匹配會變亂
- 觀看歷史是平台側的資料，創作者無法直接控制，只能透過內容定位間接影響

**Tool Mapping Layer**
- Screenwriter：`Audience Selector`（思考目標受眾的觀看歷史長什麼樣）
- v6.5 欄位：`target_audience`
- 教材定位：頻道定位一致性的重要性

---

## search behavior｜搜尋行為

**Source Layer**
- 可信度：`official`
- 來源：YouTube Help（answer/16533387 + answer/11914225）
- 原文摘要：search behavior 列為觀眾個人化訊號；search & discovery 說明搜尋意圖影響推薦

**Creator Action Layer**

這是什麼意思：
觀眾在 YouTube 搜尋框輸入的關鍵字，代表明確的「想找什麼」的意圖。YouTube 搜尋推薦會把這個意圖與影片標題、描述、字幕進行比對。

內容該怎麼做：
- 標題要包含觀眾「真的會搜尋的詞彙」，不是你覺得聰明的詞
- 可以用 YouTube 搜尋欄自動補全功能，觀察真實搜尋詞
- 描述前兩行要自然包含核心關鍵詞，不要堆砌

該注意什麼：
- 搜尋意圖對齊是長影片的核心策略，Shorts 的搜尋邏輯不同，更偏向演算法推薦
- 不要只為了 SEO 把標題寫得生硬，要同時考慮「真人看到這個標題會不會想點」

**Tool Mapping Layer**
- Screenwriter tag：`Intent-Matching`
- v6.5 欄位：`script_design.search_intent`
- 教材定位：標題設計的搜尋意圖對齊原則

---

## watch time｜觀看時間

**Source Layer**
- 可信度：`official`
- 來源：YouTube Help（answer/16533387）+ YouTube Blog（blog.youtube/inside-youtube/on-youtubes-recommendation-system）
- 原文摘要：watch time 列為影片表現訊號，是 YouTube 評估影片是否值得繼續推薦的核心依據之一

**Creator Action Layer**

這是什麼意思：
每次觀看中，觀眾實際停留在你影片的時間總量。YouTube 用這個判斷「這支影片有沒有讓觀眾覺得值得看」。

內容該怎麼做：
- 影片結構要緊湊，每個段落都要有新資訊或新進展
- 前 30 秒必須讓觀眾覺得「值得繼續看」
- 中段不要重複已說過的內容，避免觀眾提前離開

該注意什麼：
- watch time 不等於影片越長越好，3 分鐘被看完 90% 的影片，可能比 20 分鐘只看 20% 更有價值
- 不要用人工拉長的方式增加時間，例如過長片頭、重複說明、無意義過場

**Tool Mapping Layer**
- Screenwriter tag：`Retention-Bridge`（中段結構設計）
- v6.5 欄位：`history_tracking.watch_time`
- 教材定位：觀看時間的品質比長度更重要

---

## average view duration + average percentage viewed｜平均觀看時長 + 平均觀看比例

**Source Layer**
- 可信度：`official`
- 來源：YouTube Help（answer/11914225）
- 原文摘要：average view duration 與 average percentage viewed 列於 Shorts 指標說明，反映觀眾投入程度

**Creator Action Layer**

這是什麼意思：
- average view duration：平均每位觀眾看了幾分幾秒
- average percentage viewed：平均看了影片的幾 %

兩個指標合起來告訴你：觀眾願意投入多少時間，以及你的影片長度是否合適。

內容該怎麼做：
- 若 average percentage viewed 偏低，通常是影片太長、中段節奏太慢，或前段承諾與內容落差太大
- Shorts 的這兩個指標特別重要，前 1–3 秒要能讓人停下來

該注意什麼：
- 這兩個指標是發布後才能觀察的數據，腳本設計時要預測「哪裡可能掉人」
- 不要把「平均觀看時長高」解讀為一定代表滿意，有可能是觀眾在等待承諾被兌現

**Tool Mapping Layer**
- Screenwriter tag：`Retention-Bridge`（標記留存斷層點）
- v6.5 欄位：`history_tracking.avg_view_duration` / `history_tracking.avg_pct_viewed`
- 教材定位：用留存曲線找腳本的問題段落

---

## click / CTR｜點擊率

**Source Layer**
- 可信度：`official`
- 來源：YouTube Blog（blog.youtube/inside-youtube/on-youtubes-recommendation-system）
- 原文摘要：clicks 列為影片表現訊號，系統展示影片後觀眾是否點擊是判斷標題縮圖吸引力的依據

**Creator Action Layer**

這是什麼意思：
系統把你的影片展示給某人後，那個人有沒有點擊進去看。CTR 高代表標題和縮圖有吸引力，但這只是第一關。

內容該怎麼做：
- 縮圖要清楚傳達「看這支你會得到什麼」
- 標題要讓人有點進去的理由，但不能過度承諾
- 縮圖與標題要互補，不要說同樣的事

該注意什麼：
- CTR 高但 watch time 低、滿意度低，YouTube 系統會認為標題縮圖在「騙點擊」，後續推薦會下降
- 不要只追求高 CTR，要確保點進去的觀眾不會失望

**Tool Mapping Layer**
- Screenwriter tag：`CTR-Promise`（確保標題縮圖承諾在影片中被兌現）
- v6.5 欄位：`history_tracking.ctr`
- 教材定位：CTR 是入口，不是終點；高 CTR 低滿意度比低 CTR 更傷害長期推薦

---

## likes / dislikes｜按讚 / 不喜歡

**Source Layer**
- 可信度：`official`
- 來源：YouTube Help（answer/16533387）+ YouTube Blog
- 原文摘要：likes / dislikes 同時列於個人化訊號與影片表現訊號，是內容情感反應的基本訊號

**Creator Action Layer**

這是什麼意思：
觀眾對影片的基本情感回饋。按讚代表正向共鳴，不喜歡代表負向反應。兩者都是系統判斷內容品質的訊號之一。

內容該怎麼做：
- 設計能引發共鳴的觀點或資訊，自然帶動按讚
- 結尾可以輕描淡寫提醒「如果有幫助可以按讚」，但不要強迫或過度要求

該注意什麼：
- 按讚是基本盤訊號，不是推播的決定因素
- 不要說「按讚沒有用」，也不要說「按讚最重要」，兩者都不準確
- 不喜歡比例高，要回頭檢查標題是否誤導受眾

**Tool Mapping Layer**
- v6.5 欄位：`history_tracking.likes` / `history_tracking.dislikes`
- 教材定位：按讚是基本盤訊號，不是主要變現決策依據

---

## shares｜分享

**Source Layer**
- 可信度：`official`
- 來源：YouTube Help（answer/16533387）
- 原文摘要：shares 列為影片表現訊號，代表內容傳播價值

**Creator Action Layer**

這是什麼意思：
觀眾主動把你的影片分享給別人，代表內容有「值得讓別人看到」的傳播價值。

內容該怎麼做：
- 設計有「為什麼值得分享」的觀點，例如反常識的結論、有用的工具清單、打動人的故事
- 分享通常發生在內容給觀眾帶來「我要讓朋友知道這個」的感受時

該注意什麼：
- 不要說「分享保證推播」，分享是訊號之一，不是開關
- 分享數高但 watch time 低，代表觀眾只是傳連結，沒有真正看完

**Tool Mapping Layer**
- Screenwriter tag：`Satisfaction-Proof`（結尾設計有分享動機的總結）
- v6.5 欄位：`history_tracking.shares`
- 教材定位：分享是傳播價值的訊號，不是推播保證

---

## comments｜留言

**Source Layer**
- 可信度：`official`
- 來源：YouTube Help（answer/16533387）
- 原文摘要：comments 列為影片表現訊號，反映內容引發討論的能力

**Creator Action Layer**

這是什麼意思：
觀眾在影片下方留言，代表內容引發了足夠的反應，讓人想說點什麼。

內容該怎麼做：
- 結尾提出一個開放式問題，讓觀眾有回應的理由
- 問題要與影片內容真實相關，不要只是「你覺得呢？」這種無意義的問法
- 可以在留言區主動回覆，增加後續互動深度

該注意什麼：
- 不要用「留言送免費資源」這類互動誘餌
- 留言數量不等於留言品質，真實有意義的討論比單字回覆更有價值

**Tool Mapping Layer**
- Screenwriter：`CTA Generator`（YouTube 版本包含留言討論問題生成）
- v6.5 欄位：`history_tracking.comments`
- 教材定位：留言是深度互動訊號，設計要引發真實對話

---

## not interested｜不感興趣

**Source Layer**
- 可信度：`official`
- 來源：YouTube Help（answer/16533387 + answer/11914225）
- 原文摘要：not interested 列為個人化訊號與 Shorts 負向訊號，觀眾主動標記後影響後續推薦

**Creator Action Layer**

這是什麼意思：
觀眾主動點選「不感興趣」，是比 dislike 更強的負向訊號，代表觀眾不只是不喜歡這支影片，而是不想再看這類內容。

內容該怎麼做：
- 確保標題縮圖與內容一致，避免因誤導引發負向回饋
- 確保內容定位清晰，減少被推薦給不相關受眾的機率

該注意什麼：
- 標題黨和過度承諾是引發 not interested 的常見原因
- not interested 對帳號的長期推薦有累積影響

**Tool Mapping Layer**
- Screenwriter：`Algorithm Fit Check`（受眾匹配檢查）
- v6.5 欄位：`audit.warnings`（標記可能引發 not interested 的設計問題）
- 教材定位：負向訊號與正向訊號同樣重要

---

## survey responses｜滿意度調查

**Source Layer**
- 可信度：`official`
- 來源：YouTube Help（answer/16533387）+ YouTube Blog
- 原文摘要：survey responses 列為個人化訊號；YouTube Blog 提及 viewer satisfaction 是推薦系統的評估依據

**Creator Action Layer**

這是什麼意思：
YouTube 會向部分觀眾發送滿意度調查，直接問他們對剛看完的影片的評價。這是系統直接收集「觀眾是否真的覺得有價值」的機制，不依賴行為推測。

內容該怎麼做：
- 讓觀眾在看完後覺得「問題被解決了」或「學到了東西」
- 內容要有實質幫助，而非只是吸引點擊後讓人失望

該注意什麼：
- 這個訊號是平台直接問觀眾，創作者無法操控
- 它代表 YouTube 不只看行為指標，也直接問人的感受，讓觀眾真的有收穫比讓觀眾繼續看更重要

**Tool Mapping Layer**
- Screenwriter tag：`Satisfaction-Proof`（確保結尾讓觀眾覺得問題被解決）
- 教材定位：滿意度是比 watch time 更難偽造的訊號，是內容設計的最終目標

---

## engaged views（Shorts）｜有效觀看

**Source Layer**
- 可信度：`official`
- 來源：YouTube Help（answer/10059070）+ YouTube Help Community（thread/333869549）
- 原文摘要：Shorts views 與 engaged views 有明確差異；YPP 分潤仍看 engaged views；2025/3/31 起 views 只要開始播放即計算，無最低觀看時間要求

**Creator Action Layer**

這是什麼意思：
YouTube Shorts 有兩種「觀看」：
- 一般 views：只要影片開始播放就計算
- engaged views：觀眾真正投入觀看的次數，是 YPP 分潤的計算依據

兩者不同，engaged views 代表觀眾不只是滑過去，而是真的停下來看。

內容該怎麼做：
- Shorts 前 1–3 秒要有強力 Hook，讓觀眾從滑過變成停下來
- 內容密度要高，讓觀眾有理由看完整支
- 不要做讓觀眾「滑過去就算」的內容

該注意什麼：
- views 數字的增加不代表 engaged views 也在增加，兩者要分開追蹤
- 若目標是 YPP 變現，要優化 engaged views 而非總播放數

**Tool Mapping Layer**
- Screenwriter tag：`Engaged-View-Check`（Shorts 模式自動啟用）
- v6.5 欄位：`history_tracking.shorts_engaged_views`
- 教材定位：Shorts 的 views 和 engaged views 是兩個不同指標，不能混用

---

## topic interest / competition / seasonality｜外部因素

**Source Layer**
- 可信度：`official`
- 來源：YouTube Help（answer/11914225）
- 原文摘要：topic interest、competition、seasonality 列為外部因素，影響影片被推薦的機會

**Creator Action Layer**

這是什麼意思：
這三個因素是 YouTube 系統考量的「外部環境」，不是你影片本身的表現，而是你所在的話題環境：
- topic interest：這個話題現在有多少人感興趣
- competition：同類型影片有多少競爭
- seasonality：這個話題是否有季節性熱度

內容該怎麼做：
- 選題時考慮話題熱度與競爭程度的平衡：熱門話題競爭大，利基話題競爭小但受眾也小
- 提前規劃季節性選題，例如年末回顧、特定節日相關內容

該注意什麼：
- 這三個因素不是創作者直接控制的，是環境變數
- 不要因為競爭大就放棄，也不要因為話題熱就忽略內容品質

**Tool Mapping Layer**
- Screenwriter：選題建議模組（提示創作者考慮外部環境因素）
- 教材定位：選題框架的外部環境評估

---

## 下一支影片 / 播放清單續看路徑

**Source Layer**
- 可信度：`practical_inference`
- 來源：無直接官方來源
- 說明：屬創作者執行策略，非 YouTube 官方列出的推播訊號。邏輯上觀眾繼續留在頻道對整體 watch time 有正面效果，但不是官方確認的直接推播依據

**Creator Action Layer**

這是什麼意思：
在影片結尾設計引導觀眾繼續看相關影片的路徑，是創作者的執行策略。

內容該怎麼做：
- 結尾說清楚「下一支影片在哪裡、為什麼要看」
- 播放清單設計要有邏輯順序，讓觀眾知道「這是一套內容」

該注意什麼：
- 這是實務推論，不能寫成「設計播放清單保證加權」
- 如果影片本身讓觀眾失望，再多的結尾引導也沒用

**Tool Mapping Layer**
- Screenwriter tag：`Next-Video-Path`（腳本結尾設計）
- 教材定位：標示為「實務策略」，非官方推播訊號

---

# INSTAGRAM

---

## 不同版位不同排序系統｜Feed / Stories / Explore / Reels / Search

**Source Layer**
- 可信度：`official`
- 來源：Instagram Ranking Explained（about.instagram.com/blog/announcements/instagram-ranking-explained）
- 原文摘要：IG 不是單一演算法；Feed、Stories、Explore、Reels、Search 各自有不同排序系統

**Creator Action Layer**

這是什麼意思：
Instagram 不是一個演算法，而是五個不同的排序系統同時運作。你在 Reels 的成效好，不代表在 Explore 或 Feed 也會被推薦。各版位的推薦邏輯不同：
- Reels：拉新，觸及陌生人
- Explore：陌生受眾發現你的入口之一
- Feed：維持與既有追蹤者的關係
- Stories：深化信任，做承接
- Search：有意圖的主動尋找

內容該怎麼做：
- 不要用同一支影片、同一個策略應對所有版位
- Reels 要優先設計給陌生人看，而不是只給既有粉絲看
- Stories 內容設計要不同於 Reels，更偏向對話與承接

該注意什麼：
- 很多人做了 Reels 成效不好，以為是「演算法針對」，其實是版位策略搞混了
- 不同版位的數據不能直接比較，要分開看

**Tool Mapping Layer**
- Screenwriter：`Platform Selector`（選擇 Instagram 後進一步選擇版位）
- v6.5 欄位：`platform`（`instagram_reels` / `instagram_stories` / `instagram_feed`）
- 教材定位：五個版位各自獨立，策略要分開設計

---

## watch time / average watch time｜觀看時間

**Source Layer**
- 可信度：`official`
- 來源：Instagram Creators（creators.instagram.com/blog/helping-creators-of-all-sizes-break-through）
- 原文摘要：Reels 訊號包含 watch time，是系統判斷是否繼續擴大推薦的依據之一

**Creator Action Layer**

這是什麼意思：
Reels 被推薦的核心訊號之一。系統觀察觀眾實際停留在你的 Reels 上多長時間，用來判斷這支影片是否值得繼續推給更多人。

內容該怎麼做：
- 第一秒就要讓人停下來，不能用 Logo、片頭動畫或無意義的開場浪費時間
- 前 3 秒要讓陌生人知道「這支影片是給我看的」
- 整支 Reels 的資訊密度要夠，讓觀眾沒有理由提前離開

該注意什麼：
- 不要為了看起來有內容而拉長 Reels 的時間，留存斷層比影片短更傷害推薦
- Reels 平均長度建議控制在觀眾真正能看完的範圍內

**Tool Mapping Layer**
- Screenwriter tag：`Watch-Time-Hook`（第一秒設計強制檢查）
- v6.5 欄位：`history_tracking.avg_watch_time`
- 教材定位：第一秒是 Reels 留存的關鍵門檻

---

## retention｜留存率

**Source Layer**
- 可信度：`official`
- 來源：Instagram Creators（helping-creators-of-all-sizes-break-through）
- 原文摘要：Reels 訊號包含 retention，反映內容在整個播放過程中的持續吸引力

**Creator Action Layer**

這是什麼意思：
觀眾從頭看到結尾的比例。留存率反映你的 Reels 在整個播放過程中是否持續吸引觀眾，而不只是開頭幾秒。

內容該怎麼做：
- 每隔 5–10 秒要有新的資訊、新的畫面切換或新的節奏變化
- 不要讓中段「空轉」，例如說廢話、重複剛才說過的話
- 可以用「預告」的方式讓觀眾想繼續看：「最後一個方法是大多數人都忽略的...」

該注意什麼：
- 留存率斷崖式下降通常發生在：開頭承諾與內容不符、中段節奏突然變慢、過渡畫面太長
- 留存率是發布後才能看的數據，但腳本設計時可以預測哪裡可能掉人

**Tool Mapping Layer**
- Screenwriter tag：`Retention-Cut`（分鏡設計標記每個節奏切換點）
- v6.5 欄位：`history_tracking.retention_rate`
- 教材定位：留存率是腳本設計品質的間接指標

---

## shares｜分享

**Source Layer**
- 可信度：`official`
- 來源：Instagram Creators（helping-creators-of-all-sizes-break-through）
- 原文摘要：Reels 訊號包含 shares，代表內容的社交傳播價值

**Creator Action Layer**

這是什麼意思：
觀眾把你的 Reels 分享出去，可能是傳給朋友、貼到自己的限動、或傳到群組。這是 Instagram 判斷內容「社交價值」的重要訊號。分享代表觀眾覺得：「這個值得讓別人看到。」

內容該怎麼做：
- 設計明確的「send-worthy point」：想清楚這支影片在哪一刻會讓觀眾想傳給朋友
- 常見有效設計：
  - 共鳴型：「你一定有這種感覺」→ 觀眾想傳給有同樣困擾的朋友
  - 實用型：「這個方法你朋友也該知道」→ 傳播有用資訊
  - 娛樂型：「這太準了」→ 娛樂性傳播

該注意什麼：
- 分享數高但觀看時間低，代表人們傳了連結但沒看完
- 不要說「分享保證推播」，分享是訊號之一，不是開關

**Tool Mapping Layer**
- Screenwriter tag：`Send-Worthy`（腳本中明確標出 send-worthy point 的位置）
- v6.5 欄位：`script_design.send_worthy_point` / `history_tracking.shares`
- 教材定位：分享是社交傳播力的核心訊號，腳本要主動設計

---

## likes｜按讚

**Source Layer**
- 可信度：`official`
- 來源：Instagram Creators（helping-creators-of-all-sizes-break-through）
- 原文摘要：Reels 訊號包含 likes，是基本情感回饋訊號之一

**Creator Action Layer**

這是什麼意思：
觀眾對你的 Reels 按讚，代表基本的正向共鳴。按讚是 Reels 推薦訊號之一，但在訊號組合中，它的角色是「基本盤」，不是主要推播決定因素。

內容該怎麼做：
- 設計能引發共鳴的觀點、情感或有用資訊，按讚會自然發生
- 結尾可以輕描淡寫說「覺得有用的話給個讚」，但不要過度強調

該注意什麼：
- 不要說「按讚沒有用」，它是訊號之一
- 不要說「按讚是最重要的」，watch time、retention、shares 在多數分析中被認為更能反映傳播潛力
- 按讚容易被創作者過度關注，因為它是最即時可見的數字，但它反映的是共鳴，不是傳播力

**Tool Mapping Layer**
- v6.5 欄位：`history_tracking.likes`
- 教材定位：按讚是基本盤訊號，不是主要變現決策依據

---

## comments｜留言

**Source Layer**
- 可信度：`official`
- 來源：Instagram Creators（helping-creators-of-all-sizes-break-through）
- 原文摘要：Reels 訊號包含 comments，反映內容引發互動反應的能力

**Creator Action Layer**

這是什麼意思：
觀眾在你的 Reels 下留言，代表內容引發了足夠的反應，讓人想說點什麼。留言是比按讚更深度的互動訊號。

內容該怎麼做：
- 結尾提一個簡單的開放式問題，讓觀眾有回應的理由
- 例如：「你現在用的是哪個方法？」「你遇過這種情況嗎？」
- 在留言區主動回覆前幾則留言，可以帶動後續互動

該注意什麼：
- 問題要真實有意義，不要只是「你覺得呢？」這種過於泛泛的提問
- 不要用「留言送禮物」的誘餌式設計，這屬於 engagement bait

**Tool Mapping Layer**
- Screenwriter：`CTA Generator`（Instagram 版本包含留言問題生成）
- v6.5 欄位：`history_tracking.comments`
- 教材定位：留言設計要能引發真實對話，不是數字堆砌

---

## audience matching｜受眾匹配

**Source Layer**
- 可信度：`official`
- 來源：Instagram Creators（helping-creators-of-all-sizes-break-through）
- 原文摘要：Reels 訊號包含 audience matching，系統據此把內容推薦給最可能感興趣的受眾
- 注意：來源文件描述為「匹配可能感興趣的受眾」，未定義為可量化的完整公式

**Creator Action Layer**

這是什麼意思：
Instagram 系統會判斷你的內容適合推薦給哪類受眾，並把它推給「最可能感興趣的人」。如果你的內容定位模糊，系統就很難找到對的受眾。

內容該怎麼做：
- 內容定位要清晰：這支 Reels 是給誰看的，要在前 3 秒就讓對的人知道
- 例如：「如果你是做個人品牌的...」這類開頭幫助系統和觀眾同時定位
- 頻道整體定位一致，比單支影片表現更重要

該注意什麼：
- 不要把 audience matching 解讀成「系統有一個固定公式」，來源文件只說「匹配感興趣的受眾」，沒有給出可量化的定義
- 受眾匹配差的常見症狀：觀看數高但追蹤者轉換低

**Tool Mapping Layer**
- Screenwriter：`Audience Selector`（設定目標受眾描述）
- v6.5 欄位：`target_audience`
- 教材定位：受眾定位是 Reels 推薦效率的前提，不是事後調整的工具

---

## sends per reach｜每次觸及中的私訊分享率

**Source Layer**
- 可信度：`high_confidence`
- 來源：The Verge（theverge.com/2024/8/7）引述 Mosseri 說法
- 注意：來源為媒體報導引述平台負責人說法，非官方文件，教材中需標示

**Creator Action Layer**

這是什麼意思：
每 100 個看到你 Reels 的人中，有幾個人把它私訊傳給朋友。這個比率越高，代表你的內容有越強的「值得傳給別人」的驅動力。Mosseri 公開建議創作者觀察這個指標，因為它比按讚更能反映內容的真實傳播價值。

內容該怎麼做：
- 設計明確的 send-worthy point
- 思考：什麼樣的內容讓人在看完後第一反應是「我要傳給某某人」？
- 共鳴、實用、娛樂是最常見的傳播驅動力

該注意什麼：
- 這個指標在 Instagram 後台不一定直接顯示，需要自行計算或觀察相對變化
- 這是 high_confidence 說法，教材中需標示來源為 Mosseri 媒體說法，非官方文件

**Tool Mapping Layer**
- v6.5 欄位：`history_tracking.sends_per_reach`（標示來源性質）
- Screenwriter tag：`Send-Worthy`
- 教材定位：標示為「Mosseri 公開說法，非官方文件；與 shares 欄位一起觀察」

---

## originality｜原創性

**Source Layer**
- 可信度：`official`
- 來源：Instagram Original Content Guidelines（creators.instagram.com/original-content-guidelines）+ Instagram Creators（recommendations-and-originality）
- 原文摘要：原創性是推薦資格的前提條件，非加分項；低努力修改、浮水印、速度變更、只標註原作者等不算高品質原創；原創內容在推薦中會取代複製版本

**Creator Action Layer**

這是什麼意思：
Instagram 明確把「原創性」列為推薦資格的前提條件，不是加分項。沒有原創性，就沒有資格進入推薦池。以下行為官方明確說明「不算高品質原創」：
- 搬運其他平台影片（尤其是帶有浮水印的）
- 低努力修改他人內容
- 只是加快或減慢影片速度
- 只標註原作者但沒有實質新增價值

內容該怎麼做：
- 即使用 AI 輔助生成，也要加入自己的觀點、聲音、真實案例
- 不直接搬運 TikTok、YouTube 的影片，即使你有版權
- 加入「只有你能說的東西」：個人經驗、特定案例、你的觀點

該注意什麼：
- 原創性是門檻，過了才能被推薦，但過了不代表保證推薦
- AI 生成的罐頭內容如果沒有人工調整，很容易被判斷為「低品質再製」

**Tool Mapping Layer**
- Screenwriter tag：`Originality-Check`（腳本審核最後一項強制檢查）
- v6.5 欄位：`audit.originality_check`
- 教材定位：原創性是資格問題，不是加分問題；AI 生成要有人工調整層

---

## recommendation eligibility｜推薦資格

**Source Layer**
- 可信度：`official`
- 來源：Instagram Creators（instagram-recommendations-eligibility-tips-creators）
- 原文摘要：內容要符合推薦資格；避免不利推薦的低品質或不合規內容

**Creator Action Layer**

這是什麼意思：
Instagram 有一套推薦資格審核機制，決定你的內容是否能進入 Explore、Reels 推薦池。不符合資格的內容，即使品質很好，也不會被推薦給陌生人。常見不符合資格的原因：違反社群守則、包含誤導性內容、低品質搬運、帶有浮水印。

內容該怎麼做：
- 定期確認帳號的推薦資格狀態（可在帳號設定中查看）
- 避免任何可能觸發資格限制的內容類型
- 新帳號要特別注意，早期發布的內容品質會影響後續推薦資格

該注意什麼：
- 推薦資格是二元的：有或沒有，不是「部分有」
- 如果發現觸及率突然大幅下降，要先確認是否有推薦資格問題

**Tool Mapping Layer**
- Screenwriter：`Algorithm Fit Check`（推薦資格確認項目）
- v6.5 欄位：`audit.recommendation_eligibility`
- 教材定位：推薦資格是所有策略的前提，要定期確認

---

## IG Reels Chaining AI system｜Reels 連鎖推薦 AI 系統

**Source Layer**
- 可信度：`official`
- 來源：Meta Transparency Center（transparency.meta.com/features/explaining-ranking/ig-reels-chaining）
- 原文摘要：IG Reels Chaining AI system 會預測使用者最可能感興趣的 Reels 並排序

**Creator Action Layer**

這是什麼意思：
Instagram Reels 有一個獨立的 AI 系統，專門負責「看完一支 Reels 後，接下來推薦哪支」。這個系統會預測使用者最可能感興趣的下一支 Reels，並決定播放順序。

內容該怎麼做：
- 頻道內容定位一致，讓 AI 系統能把你的多支 Reels 歸類為「相關內容」
- 如果你有多支 Reels，它們之間應該有主題關聯

該注意什麼：
- 這個機制代表主題一致的多支 Reels，可能更容易在連鎖推薦中出現，但這是系統邏輯推論，而非保證機制，不代表一支爆了就必然帶動其他影片
- 反過來，如果你的 Reels 主題雜亂，系統很難把你的內容歸類，連鎖推薦的機率也會降低

**Tool Mapping Layer**
- 教材概念：頻道定位一致性的重要性
- Screenwriter：`Audience Selector`（確保每支 Reels 的受眾定位一致）

---

## views｜觀看數

**Source Layer**
- 可信度：`high_confidence`
- 來源：The Verge（theverge.com/2024/8/7）引述 Mosseri 說法
- 注意：來源為媒體報導，非官方文件

**Creator Action Layer**

這是什麼意思：
Mosseri 公開說法中，views 成為 Instagram 的主要觀察指標，取代過去以按讚為主的評估方式。views 包含所有看過這支影片的次數，不限追蹤者。

內容該怎麼做：
- 把 views 當作「觸及廣度」的基本觀察指標
- 高 views 但低 sends per reach 或低 retention，代表吸引了人但沒有留住人

該注意什麼：
- 這是 Mosseri 的媒體說法，要標示來源性質
- views 是結果數字，不是設計目標，要看它背後的 watch time 和 retention 才有意義

**Tool Mapping Layer**
- v6.5 欄位：`history_tracking.views`
- 教材定位：標示為「Mosseri 公開說法；views 是結果，要配合 watch time / retention 一起觀察」

---

## like rate｜按讚率

**Source Layer**
- 可信度：`high_confidence`
- 來源：無官方文件直接支撐，見於 Mosseri 相關說法
- 注意：需標示為高可信說法，非官方文件

**Creator Action Layer**

這是什麼意思：
按讚率是按讚數除以觸及人數的比例，反映「看到這支影片的人中，有多少比例按讚」。比純按讚數更能反映內容的相對吸引力。

內容該怎麼做：
- 觀察哪類主題或格式的按讚率較高，作為後續選題依據
- 按讚率低但觀看數高，通常代表內容吸引了不相關受眾

該注意什麼：
- 這個指標沒有官方文件直接列為推薦訊號，屬於高可信推論
- 教材中要清楚標示：「業界常用觀察指標，非官方正式推播訊號」

**Tool Mapping Layer**
- v6.5 欄位：`history_tracking.like_rate`（計算欄位，需標示來源性質）
- 教材定位：輔助觀察指標，非官方推播訊號

---

## Trial Reels｜試播 Reels

**Source Layer**
- 可信度：`high_confidence`
- 來源：The Verge（theverge.com/2024/12/10）
- 注意：來源為媒體報導，非官方文件；功能細節請以 Instagram 官方說明為準

**Creator Action Layer**

這是什麼意思：
Trial Reels 是 Instagram 的功能，讓創作者可以把一支 Reels 先推給非追蹤者測試，觀察陌生受眾的反應，再決定是否正式發布。測試期間觀察的訊號：views、likes、shares、comments。

內容該怎麼做：
- 用 Trial Reels 測試新主題或新格式，在正式發布前先確認陌生受眾的反應
- 如果 Trial 期間表現好，可以正式轉為一般 Reels 擴大推薦

該注意什麼：
- 來源為媒體報導，細節可能有所變化
- Trial Reels 的觀察訊號與一般 Reels 相同，但測試對象限定為非追蹤者

**Tool Mapping Layer**
- 教材策略單元：Trial Reels 作為新主題測試工具
- 標示：來源為媒體報導，功能細節請以 Instagram 官方說明為準

---

## Profile visits｜個人頁訪問

**Source Layer**
- 可信度：`practical_inference`
- 來源：無官方來源
- 注意：來源文件明確說明為「變現承接路徑觀察指標」，非官方確認的 Reels 推播訊號

**Creator Action Layer**

這是什麼意思：
觀眾看完 Reels 後點進你的個人頁，是從「陌生觀眾」進入「有興趣的潛在追蹤者或客戶」的第一步。這是變現漏斗中的重要承接節點。

內容該怎麼做：
- 結尾設計引導觀眾點進個人頁的 CTA：「更多資源在個人頁」、「連結在個人頁」
- 個人頁要能承接從 Reels 點進來的陌生觀眾：3 秒內讓人知道「你是誰、能幫他什麼、下一步是什麼」

該注意什麼：
- Profile visits 是變現漏斗指標，不是演算法推播訊號
- 如果 Reels 觀看數高但 profile visits 低，通常是 CTA 設計不夠清楚，或內容與個人頁定位不一致

**Tool Mapping Layer**
- Screenwriter tag：`Profile-CTA`（確保結尾有引導個人頁的設計）
- v6.5 欄位：`history_tracking.profile_visits`（標示為變現漏斗指標，非推播訊號）
- 教材定位：標示為「實務推論：變現承接，非官方推播訊號」

---

## DM｜私訊

**Source Layer**
- 可信度：`practical_inference`
- 來源：無官方來源
- 注意：高意向轉化的變現承接指標，非官方確認的推播訊號

**Creator Action Layer**

這是什麼意思：
觀眾主動私訊你，是高意向轉化的訊號，代表對方已從「路過的陌生人」變成「主動聯繫的潛在客戶」。這是 Instagram 變現漏斗中最接近成交的節點之一。

內容該怎麼做：
- 設計自然的私訊誘因：「私訊我『關鍵字』我傳你完整清單」
- 關鍵字型私訊引導比「歡迎私訊我」更有效，因為降低了觀眾的行動門檻
- 私訊承接要有後續流程：不能讓人傳訊息後沒有回應

該注意什麼：
- DM 是高意向指標，但在推播機制中的角色是實務推論
- 私訊引導要自然，不能太強迫，否則會讓觀眾有被推銷的感覺

**Tool Mapping Layer**
- Screenwriter tag：`DM-Bridge`（設計引發私訊的 CTA 路徑）
- v6.5 欄位：`history_tracking.dm_count`（標示為變現漏斗指標）
- 教材定位：標示為「實務推論：高意向轉化指標，非官方推播訊號」

---

## Stories 回覆｜限動回覆

**Source Layer**
- 可信度：`practical_inference`
- 來源：無官方來源
- 注意：信任深化的互動指標，非官方確認的推播訊號

**Creator Action Layer**

這是什麼意思：
觀眾對你的 Stories 直接回覆，是比按讚更深度的互動，代表對方願意主動與你對話。在信任建立的層面上，Stories 回覆是從「觀眾」變成「熱情粉絲」的重要節點。

內容該怎麼做：
- 設計「值得回應」的 Stories 內容：投票、問答、填空、真實提問
- 把 Reels 的話題延伸到 Stories，讓看過 Reels 的人有繼續互動的理由
- 回覆每一則 Stories 回覆，建立一對一對話感

該注意什麼：
- Stories 是信任深化的工具，不是拉新的工具
- 不要把 Stories 當廣告版位，它更適合做「私下聊天」的感覺

**Tool Mapping Layer**
- 教材定位：標示為「實務推論：信任承接工具，非官方推播訊號」
- 變現漏斗設計中的「信任深化」節點

---

# FACEBOOK

---

## Facebook Reels AI system｜Reels 人工智慧排序系統

**Source Layer**
- 可信度：`official`
- 來源：Meta Transparency Center（transparency.meta.com/features/explaining-ranking/fb-reels）
- 原文摘要：Facebook Reels AI system 會決定哪些 Reels 顯示、順序如何，依據預測使用者最可能感興趣的內容

**Creator Action Layer**

這是什麼意思：
Facebook Reels 有一個獨立的 AI 系統，專門決定哪些 Reels 出現在哪些使用者面前、順序如何。核心邏輯是：預測這個使用者最可能對哪支 Reels 感興趣，然後把它排到前面。它與 Instagram Reels、Facebook Feed、Facebook Video 是三個不同的系統，各自獨立運作。

內容該怎麼做：
- 把 Facebook Reels 定位為「讓陌生人發現你」的工具
- 內容要對目標受眾有明確的「這是給你看的」訊號，幫助 AI 系統判斷應該推給誰
- 不要假設 Facebook 粉絲頁的粉絲會自動看到你的 Reels，AI 系統會獨立判斷

該注意什麼：
- Facebook Reels AI system 和 Facebook Feed AI system 是不同系統，同一支內容在兩個版位的表現可能完全不同
- 不要把 Instagram Reels 的策略直接套用到 Facebook Reels

**Tool Mapping Layer**
- Screenwriter：`Platform Selector`（選擇 Facebook 後區分 Reels / Feed / Video 版位）
- v6.5 欄位：`platform`（`facebook_reels` / `facebook_feed` / `facebook_video`）
- 教材定位：Facebook 三個版位各自獨立，策略要分開設計

---

## Facebook Video AI system｜影片頁面人工智慧排序系統

**Source Layer**
- 可信度：`official`
- 來源：Meta Transparency Center（transparency.meta.com/features/explaining-ranking/fb-video）
- 原文摘要：Facebook Video AI system 會決定 Video tab 中哪些影片出現與排序

**Creator Action Layer**

這是什麼意思：
Facebook 的 Video tab 有獨立的 AI 排序系統，決定哪些影片出現在使用者的影片瀏覽頁面。這個版位通常是使用者主動進入「看影片」狀態時使用的，與被動刷到 Reels 的情境不同。

內容該怎麼做：
- 較長的影片、深度內容更適合出現在 Video tab
- 如果你有長影片內容，要單獨考慮 Video tab 的策略，不能只依賴 Reels
- 影片標題和縮圖在 Video tab 同樣重要，因為使用者是主動選擇要看哪支

該注意什麼：
- Video tab 的受眾是「主動想看影片」的人，比被動刷 Reels 的人更有耐心
- 這個版位適合教學型、深度分析型的長影片

**Tool Mapping Layer**
- Screenwriter：`Platform Selector`（Facebook Video 模式）
- v6.5 欄位：`platform`（`facebook_video`）
- 教材定位：三個 Facebook 版位的定位差異

---

## Facebook Feed AI system｜動態消息人工智慧排序系統

**Source Layer**
- 可信度：`official`
- 來源：Meta Transparency Center（transparency.meta.com/features/explaining-ranking/fb-feed）
- 原文摘要：Facebook Feed AI system 會預測使用者覺得最有價值、最相關的貼文並排序

**Creator Action Layer**

這是什麼意思：
Facebook Feed 的 AI 系統預測「使用者覺得最有價值、最相關的貼文」，並依此排序。這個版位混合了朋友的貼文、追蹤的粉絲頁內容、以及 AI 推薦的陌生內容。

內容該怎麼做：
- Feed 貼文要設計成「讓既有追蹤者覺得有價值」，同時有機會被推薦給陌生人
- 文字型貼文在 Feed 仍然有效，不一定都要做影片
- 貼文開頭的前兩行非常重要，因為 Feed 只顯示前兩行，要讓人有理由點「查看更多」

該注意什麼：
- Feed 的排序邏輯與 Reels 不同，不要用同一套指標評估兩個版位
- 朋友的互動（留言、分享）對 Feed 的擴散有明顯影響，這是 Feed 與 Reels 最大的差異之一

**Tool Mapping Layer**
- Screenwriter：`Platform Selector`（Facebook Feed 模式）
- v6.5 欄位：`platform`（`facebook_feed`）
- 教材定位：Feed 與 Reels 是不同邏輯，要分開設計

---

## Facebook Feed Recommendations AI system｜動態消息推薦系統

**Source Layer**
- 可信度：`official`
- 來源：Meta Transparency Center（transparency.meta.com/features/explaining-ranking/fb-feed-recommendations）
- 原文摘要：Facebook Feed Recommendations 會預測哪些未追蹤內容可能對使用者有興趣

**Creator Action Layer**

這是什麼意思：
這是 Facebook Feed 中專門處理「你沒有追蹤但可能感興趣的內容」的推薦系統。它讓你的內容有機會出現在沒有追蹤你的人的 Feed 中，是陌生觸及的重要管道之一。

內容該怎麼做：
- 內容要有明確的主題定位，讓系統能判斷「這個人可能對這個話題感興趣」
- 不要做太廣泛、什麼都想說的內容，利基定位更容易被推薦給對的陌生人

該注意什麼：
- 這個系統的存在代表你的 Feed 貼文不只給追蹤者看，有機會觸及陌生人
- 但前提是內容足夠有價值、主題夠清晰

**Tool Mapping Layer**
- 教材概念：Facebook Feed 不只是給粉絲看的版位
- Screenwriter tag：`True-Interest-Fit`（確保內容主題清晰，適合推薦給陌生受眾）

---

## personalized ranking｜個人化排序

**Source Layer**
- 可信度：`official`
- 來源：Meta Transparency Center（transparency.meta.com/features/ranking-and-content）
- 原文摘要：Facebook Feed 使用機器學習為超過 20 億使用者個人化排序內容（此數字為來源文件記載時的說法，實際數字可能隨時間變化）

**Creator Action Layer**

這是什麼意思：
每個 Facebook 使用者看到的內容順序都是個人化的，由機器學習系統根據這個人的行為歷史、興趣、關係網絡等因素決定。沒有兩個人看到的 Facebook 是完全相同的。

內容該怎麼做：
- 設計有清楚族群定位的內容，讓個人化系統能把你推薦給對的人
- 不要嘗試製作「所有人都會喜歡」的內容，個人化系統更擅長處理有明確定位的內容

該注意什麼：
- 引用「20 億使用者」這個數字時需保留「來源文件記載時的說法」前提，實際數字可能變化
- 個人化排序代表你無法控制「誰會看到你的內容」，只能透過內容定位間接影響

**Tool Mapping Layer**
- Screenwriter：`Audience Selector`（設定目標受眾，輔助個人化系統定向）
- v6.5 欄位：`target_audience`
- 教材定位：個人化排序是 Facebook 的底層邏輯，內容定位清晰是前提

---

## UTIS / User True Interest Survey｜使用者真實興趣調查

**Source Layer**
- 可信度：`official`
- 來源：Meta Engineering（engineering.fb.com/2026/01/14/ml-applications/adapting-the-facebook-reels-recsys-ai-model-based-on-user-feedback）
- 原文摘要：User True Interest Survey、interest matching、likes、shares、watch time、retention、satisfaction、niche high-quality content 均為 UTIS 模型的評估訊號

**Creator Action Layer**

這是什麼意思：
UTIS 是 Facebook Reels 在 2026 年明確導入的機制。Facebook 系統會向部分使用者發送調查，詢問他們對看過的 Reels 的「真實興趣程度」，而不只是依賴按讚、分享等行為訊號。

這個機制代表一件重要的事：行為訊號（按讚、觀看）不等於真實興趣。有時候人們因為好奇、無聊或誤點而看了一支影片，但那不代表真的對這個主題感興趣。UTIS 試圖捕捉更接近「真實」的興趣。

內容該怎麼做：
- 製作對目標族群有實質價值的內容，而不是靠標題或包裝製造點擊衝動
- 深耕特定族群的真實需求，比追求泛大眾話題更符合 UTIS 的邏輯
- 語氣要像真人說話，而不是廣告或行銷文案

該注意什麼：
- 不要說「UTIS 等於按讚加權」，兩者是不同層次的訊號
- 不要說「UTIS 保證推播」，它是修正系統，讓推薦更準確，不是加速推播的開關
- 製造「讓人停不下來但其實沒興趣」的內容，在 UTIS 模型下會被修正

**Tool Mapping Layer**
- Screenwriter tag：`True-Interest-Fit`（確保內容對目標族群有真實價值）
- v6.5 欄位：`algorithm_factors`（包含 UTIS 標籤）
- 教材核心概念：UTIS 代表「讓人停留」和「讓人真的有興趣」是兩件不同的事

---

## interest matching｜興趣匹配

**Source Layer**
- 可信度：`official`
- 來源：Meta Engineering（engineering.fb.com/2026/01/14）
- 原文摘要：interest matching 是 UTIS 模型中的核心配對機制

**Creator Action Layer**

這是什麼意思：
Facebook Reels 系統會把你的內容與使用者的興趣檔案進行比對，判斷這支影片適合推薦給哪類人。興趣匹配越準確，推薦效率越高。這與 UTIS 是配套的：UTIS 收集真實興趣回饋，interest matching 把這些回饋用來優化後續推薦。

內容該怎麼做：
- 內容主題要清晰，讓系統容易判斷「這是哪類人會感興趣的內容」
- 開頭就說清楚這支影片是給誰的，例如「如果你是做小生意的老闆...」
- 避免一支影片同時想打三個不同的受眾，會讓系統難以定向

該注意什麼：
- interest matching 是系統側的機制，不是創作者直接控制的
- 你能影響的是「讓系統更容易判斷你的內容適合誰」，而不是直接操控匹配結果

**Tool Mapping Layer**
- Screenwriter：`Audience Selector`（精準描述目標受眾）
- Screenwriter tag：`True-Interest-Fit`
- v6.5 欄位：`target_audience`

---

## watch time｜觀看時間

**Source Layer**
- 可信度：`official`
- 來源：Meta Engineering（engineering.fb.com/2026/01/14）
- 原文摘要：watch time 為 UTIS 模型的評估訊號之一

**Creator Action Layer**

這是什麼意思：
觀眾實際停留在你的 Facebook Reels 上的時間。這是 UTIS 模型中的評估訊號之一，代表觀眾願意投入多少時間在這支影片上。

內容該怎麼做：
- 前幾秒要能讓目標受眾停下來，不適合的人離開沒關係，對的人要留住
- 內容節奏要緊湊，讓觀眾有理由一直看下去

該注意什麼：
- watch time 高不等於真實興趣高，UTIS 的存在就是為了修正這個落差
- 不要只追求 watch time，要讓觀眾看完後覺得「有收穫」

**Tool Mapping Layer**
- v6.5 欄位：`history_tracking.watch_time`
- Screenwriter tag：`Watch-Time-Hook`（Facebook 版本）

---

## retention｜留存率

**Source Layer**
- 可信度：`official`
- 來源：Meta Engineering（engineering.fb.com/2026/01/14）
- 原文摘要：retention 為 UTIS 模型的評估訊號之一

**Creator Action Layer**

這是什麼意思：
觀眾從頭看到結尾的比例。Facebook Reels 的留存率代表內容在整個播放過程中是否持續吸引觀眾。

內容該怎麼做：
- 每隔幾秒要有新的資訊點或節奏變化，避免觀眾提前離開
- Facebook 的使用者年齡層通常比 Instagram 高，內容節奏可以稍微穩健一些，但不代表可以鬆散
- 真實案例和具體數字是維持留存的有效方式

該注意什麼：
- 留存率斷崖式下降通常代表某個段落內容品質突然下降，或節奏突然變慢
- 留存率是發布後的觀察數據，腳本設計階段要預測「哪裡可能掉人」

**Tool Mapping Layer**
- Screenwriter tag：`Retention-Cut`（分鏡設計標記節奏切換點）
- v6.5 欄位：`history_tracking.retention_rate`

---

## likes｜按讚

**Source Layer**
- 可信度：`official`
- 來源：Meta Engineering（engineering.fb.com/2026/01/14）
- 原文摘要：likes 為 UTIS 模型的評估訊號之一

**Creator Action Layer**

這是什麼意思：
觀眾對你的 Facebook Reels 或貼文按讚，是基本的正向情感訊號。在 UTIS 模型中，likes 是評估訊號之一，但不是唯一決定因素。

內容該怎麼做：
- 讓內容能引發真實的正向共鳴，按讚會自然發生
- 不要用「按讚解鎖內容」或「按讚支持創作」這類強迫性語言

該注意什麼：
- Facebook 的按讚有多種類型（讚、愛心、哈哈、哇、嗚嗚、憤怒），不同類型可能傳達不同情感訊號
- 按讚是基本盤，但 UTIS 模型代表系統不只看按讚，也直接問使用者的真實感受

**Tool Mapping Layer**
- v6.5 欄位：`history_tracking.likes`
- 教材定位：按讚是基本盤訊號，UTIS 是更深層的真實興趣判斷

---

## shares｜分享

**Source Layer**
- 可信度：`official`
- 來源：Meta Engineering（engineering.fb.com/2026/01/14）
- 原文摘要：shares 為 UTIS 模型的評估訊號之一

**Creator Action Layer**

這是什麼意思：
觀眾把你的 Reels 或貼文分享給朋友、貼到自己的動態、或分享到社團，代表內容有「值得讓別人看到」的傳播價值。在 Facebook 的社交圖譜環境中，分享特別重要，因為它直接借用朋友的信任關係擴散你的內容。

內容該怎麼做：
- 設計有「值得分享給特定族群」的內容，例如：「這個資訊我的朋友一定要看」
- 真實案例、反常識的觀點、有用的工具清單是常見的分享驅動力
- 社團分享是 Facebook 特有的擴散管道，設計適合社團環境的內容格式

該注意什麼：
- 不要說「分享保證分發」，分享是訊號之一，不是推播開關
- 社團分享在官方文件中是「信任場景」，沒有被列為固定加權公式

**Tool Mapping Layer**
- v6.5 欄位：`history_tracking.shares`
- Screenwriter tag：`Group-Ready`（確保內容適合社團分享格式）

---

## satisfaction｜滿意度

**Source Layer**
- 可信度：`official`
- 來源：Meta Engineering（engineering.fb.com/2026/01/14）
- 原文摘要：satisfaction 為 UTIS 模型的核心評估維度之一

**Creator Action Layer**

這是什麼意思：
UTIS 模型中的核心評估維度之一。Facebook 系統不只看觀眾的行為（有沒有看完、有沒有按讚），也試圖判斷觀眾看完後「是否真的覺得滿意」。

滿意度與 watch time 的差別：
- watch time 高但 satisfaction 低：觀眾被懸念吊著看完，但看完後覺得被騙
- watch time 適中但 satisfaction 高：觀眾覺得真的有收穫，看完很值得

內容該怎麼做：
- 內容要真正解決觀眾的問題或滿足他們的需求
- 不要用「看到最後才告訴你答案」的手法拖延，讓觀眾看完後覺得浪費時間
- 結尾要讓觀眾有「這支影片值得的」的感受

該注意什麼：
- 滿意度是系統主動收集的訊號，不是創作者能直接操控的
- 它代表 Facebook 已經意識到「行為訊號可以被操控，真實感受更難偽造」

**Tool Mapping Layer**
- Screenwriter tag：`Satisfaction-Proof`（確保結尾設計讓觀眾覺得有收穫）
- 教材核心概念：滿意度是比 watch time 更難偽造的訊號

---

## niche high-quality content｜利基高品質內容

**Source Layer**
- 可信度：`official`
- 來源：Meta Engineering（engineering.fb.com/2026/01/14）
- 原文摘要：UTIS 模型說明中明確提及 niche high-quality content 為受益對象

**Creator Action Layer**

這是什麼意思：
UTIS 模型的官方說明中，明確提到「利基高品質內容」是受益對象。聚焦特定小眾族群的深度內容，比試圖觸及所有人的泛大眾內容，在 UTIS 模型下更有機會被精準推薦。

內容該怎麼做：
- 不要為了追求更大的受眾而稀釋內容的深度
- 聚焦在特定族群的真實痛點，做他們真的需要的內容
- 深度勝過廣度：一支真正解決特定族群問題的影片，比一支所有人都覺得還好的影片更有價值

該注意什麼：
- 「利基」不等於「小眾到沒人看」，而是「有清楚定位的受眾群體」
- 不要說「只要是利基就保證推播」，UTIS 同時要求高品質，兩者缺一不可

**Tool Mapping Layer**
- Screenwriter：`Audience Selector`（精準定義目標族群）
- Screenwriter tag：`True-Interest-Fit`
- 教材策略單元：為什麼利基定位比泛大眾定位更適合變現

---

## Interested / Not interested｜感興趣 / 不感興趣

**Source Layer**
- 可信度：`official`
- 來源：Meta Transparency Center（transparency.meta.com/features/user-control-shape-your-experience-on-meta-platforms）
- 原文摘要：使用者可用 Interested / Not interested 影響 Reels、Feed、Explore、Search 推薦

**Creator Action Layer**

這是什麼意思：
Facebook 使用者可以主動點選「感興趣」或「不感興趣」來告訴系統自己的偏好，系統會據此調整後續推薦。這是雙向訊號：
- 感興趣：系統增加推薦類似內容的機率
- 不感興趣：系統減少推薦類似內容，並可能影響你的帳號在這個使用者面前的曝光

內容該怎麼做：
- 確保內容對目標受眾真的有價值，減少「不感興趣」的負向回饋
- 透過內容定位清晰，讓系統推薦給真正感興趣的人，而不是大量推給不相關受眾

該注意什麼：
- 不感興趣的回饋對帳號的長期推薦有累積影響，不只影響單支影片
- 如果持續被推薦給錯誤的受眾，會累積大量「不感興趣」，影響整體帳號的推薦效率

**Tool Mapping Layer**
- v6.5 欄位：`audit.warnings`（標記可能引發「不感興趣」的內容設計問題）
- Screenwriter：`Algorithm Fit Check`（受眾匹配檢查）

---

## Meaningful Social Interactions（MSI）｜有意義的社交互動

**Source Layer**
- 可信度：`official`
- 來源：Facebook Newsroom（about.fb.com/news/2018/01/news-feed-fyi-bringing-people-closer-together）
- 原文摘要：Facebook 調整 News Feed，重視人與人之間有意義互動、留言、分享、朋友互動

**Creator Action Layer**

這是什麼意思：
2018 年 Facebook 明確說明，他們更重視「人與人之間有意義的互動」，而不只是被動消費內容。MSI 包含：留言（特別是有實質內容的留言）、分享並附上個人評語、朋友之間的互動、來回討論。這個原則至今仍是 Facebook Feed 排序的核心邏輯之一。

內容該怎麼做：
- 設計能引發真實討論的內容，而不是讓人滑過去
- 在貼文中提出真實有意義的問題，讓觀眾有回應的動力
- 鼓勵觀眾分享給有同樣情況的朋友，並說明原因

該注意什麼：
- MSI 強調的是「有意義」，不是「互動數量多」
- 大量低品質留言不等於有意義的社交互動
- engagement bait 會被系統識別並降權

**Tool Mapping Layer**
- Screenwriter tag：`Discussion-Starter`（確保腳本中有真實討論問題的設計）
- Screenwriter tag：`Meaningful-Interaction`（腳本審核，避免 engagement bait）
- 教材核心概念：MSI 要的是真實對話，不是數字堆砌

---

## comments｜留言

**Source Layer**
- 可信度：`official`
- 來源：Facebook Newsroom（about.fb.com/news/2018/01）
- 原文摘要：comments 是 MSI 的核心組成，反映內容引發深度互動的能力

**Creator Action Layer**

這是什麼意思：
留言是 MSI 的核心組成之一。觀眾在你的 Reels 或貼文下留言，代表內容引發了足夠的反應，讓人願意花時間說點什麼。在 Facebook 的邏輯中，留言比按讚更深度，因為它需要觀眾主動輸入文字。

內容該怎麼做：
- 結尾提出一個開放式問題，連結真實生活情境
- 好的問題範例：「你現在遇到最大的挑戰是什麼？」「你試過這個方法嗎？結果怎樣？」
- 主動在留言區回覆，帶動後續的 back-and-forth discussion

該注意什麼：
- 不要用「留言送禮物」、「留言+1 領取」這類互動誘餌，Facebook 系統會識別並降權
- 問題要真實有意義，不要只是「你覺得呢？」這種無法引發實質討論的空泛提問

**Tool Mapping Layer**
- Screenwriter：`CTA Generator`（Facebook 版本包含討論問題生成）
- v6.5 欄位：`history_tracking.comments`

---

## back-and-forth discussion｜來回討論

**Source Layer**
- 可信度：`official`
- 來源：Facebook Newsroom（about.fb.com/news/2018/01）+ Facebook Public Comments Ranking（about.fb.com/news/2019/06/making-public-comments-more-meaningful）
- 原文摘要：Facebook 重視來回討論的深度互動；公開留言排序考慮留言品質、相關性、integrity、engagement bait

**Creator Action Layer**

這是什麼意思：
Facebook 特別重視留言區中的「來回討論」，也就是觀眾之間或觀眾與創作者之間的持續對話。這種互動比單次留言更有價值，因為它代表內容真正引發了人們想深入討論的動力。

內容該怎麼做：
- 設計的問題要能引發「多輪回覆」，而不是一次性的是非題
- 例如：「你當時是怎麼決定的？後來結果如何？」比「你同意嗎？」更能引發來回討論
- 主動回覆第一波留言，讓討論繼續下去

該注意什麼：
- 來回討論需要時間累積，不是一支影片發布後馬上就能看到的數字
- 如果你的留言區都是單一回覆，沒有延續性討論，要重新思考問題設計

**Tool Mapping Layer**
- Screenwriter tag：`Discussion-Starter`（設計能引發來回討論的問題）
- 教材定位：back-and-forth discussion 是比留言數更有價值的互動形式

---

## friends and family interactions｜朋友與家人互動

**Source Layer**
- 可信度：`official`
- 來源：Facebook Newsroom（about.fb.com/news/2018/01）
- 原文摘要：Facebook Feed 排序中，朋友和家人的互動訊號有特別影響力

**Creator Action Layer**

這是什麼意思：
Facebook Feed 的排序邏輯中，朋友和家人的互動訊號有特別的影響力。如果你的內容被使用者的朋友按讚、留言或分享，這支內容出現在那個使用者 Feed 中的機率會上升。你的粉絲的朋友，是你觸及陌生人最自然的管道。

內容該怎麼做：
- 設計能讓既有追蹤者「覺得值得分享給朋友」的內容
- 想清楚：你的追蹤者會在什麼情境下把你的內容傳給朋友？
- 標記特定族群的痛點，讓追蹤者看到後想起某個朋友

該注意什麼：
- 這個機制在 Facebook 比在 Instagram 更明顯，因為 Facebook 的社交圖譜更強
- 不要把這個解讀成「只要朋友互動就保證擴散」，它是訊號組合的一部分

**Tool Mapping Layer**
- Screenwriter tag：`Real-Life-Case`（設計有真實案例的內容，提高朋友間的分享動機）
- 教材定位：朋友關係圖譜是 Facebook 與 Instagram 最大的差異之一

---

## 留言品質 / engagement bait 排除｜留言排序品質機制

**Source Layer**
- 可信度：`official`
- 來源：Facebook Newsroom（about.fb.com/news/2019/06/making-public-comments-more-meaningful）
- 原文摘要：公開留言排序考慮留言品質、相關性、integrity、engagement bait 等因素

**Creator Action Layer**

這是什麼意思：
Facebook 的公開留言排序系統會考慮留言的品質、相關性、integrity，並主動識別和降權 engagement bait。

engagement bait 的常見形式包含：
- 「按讚支持創作者」
- 「留言 1 代表同意」
- 「分享給需要的朋友」（指令式，而非真實分享動機）
- 「留言抽獎」

內容該怎麼做：
- 用真實有意義的問題引發互動，而不是指令式的誘餌
- 如果要引導分享，說清楚「為什麼分享對朋友有價值」，而不是直接叫人分享
- 留言區要管理，避免低品質留言主導討論

該注意什麼：
- engagement bait 是 Facebook 官方明確說明會被降權的行為，不是推論
- 很多創作者不知道某些常見說法屬於 engagement bait，要在教材中明確列出

**Tool Mapping Layer**
- Screenwriter tag：`Meaningful-Interaction`（腳本審核，自動標記可能的 engagement bait 語言）
- v6.5 欄位：`audit.warnings`（列出 engagement bait 風險警告）
- 教材定位：列出常見 engagement bait 範例，讓學員知道要避免什麼

---

## 社團分享｜Groups

**Source Layer**
- 可信度：`practical_inference`
- 來源：無直接官方來源
- 注意：文件明確定位為「信任與擴散場景」，非官方確認的固定加權公式

**Creator Action Layer**

這是什麼意思：
Facebook 社團是一個「信任場景」，成員之間有共同興趣或身份認同，分享到社團的內容在信任背景下更容易被接受和互動。

內容該怎麼做：
- 社團是信任場景，不是廣告版位，內容要以「分享經驗」的語氣切入
- 適合社團的內容格式：真實案例、學習心得、實測結果、問題求助
- 不要直接在社團貼廣告，要先提供價值，再讓人主動詢問

該注意什麼：
- 不同社團有不同的社群文化和規則，要先了解社團性質再發布內容
- 不要說「分享到社團保證加權」，沒有官方文件支撐

**Tool Mapping Layer**
- Screenwriter tag：`Group-Ready`（確保內容格式適合社團環境）
- 教材定位：標示為「實務推論：信任承接場景，非官方固定加權公式」

---

## Messenger 互動｜私訊

**Source Layer**
- 可信度：`practical_inference`
- 來源：無官方來源
- 注意：高意向轉化的變現承接工具，非官方確認的推播訊號

**Creator Action Layer**

這是什麼意思：
觀眾主動透過 Facebook Messenger 私訊你，是高意向轉化的入口。在 Facebook 的變現漏斗中，Messenger 是從「有興趣的觀眾」變成「真正的潛在客戶」的關鍵節點。

內容該怎麼做：
- 結尾設計自然的 Messenger 引導：「有問題可以私訊我」、「私訊我『關鍵字』我傳你資源」
- Messenger 承接要有後續流程，不能讓人傳訊息後沒有回應
- 可以設計自動回覆，確保每個私訊都能在第一時間得到回應

該注意什麼：
- Messenger 引導要自然，不能讓人覺得被強迫進入銷售流程
- Messenger 是私下的一對一空間，語氣要比 Reels 更個人化

**Tool Mapping Layer**
- Screenwriter tag：`Messenger-or-Live-Path`（設計承接 Messenger 的 CTA 路徑）
- v6.5 欄位：`history_tracking.messenger_count`（標示為變現漏斗指標）
- 教材定位：標示為「實務推論：高意向轉化工具，非官方推播訊號」

---

## 直播互動｜Live

**Source Layer**
- 可信度：`practical_inference`
- 來源：無官方來源
- 注意：信任深化的承接工具，非官方確認的推播訊號

**Creator Action Layer**

這是什麼意思：
Facebook 直播是建立深度信任的工具，讓觀眾能即時與你互動、提問、看到真實的你。在變現漏斗中，直播通常是從「有興趣的觀眾」轉化為「付費客戶」的重要一步。

內容該怎麼做：
- 用 Reels 預熱直播：在 Reels 中說「下週直播會詳細說明這個主題」
- 直播中設計明確的價值點，讓觀眾覺得來看直播是值得的
- 直播結束後把精華片段剪成 Reels，形成內容循環

該注意什麼：
- 直播的即時互動性是它最大的優勢，不要把直播做成單向廣播
- 直播預熱的 Reels 要說清楚「來看直播你會得到什麼」

**Tool Mapping Layer**
- Screenwriter tag：`Messenger-or-Live-Path`（Content Goal 設為「直播預熱」時自動建議）
- 教材定位：標示為「實務推論：信任深化工具，非官方推播訊號」

---

## Friend bubbles / Relationship strength｜朋友圈 / 關係強度

**Source Layer**
- 可信度：`practical_inference`
- 來源：file 1、3 提及，來源資料庫無對應官方 URL
- 注意：「Friend bubbles」和「Relationship strength」非 Facebook 官方術語；MSI 的官方說明支持「朋友互動影響排序」的邏輯，但沒有官方文件用這兩個詞定義固定加權公式

**Creator Action Layer**

這是什麼意思：
這個概念描述的是：與你有更強關係的朋友（常互動、常留言、常分享）的行為訊號，對你的 Feed 排序影響更大。你們之間的「關係強度」越高，彼此的內容越容易出現在對方的 Feed 中。

內容該怎麼做：
- 鼓勵真實的互動，讓既有的關係更強化
- 定期與留言者互動，建立雙向關係

該注意什麼：
- 不能把這個說法寫成「Facebook 官方確認的加權公式」
- 教材和工具中要標示為「業界推論，非官方術語；基於 MSI 邏輯的延伸推論」

**Tool Mapping Layer**
- 教材定位：標示為「實務推論，非官方術語，基於 MSI 邏輯的延伸推論」
- 不建議在 v6.5 JSON 中作為獨立欄位，可在 notes 中說明

---

# 附錄：統一欄位命名規則

```json
{
  "platform": "youtube | instagram_reels | instagram_stories | instagram_feed | facebook_reels | facebook_feed | facebook_video",
  "content_goal": "awareness | trust | dm | course | product | live_warmup",
  "target_audience": "描述文字",
  "source_claim_level": "official | high_confidence | practical_inference | unsupported",

  "script_design": {
    "search_intent": "",
    "hook_type": "",
    "send_worthy_point": "",
    "save_worthy_point": "",
    "cta_type": ""
  },

  "algorithm_factors": {
    "platform": "",
    "harness_tags": [],
    "key_signals": []
  },

  "audit": {
    "originality_check": "",
    "recommendation_eligibility": "",
    "engagement_bait_check": "",
    "warnings": []
  },

  "history_tracking": {
    "publish_date": null,
    "views": null,
    "likes": null,
    "dislikes": null,
    "shares": null,
    "comments": null,
    "watch_time": null,
    "avg_view_duration": null,
    "avg_pct_viewed": null,
    "retention_rate": null,
    "ctr": null,
    "shorts_engaged_views": null,
    "avg_watch_time": null,
    "sends_per_reach": null,
    "like_rate": null,
    "saves": null,
    "profile_visits": null,
    "dm_count": null,
    "messenger_count": null,
    "new_followers": null,
    "conversions": null
  }
}
```

---

# 附錄：Pre-check / Post-check / Strategy-only 分類

| 類型 | 代表訊號 | 平台 | 用途 |
|---|---|---|---|
| **Pre-check**（腳本產出前審稿） | search intent | YouTube | 標題是否對齊搜尋意圖 |
| Pre-check | CTR-Promise | YouTube | 標題縮圖承諾是否在前 30 秒兌現 |
| Pre-check | audience matching | Instagram | 受眾定位是否清晰 |
| Pre-check | originality check | Instagram | 是否符合原創性要求 |
| Pre-check | recommendation eligibility | Instagram | 是否符合推薦資格 |
| Pre-check | true-interest-fit | Facebook | 內容是否符合目標族群真實興趣 |
| Pre-check | engagement bait check | Facebook | 是否包含 engagement bait 語言 |
| Pre-check | hook design | 三平台 | 開頭是否有有效的 Hook |
| Pre-check | CTA design | 三平台 | 結尾是否有對應平台的 CTA |
| **Post-check**（發布後成效觀察） | watch time | 三平台 | 觀眾實際投入時間 |
| Post-check | retention rate | 三平台 | 觀眾看完比例 |
| Post-check | CTR | YouTube | 標題縮圖點擊率 |
| Post-check | avg view duration | YouTube | 平均觀看時長 |
| Post-check | avg pct viewed | YouTube | 平均觀看比例 |
| Post-check | engaged views | YouTube Shorts | YPP 分潤依據 |
| Post-check | shares | 三平台 | 傳播價值指標 |
| Post-check | comments | 三平台 | 深度互動指標 |
| Post-check | likes | 三平台 | 基本共鳴指標 |
| Post-check | sends per reach | Instagram | 私訊分享率（Mosseri 高可信說法） |
| Post-check | views | Instagram | 觸及廣度 |
| Post-check | satisfaction / UTIS 回饋 | YouTube / Facebook | 真實滿意度訊號 |
| **Strategy-only**（策略備註，不寫成官方權重） | 下一支影片 / 播放清單路徑 | YouTube | 續看設計策略 |
| Strategy-only | Profile visits | Instagram | 變現漏斗承接指標 |
| Strategy-only | DM | Instagram | 高意向轉化指標 |
| Strategy-only | Stories 回覆 | Instagram | 信任深化互動指標 |
| Strategy-only | Groups 社團分享 | Facebook | 信任擴散場景 |
| Strategy-only | Messenger | Facebook | 高意向轉化承接 |
| Strategy-only | Live 直播 | Facebook | 信任深化工具 |
| Strategy-only | Friend bubbles / Relationship strength | Facebook | 業界推論，非官方術語 |

---

# 附錄：不可過度宣稱清單

| 常見說法 | 可信度 | 正確表述 |
|---|---|---|
| 按讚沒有用 | unsupported | 按讚是基本盤訊號之一，不是主要變現決策依據 |
| 按讚最重要 | unsupported | 按讚是訊號之一，與 watch time、retention、shares 並列 |
| 每天發片保證加權 | unsupported | 穩定發布有助受眾預期，頻率本身無官方推播保證 |
| 分享保證分發 | unsupported | 分享是推薦訊號之一，不是推播開關 |
| 社團分享固定加權 | unsupported | 社團是信任承接場景，非官方固定加權公式 |
| Profile visits 是官方推播權重 | unsupported | Profile visits 是變現漏斗指標，非推播訊號 |
| DM 是官方推播權重 | unsupported | DM 是高意向轉化指標，非推播訊號 |
| 一支爆了其他支必然被帶動 | unsupported | 主題一致可能有助於連鎖推薦，但不是保證機制 |
| Friend bubbles 是官方公式 | unsupported | 業界推論，非官方術語，基於 MSI 邏輯的延伸推論 |
| Trial Reels 是官方文件說明 | 需標示 | 來源為媒體報導，非官方文件 |
| sends per reach 是官方指標 | 需標示 | Mosseri 媒體說法，非官方文件 |

---

*文件版本：AK 三平台影音變現演算法實戰資料庫 v1.0（封存版）*
*定位：演算法官方訊號 × 創作者行動 × 工具化欄位整合母版*
*建立日期：2026-05-14*
*GPT 評分歷程：v1.0 母版 94/100，封存*
*衍生版本：*
*→ AK_Algorithm_Database_Executive_Summary_v1.0（簡報與決策用）*
*→ AK_Algorithm_Course_Blueprint_v1.0（影音變現教材用）*
*→ AK_Algorithm_ToolSpec_Screenwriter_v6_5_JSON_v1.0（工具規格用）*
---

# FACEBOOK PAGE MODULE｜粉絲專頁詳細補充章

**定位：** Facebook 粉絲專頁（Page / Fan Page）專用補充模組。  
**用途：** 補足三平台母版中 Facebook Page 的版位分流、官方來源、實務操作、注意事項、工具欄位與 PPT 教學頁。  
**核心定調：** Facebook Page 不是單一演算法；Page Feed、Page Reels、Page Video、Groups、Messenger、Live 必須分開設計與追蹤。  

---

## Page 總覽｜粉專不是單一演算法

**Source Layer**
- 可信度：`official / practical_inference`
- 主要來源：
  - `fb_feed_ai_system`
  - `fb_reels_ai_system`
  - `fb_video_ai_system`
  - `fb_feed_recommendations_ai`
  - `fb_engineering_utis`
  - `fb_msi_newsroom`
  - `fb_public_comments_ranking`
- 原文摘要：
  - Facebook Feed、Facebook Reels、Facebook Video 是不同 AI system。
  - Feed AI system 預測使用者覺得有價值、相關的貼文。
  - Reels AI system 預測使用者可能感興趣的 Reels。
  - Video AI system 決定 Video tab 中影片的出現與排序。
  - UTIS 補足「真實興趣」；MSI 補足「有意義互動」。

**Creator Action Layer**

這是什麼意思：  
粉絲專頁不是「發了粉絲就會看到」。同一個粉專內容進入不同版位後，會被不同 AI system 判斷：

- **Page Feed Post：** 偏向關係、相關性、價值與討論。
- **Page Reels：** 偏向陌生觸及、興趣匹配、留存與真實興趣。
- **Page Video：** 偏向主動觀看、長影片、標題縮圖與觀看深度。
- **Groups：** 信任承接場景，不是官方固定推播權重。
- **Messenger / Live：** 轉化與信任深化，不是官方 ranking factor。

內容該怎麼做：
- 先判斷這篇內容要進哪個版位：Feed / Reels / Video / Group / Messenger / Live。
- Feed 貼文不一定要影片，文字、圖文、案例文仍然有效。
- Reels 要在 1–3 秒內明確呼叫目標受眾。
- 長影片要用標題、縮圖與段落結構支撐主動觀看。
- 社團、Messenger、Live 要標示為變現承接，不可寫成推播公式。

該注意什麼：
- 不要把 Facebook 個人帳號邏輯直接套到粉專。
- 不要把 Reels、Feed、Video 的數據混在一起比較。
- 不要說「粉絲專頁權重與個人帳號相同」，官方沒有這樣定義。
- 不要說「投廣告會提高自然流」，這不屬於官方確認推播公式。

**Tool Mapping Layer**
- Screenwriter：
  - `account_type = page`
  - `placement = page_feed / page_reels / page_video / group_share / messenger / live`
  - `Page-Placement-Selector`
- v6.5：
  - `platform_profile.account_type = "page"`
  - `platform_profile.placement`
  - `history_tracking.page_*`
- 教材定位：
  - 粉專補充章第一頁
  - 建議標題：`Facebook 粉絲專頁不是單一演算法`

---

## Facebook Feed AI System｜粉專貼文 / Page Feed

**Source Layer**
- 可信度：`official`
- 來源：Meta Transparency Center  
  https://transparency.meta.com/features/explaining-ranking/fb-feed/
- Source ID：`fb_feed_ai_system`
- 原文摘要：Facebook Feed AI system 會預測使用者覺得最有價值、最相關的貼文並排序。
- 補充來源：
  - `fb_feed_recommendations_ai`
  - `fb_feed_ranking_content`
  - `fb_content_distribution`
  - `fb_improve_reach`

**Creator Action Layer**

這是什麼意思：  
粉專貼文進入 Feed 後，並不是單純照時間順序出現在粉絲面前。Feed 會混合朋友貼文、粉專內容、群組內容與推薦內容，並依使用者過去行為、興趣與關係網絡個人化排序。

對粉專而言，Feed 的角色是：
- 維護既有追蹤者關係
- 建立價值感與信任
- 透過留言、分享、朋友互動擴散
- 讓粉專主題被系統更清楚地理解

內容該怎麼做：
- 貼文前兩行要非常清楚，因為 Feed 常只露出開頭。
- 文字型貼文仍然有效，不一定每篇都要做成 Reels。
- 用真實案例、經驗、問題拆解取代純宣傳。
- 設計能引發長留言的問題。
- 主動回覆留言，延長 back-and-forth discussion。

該注意什麼：
- 粉絲數不是觸及保證。
- Feed 和 Reels 是不同系統，不要用 Reels 的留存邏輯衡量所有 Feed 貼文。
- 純廣告、硬銷、無價值轉貼會降低關係信任。
- 若貼文觸及低，先檢查前兩行、主題清晰度與互動品質，不要直接歸因於被限流。

**Tool Mapping Layer**
- Screenwriter tag：
  - `Page-Feed-Value`
  - `Discussion-Starter`
  - `Meaningful-Interaction`
  - `Engagement-Bait-Guard`
- v6.5 欄位：
  - `platform_profile.placement = "page_feed"`
  - `script_design.opening_lines`
  - `script_design.discussion_starter`
  - `audit.engagement_bait_check`
  - `history_tracking.page_feed_reach`
  - `history_tracking.page_feed_comments`
  - `history_tracking.back_and_forth_replies`
- 教材定位：
  - Page Feed = 關係、價值、討論，不是單純曝光。

---

## Facebook Reels AI System｜粉專 Reels

**Source Layer**
- 可信度：`official`
- 來源：Meta Transparency Center  
  https://transparency.meta.com/features/explaining-ranking/fb-reels/
- Source ID：`fb_reels_ai_system`
- 原文摘要：Facebook Reels AI system 會決定哪些 Reels 顯示、順序如何，並依據預測使用者可能感興趣的內容排序。
- 補充來源：
  - `fb_engineering_utis`
  - `meta_user_control_recommendations`

**Creator Action Layer**

這是什麼意思：  
粉專 Reels 是粉專觸及未追蹤受眾的重要版位，但不是「保證陌生公域推播」。它的核心是 Facebook Reels AI system 依使用者興趣預測與行為回饋，判斷哪些 Reels 適合出現在誰面前。

對粉專而言，Reels 的角色是：
- 陌生受眾發現
- 主題興趣測試
- 利基受眾定位
- 將高興趣觀眾導向 Page / Messenger / Live

內容該怎麼做：
- 開頭 1–3 秒要明確標示「這是給誰看的」。
- 主題要垂直，不要今天 AI、明天美食、後天人生雞湯。
- 用具體痛點與真實案例建立 true-interest fit。
- 不要只靠懸念拖時間，要在短時間內交付價值。
- 結尾可以引導留言、下一步資源或 Messenger，但須標示為變現承接。

該注意什麼：
- 不要假設粉絲會自動看到粉專 Reels。
- 不要把 Instagram Reels 策略 1:1 套到 Facebook Reels。
- Reels 高觀看不代表粉專 Feed 也會高觸及。
- UTIS 是真實興趣模型的一部分，不是爆發保證。

**Tool Mapping Layer**
- Screenwriter tag：
  - `Page-Reels-Discovery`
  - `True-Interest-Fit`
  - `Watch-Time-Hook`
  - `Satisfaction-Proof`
  - `Niche-High-Quality`
- v6.5 欄位：
  - `platform_profile.placement = "page_reels"`
  - `script_design.target_audience_callout`
  - `script_design.niche_topic_lock`
  - `audit.curiosity_trap_check`
  - `history_tracking.page_reels_views`
  - `history_tracking.page_reels_watch_time`
  - `history_tracking.page_reels_retention_rate`
  - `history_tracking.not_interested_count`
- 教材定位：
  - Page Reels = 陌生觸及與興趣匹配，不是粉絲通知工具。

---

## Facebook Video AI System｜粉專長影片 / Video Tab

**Source Layer**
- 可信度：`official`
- 來源：Meta Transparency Center  
  https://transparency.meta.com/features/explaining-ranking/fb-video/
- Source ID：`fb_video_ai_system`
- 原文摘要：Facebook Video AI system 會決定 Video tab 中哪些影片出現與排序。

**Creator Action Layer**

這是什麼意思：  
粉專長影片與 Video Tab 屬於較深度的影片消費場景。相較 Reels 的快速刷動，Video Tab 的使用者更可能處於「主動想看影片」狀態，因此適合長度較長、結構完整、教學或分析型內容。

內容該怎麼做：
- 標題與縮圖要清楚傳達觀看價值。
- 前段要快速交代「為什麼值得看完」。
- 中段要有段落分層，避免資訊堆疊。
- 適合教學、案例拆解、直播精華、長版說明。
- 可把直播內容剪成長影片，再拆成 Reels 做二次分發。

該注意什麼：
- Video Tab 不等於 Reels。
- 長影片不代表可以節奏鬆散。
- 若平均觀看時長低，先檢查開頭價值承諾與章節結構。
- 不要用短影音 1 秒跳點節奏硬套到所有長影片。

**Tool Mapping Layer**
- Screenwriter tag：
  - `Long-Form-Value`
  - `Retention-Bridge`
  - `Satisfaction-Proof`
  - `Chapter-Structure`
- v6.5 欄位：
  - `platform_profile.placement = "page_video"`
  - `script_design.chapter_outline`
  - `history_tracking.page_video_watch_time`
  - `history_tracking.avg_view_duration`
  - `history_tracking.retention_rate`
- 教材定位：
  - Page Video = 深度內容與主動觀看場景。

---

## UTIS / User True Interest Survey｜粉專 Reels 的真實興趣校正

**Source Layer**
- 可信度：`official`
- 來源：Meta Engineering  
  https://engineering.fb.com/2026/01/14/ml-applications/adapting-the-facebook-reels-recsys-ai-model-based-on-user-feedback/
- Source ID：`fb_engineering_utis`
- 原文摘要：User True Interest Survey、interest matching、likes、shares、watch time、retention、satisfaction、niche high-quality content 均為 UTIS 模型相關訊號。

**Creator Action Layer**

這是什麼意思：  
UTIS 的重點是修正「行為訊號」與「真實興趣」之間的落差。觀眾看完一支 Reels，不一定代表真的感興趣；可能只是無聊、誤點、被懸念拖住。UTIS 透過使用者回饋，協助系統更準確理解觀眾是否真的想看這類內容。

對粉專而言，UTIS 的啟示是：
- 粉專內容要讓目標受眾真正覺得有價值。
- 利基高品質內容比泛大眾話題更容易被準確匹配。
- 內容垂直度越高，系統越容易判斷適合誰。
- 不能只靠吊胃口、誇張標題、情緒操控拉留存。

內容該怎麼做：
- 聚焦特定族群與特定問題。
- 每支 Reels 都要清楚說明「這是給誰看的」。
- 用真實案例與具體解法支撐內容價值。
- 結尾讓觀眾有「這支影片值得」的感受。

該注意什麼：
- 不要說「UTIS 保證推播」。
- 不要說「UTIS 等於按讚加權」。
- 不要把「利基高品質」簡化成「小眾就會被推」。
- 更精準說法是：UTIS 有助於提升利基高品質內容的推薦匹配與分發品質。

**Tool Mapping Layer**
- Screenwriter tag：
  - `True-Interest-Fit`
  - `Niche-High-Quality`
  - `Satisfaction-Proof`
- v6.5 欄位：
  - `algorithm_tags.true_interest_fit`
  - `script_design.target_audience`
  - `script_design.viewer_problem`
  - `history_tracking.not_interested_count`
- 教材定位：
  - UTIS = 真實興趣校正，不是爆發開關。

---

## Interest Matching｜興趣匹配

**Source Layer**
- 可信度：`official`
- 來源：Meta Engineering UTIS 文章
- Source ID：`fb_engineering_utis`
- 原文摘要：interest matching 與 UTIS 配套，用於改善推薦與使用者興趣之間的匹配。

**Creator Action Layer**

這是什麼意思：  
Interest Matching 是系統側的興趣比對。粉專不能直接控制系統怎麼匹配，但可以透過內容主題清晰度、帳號定位一致性、開頭受眾呼叫，讓系統更容易判斷這支內容適合誰。

內容該怎麼做：
- 不要一支影片同時鎖定三種完全不同受眾。
- 開頭可使用：「如果你是……」「你正在……」「這支是給……」
- 粉專整體內容主題要一致，避免興趣標籤混亂。
- 同一主題可以連續做系列，累積系統對受眾的判斷。

該注意什麼：
- interest matching 不是創作者可手動操作的開關。
- 主題太廣不一定帶來更大受眾，反而可能讓系統難以定向。
- 粉專變現更適合「清楚利基」而非「所有人都可能喜歡」。

**Tool Mapping Layer**
- Screenwriter：
  - `Audience Selector`
  - `True-Interest-Fit`
  - `Niche Topic Lock`
- v6.5：
  - `target_audience`
  - `content_category`
  - `history_tracking.topic_cluster`
- 教材定位：
  - 粉專要從「漲粉」思維轉成「受眾標籤」思維。

---

## Watch Time / Retention / Likes / Shares / Satisfaction｜粉專 Reels 核心行為訊號

**Source Layer**
- 可信度：`official`
- 來源：Meta Engineering UTIS 文章
- Source ID：`fb_engineering_utis`
- 原文摘要：watch time、retention、likes、shares、satisfaction 均為 UTIS 模型相關訊號。

**Creator Action Layer**

這是什麼意思：  
這些是 Facebook Reels / Video 系統理解使用者行為與內容價值的重要訊號，但不能單獨看。

| 訊號 | 這是什麼意思 | 內容做法 | 注意事項 |
|---|---|---|---|
| Watch Time | 觀眾停留在內容上的時間 | 前幾秒讓對的人留下，中段持續給新資訊 | 高觀看不等於高真實興趣 |
| Retention | 觀眾是否持續看到後面 | 每幾秒給新資訊點，長影片做章節 | 留存斷崖代表結構出問題 |
| Likes | 基本正向情感訊號 | 內容有用、有共鳴，按讚自然發生 | 不要說按讚沒用，也不要說最重要 |
| Shares | 內容值得被別人看到 | 工具清單、案例、避坑指南易分享 | 不要說分享保證分發 |
| Satisfaction | 看完是否覺得值得 | 明確解決問題，承諾與交付一致 | 不是創作者可直接操控的開關 |

**Tool Mapping Layer**
- Screenwriter：
  - `Watch-Time-Hook`
  - `Retention-Cut`
  - `Share-Worthy`
  - `Satisfaction-Proof`
- v6.5：
  - `history_tracking.watch_time`
  - `history_tracking.retention_rate`
  - `history_tracking.likes`
  - `history_tracking.shares`
  - `post_review.viewer_value_note`
- 教材定位：
  - 粉專 Reels 的核心不是單一數字，而是訊號組合。

---

## Niche High-Quality Content｜利基高品質內容

**Source Layer**
- 可信度：`official`
- 來源：Meta Engineering UTIS 文章
- Source ID：`fb_engineering_utis`
- 原文摘要：UTIS 模型有助於提升利基高品質內容的推薦匹配與分發品質。

**Creator Action Layer**

這是什麼意思：  
粉專不一定要做大眾熱門題材。相反地，如果粉專能深耕特定族群、特定問題，並提供高品質內容，系統更容易把內容匹配給真正需要的人。

內容該怎麼做：
- 先定義「誰會需要這個粉專」。
- 長期圍繞同一類主題建立內容池。
- 用深度、案例與可操作建議建立專業感。
- 不要為了蹭流量讓粉專主題失焦。

該注意什麼：
- 利基不等於小到沒人看。
- 高品質是前提，不能只靠小眾定位。
- 不要說「利基就會被推」，應寫成「有助於推薦匹配」。

**Tool Mapping Layer**
- Screenwriter：
  - `Niche-High-Quality`
  - `Audience Selector`
- v6.5：
  - `content_category`
  - `topic_cluster`
- 教材定位：
  - 粉專經營要從追大眾熱點轉向建立清楚利基標籤。

---

## MSI / Meaningful Social Interactions｜有意義社交互動

**Source Layer**
- 可信度：`official`
- 來源：Facebook Newsroom  
  https://about.fb.com/news/2018/01/news-feed-fyi-bringing-people-closer-together/
- Source ID：`fb_msi_newsroom`
- 原文摘要：Facebook 調整 News Feed，重視人與人之間有意義互動、留言、分享、朋友與家人互動。

**Creator Action Layer**

這是什麼意思：  
MSI 不是單純互動數量，而是互動品質。粉專若能引發觀眾與觀眾之間、觀眾與創作者之間的真實討論，比只有大量按讚更有價值。

內容該怎麼做：
- 設計具體而非空泛的問題。
- 問題應連結真實經驗，例如：「你遇到這種狀況時怎麼處理？」
- 主動回覆留言，讓討論延續。
- 鼓勵分享時要說清楚對朋友的價值，而不是命令觀眾分享。

該注意什麼：
- 「有意義」不等於互動多。
- 「留言 +1」不是有意義互動。
- 粉專應避免把留言區變成機械式領取區。

**Tool Mapping Layer**
- Screenwriter：
  - `Meaningful-Interaction`
  - `Discussion-Starter`
- v6.5：
  - `history_tracking.comments`
  - `history_tracking.back_and_forth_replies`
- 教材定位：
  - 粉專留言區是信任建立場所，不是刷數字場所。

---

## Comments / Back-and-forth Discussion｜留言與來回討論

**Source Layer**
- 可信度：`official`
- 來源：
  - `fb_msi_newsroom`
  - `fb_public_comments_ranking`
- 原文摘要：Facebook 重視留言與來回討論；公開留言排序會考慮留言品質、相關性、integrity、engagement bait 等。

**Creator Action Layer**

這是什麼意思：  
粉專留言不是越多越好，而是要看是否形成高品質討論。來回討論代表觀眾投入更深，且貼文有機會延長生命週期。

內容該怎麼做：
- 問題要能引出個人經驗，而不是單字回答。
- 範例：
  - 不佳：「你同意嗎？」
  - 較佳：「你上次遇到這個問題時，是怎麼處理的？」
- 粉專管理員應回覆第一波留言，讓討論延續。
- 對高品質留言可延伸成下一篇貼文或 Reels 題材。

該注意什麼：
- 單字留言、表情符號留言、+1 不等於高品質討論。
- 互動誘餌會被辨識與降權。
- 來回討論需要時間，不一定在發文第一小時完全反映。

**Tool Mapping Layer**
- Screenwriter：
  - `Discussion-Starter`
  - `Comment-Quality-Check`
- v6.5：
  - `history_tracking.back_and_forth_replies`
  - `history_tracking.comment_quality_note`
- 教材定位：
  - 粉專管理者的回覆也是內容策略的一部分。

---

## Engagement Bait｜互動誘餌排除

**Source Layer**
- 可信度：`official`
- 來源：
  - `fb_public_comments_ranking`
  - `fb_engagement_bait_help`
- 原文摘要：Facebook 公開留言排序與 Business Help 均強調低品質互動與誘餌式互動會降低內容品質或分發效果。

**Creator Action Layer**

這是什麼意思：  
互動誘餌是指用指令式、機械式方式要求觀眾按讚、留言、分享，以換取某種好處或製造假互動。這類行為會傷害粉專內容的品質評估。

常見高風險語句：
- 留言 +1
- 按讚支持創作者
- 分享給三個朋友
- 留言抽獎
- 按讚解鎖
- 不留言就錯過

安全替代：
- 「你遇過類似情況嗎？當時怎麼處理？」
- 「哪一個步驟最容易卡住？」
- 「如果你正在處理這類問題，可以收藏起來慢慢看。」
- 「這份清單適合傳給正在卡同樣問題的人。」

該注意什麼：
- 不要把 CTA 寫成誘餌。
- 「私訊關鍵字」可作為變現承接，但不要包裝成演算法加權技巧。
- 粉專比個人帳號更需要注意商業語氣與誘餌風險。

**Tool Mapping Layer**
- Screenwriter：
  - `Engagement-Bait-Guard`
  - `Meaningful-Interaction`
- v6.5：
  - `audit.engagement_bait_check`
  - `audit.warnings`
- 教材定位：
  - 粉專變現最容易踩到的降權風險。

---

## Interested / Not Interested｜感興趣 / 不感興趣

**Source Layer**
- 可信度：`official`
- 來源：Meta Transparency Center  
  https://transparency.meta.com/features/user-control-shape-your-experience-on-meta-platforms/
- Source ID：`meta_user_control_recommendations`
- 原文摘要：使用者可以透過 Interested / Not interested 影響後續推薦。

**Creator Action Layer**

這是什麼意思：  
使用者對內容標記「感興趣」或「不感興趣」，是對推薦系統的明確回饋。對粉專來說，若內容經常被不相關受眾標記不感興趣，可能影響後續推薦效率。

內容該怎麼做：
- 內容定位要清楚，減少被推給錯誤受眾。
- 標題與開頭不要誤導。
- 垂直經營，讓系統更容易找到對的人。
- 對不同受眾要拆不同內容，不要用一篇打所有人。

該注意什麼：
- 不感興趣是負向訊號，不是單純沒按讚。
- 若常出現高觸及低互動，可能代表受眾匹配不準。
- 粉專要定期檢查哪些主題容易引發負向回饋。

**Tool Mapping Layer**
- Screenwriter：
  - `Audience-Fit-Check`
  - `True-Interest-Fit`
- v6.5：
  - `history_tracking.not_interested_count`
  - `audit.audience_mismatch_warning`
- 教材定位：
  - 負向回饋是粉專定位是否清楚的重要信號。

---

## Groups｜社團承接

**Source Layer**
- 可信度：`practical_inference`
- 來源：無官方固定 ranking factor 來源
- 說明：社團是信任與擴散場景，不是官方固定推播權重。

**Creator Action Layer**

這是什麼意思：  
社團成員通常共享身份、興趣或問題。粉專內容如果被分享到合適社團，可能更容易獲得精準互動與信任，但這是社群場景優勢，不是官方加權公式。

內容該怎麼做：
- 用經驗分享語氣，不要硬廣。
- 適合內容：
  - 真實案例
  - 實測結果
  - 學習心得
  - 問題求助
  - 檢查清單
- 先提供價值，再讓人主動詢問。

該注意什麼：
- 不要說「社團分享保證加權」。
- 不同社團規則不同，硬廣容易被刪。
- 社團不是發廣告的地方，是建立信任的地方。

**Tool Mapping Layer**
- Screenwriter：
  - `Group-Ready`
  - `Real-Life-Case`
  - `Trust-Handoff`
- v6.5：
  - `history_tracking.group_engagement`
- 教材定位：
  - 社團是信任承接，不是官方推播開關。

---

## Messenger｜私訊承接

**Source Layer**
- 可信度：`practical_inference`
- 來源：無官方固定 ranking factor 來源
- 說明：Messenger 是高意向轉化入口，非官方推播權重。

**Creator Action Layer**

這是什麼意思：  
粉專 Messenger 是從公開內容進入一對一對話的關鍵節點。觀眾願意私訊，代表已經從瀏覽者進入潛在客戶階段。

內容該怎麼做：
- 設計自然的私訊 CTA。
- 可使用關鍵字：
  - 「私訊我『Page』領取檢查表」
  - 「需要完整範本，可以私訊我」
- 私訊後要有清楚承接流程。
- 語氣要個人化，不要像廣告自動回覆。

該注意什麼：
- Messenger 不是官方推播權重。
- 不要說私訊會提高自然觸及。
- 引導私訊要自然，不要讓人感覺被銷售。

**Tool Mapping Layer**
- Screenwriter：
  - `Messenger-Bridge`
- v6.5：
  - `history_tracking.messenger_count`
  - `history_tracking.qualified_leads`
- 教材定位：
  - Messenger 是變現漏斗的高意向節點。

---

## Live｜直播承接

**Source Layer**
- 可信度：`practical_inference`
- 來源：無官方固定 ranking factor 來源
- 說明：Live 是信任深化與成交場景，非官方固定推播權重。

**Creator Action Layer**

這是什麼意思：  
直播讓粉專能即時回答問題、展示真人可信度、建立比短影音更深的信任。它適合承接已經被 Reels 或 Feed 喚起興趣的觀眾。

內容該怎麼做：
- 用 Reels 預熱直播主題。
- Feed 貼文整理直播重點。
- 直播中設計問答與轉化節點。
- 直播後剪成 Reels / Video 再利用。

該注意什麼：
- Live 不是官方固定推播權重。
- 直播價值是即時互動與信任，不是單向廣播。
- 若直播前沒有預熱，出席率通常會低。

**Tool Mapping Layer**
- Screenwriter：
  - `Live-Warmup`
  - `Messenger-or-Live-Path`
- v6.5：
  - `history_tracking.live_attendance`
  - `history_tracking.follow_up_dm`
- 教材定位：
  - Live 是信任深化與成交工具。

---

## Ads / Paid Distribution｜廣告與自然流的界線

**Source Layer**
- 可信度：`unsupported / practical_inference`
- 來源：無官方直接支持「投廣告會提高自然推播」的固定公式
- 可參考：
  - `fb_content_distribution`
  - `fb_improve_reach`
- 說明：官方有內容分發與觸及提升建議，但沒有證明投廣告會直接帶動自然流排序。

**Creator Action Layer**

這是什麼意思：  
粉專可以用廣告測試受眾、擴大觸及、驗證轉化，但不應把廣告與自然推薦混為一談。投廣告帶來的互動可以幫助你理解受眾，但不能直接寫成「投廣告會加權自然流」。

內容該怎麼做：
- 用廣告測試不同受眾與主題。
- 分開記錄 paid reach 和 organic reach。
- 不要把廣告帶來的互動直接當成自然演算法成功。
- 用廣告驗證哪類內容能轉化，再回到自然內容做題材優化。

該注意什麼：
- 不要說「投廣告會提高自然觸及」。
- 不要把 paid engagement 與 organic engagement 混在一起解讀。
- 廣告是放大器，不是內容品質替代品。

**Tool Mapping Layer**
- Screenwriter：
  - `Paid-vs-Organic-Guard`
- v6.5：
  - `history_tracking.paid_reach`
  - `history_tracking.organic_reach`
  - `history_tracking.paid_conversion`
- 教材定位：
  - 廣告可作測試與轉化，但不是自然演算法加權公式。

---

## Facebook Page 專用 Pre-check

| 檢查項 | 問題 |
|---|---|
| Account Type | 是否明確標示為 Page，而非 Personal Profile？ |
| Placement Fit | 此內容適合 Page Feed、Page Reels、Page Video、Group、Messenger 還是 Live？ |
| Audience Clarity | 目標受眾是否清楚？ |
| True Interest Fit | 內容是否真的對該受眾有價值？ |
| Niche Consistency | 是否延續粉專主題，不讓系統標籤混亂？ |
| First 3 Seconds | 若為 Reels，前 1–3 秒是否清楚呼叫受眾？ |
| Opening Lines | 若為 Feed，前兩行是否足以讓人點開？ |
| MSI Design | 是否有具體問題能引發討論？ |
| Engagement Bait Guard | 是否避免留言 +1、按讚解鎖等語句？ |
| Conversion Handoff | 若有 CTA，是否標示為變現承接，而非官方推播訊號？ |
| Paid-vs-Organic Guard | 是否避免把廣告互動當成自然推播成功？ |

---

## Facebook Page 專用 Post-check

| 目標 | 指標 | 用途 |
|---|---|---|
| Feed 價值 | reach、comments、shares、back_and_forth_replies | 判斷是否有討論與關係互動 |
| Reels 興趣 | views、watch_time、retention_rate、shares、not_interested_count | 判斷是否對陌生受眾有興趣匹配 |
| Video 深度 | avg_view_duration、watch_time、retention_rate | 判斷長影片是否值得看 |
| Messenger 轉化 | messenger_count、reply_rate、qualified_leads | 判斷是否產生高意向對話 |
| Group 承接 | group_engagement、inquiries、comments | 判斷是否適合社團信任場景 |
| Live 承接 | live_attendance、questions、follow_up_dm | 判斷直播是否建立信任與轉換 |
| Paid / Organic | paid_reach、organic_reach、paid_conversion、organic_conversion | 避免廣告與自然流混淆 |

---

## Facebook Page 專用 JSON 範例

```json
{
  "platform": "facebook",
  "account_type": "page",
  "placement": "page_reels",
  "content_goal": {
    "primary_goal": "awareness",
    "secondary_goal": "messenger_conversion",
    "conversion_path": "page_reels_to_messenger"
  },
  "algorithm_tags": [
    {
      "tag": "Page-Reels-Discovery",
      "source_claim_level": "official"
    },
    {
      "tag": "True-Interest-Fit",
      "source_claim_level": "official"
    },
    {
      "tag": "Niche-High-Quality",
      "source_claim_level": "official"
    },
    {
      "tag": "Messenger-Bridge",
      "source_claim_level": "practical_inference"
    },
    {
      "tag": "Paid-vs-Organic-Guard",
      "source_claim_level": "unsupported/practical_inference"
    }
  ],
  "script_design": {
    "target_audience": "想用 Facebook 粉專做短影音變現的創作者",
    "hook_text": "粉專不是發了粉絲就會看到，Reels 會被另一套 AI 系統重新判斷。",
    "discussion_starter": "你目前粉專最卡的是觸及、留言，還是私訊轉換？",
    "cta": {
      "type": "messenger_keyword",
      "text": "私訊我『粉專』領取粉專內容檢查表。",
      "source_claim_level": "practical_inference",
      "note": "Messenger is conversion handoff, not official ranking factor."
    }
  },
  "audit": {
    "engagement_bait_check": {
      "passed": true,
      "detected_patterns": []
    },
    "unsupported_claim_check": {
      "passed": true,
      "detected_claims": []
    },
    "paid_vs_organic_check": {
      "passed": true,
      "note": "Paid reach and organic reach must be tracked separately."
    },
    "warnings": [
      "Do not describe Messenger as official ranking factor.",
      "Do not describe Groups as fixed distribution boost.",
      "Do not describe paid ads as organic ranking boost."
    ]
  },
  "history_tracking": {
    "views": null,
    "watch_time": null,
    "retention_rate": null,
    "comments": null,
    "shares": null,
    "not_interested_count": null,
    "messenger_count": null,
    "paid_reach": null,
    "organic_reach": null
  }
}
```

---

## Facebook Page PPT 補充章建議

建議加入原 PPT 中 Facebook 主章之後：

1. **Slide P1｜Facebook 粉絲專頁不是單一演算法**  
   Feed / Reels / Video / Groups / Messenger / Live 分流。

2. **Slide P2｜Page Feed：粉絲不一定會看到**  
   Feed 個人化排序、前兩行、MSI、留言討論。

3. **Slide P3｜Page Reels：陌生觸及與真實興趣匹配**  
   Reels AI system、UTIS、1–3 秒受眾呼叫、利基高品質內容。

4. **Slide P4｜Page Video：長影片與主動觀看情境**  
   Video AI system、標題縮圖、教學型長影片、章節設計。

5. **Slide P5｜Groups / Messenger / Live：變現承接，不是推播權重**  
   社團、私訊、直播、paid vs organic 分流。

6. **Slide P6｜粉專內容設計檢查表**  
   True-Interest-Fit、MSI、Engagement-Bait-Guard、Paid-vs-Organic-Guard。

---

## NotebookLM Prompt｜重新產出含粉專補充章的 PPT 文字稿

```text
請根據《AK 三平台影音變現演算法實戰資料庫 v1.0.2（Source Linked）》重新產出「文字型 PPT 內容稿」。

重要要求：
1. 請使用繁體中文。
2. 不要輸出視覺 PDF，不要使用 QR Code 取代網址。
3. 主投影片只需保留 source_id；Appendix 必須保留完整 URL。
4. 保留 official / high_confidence / practical_inference / unsupported 分級。
5. 不要把 practical_inference 寫成官方推播權重。
6. 不要把 Profile visits、DM、Messenger、Groups、Live 寫成官方 ranking factor。
7. Facebook 粉絲專頁請獨立成 6 頁補充章，不要塞進原本 Facebook 兩頁。
8. 廣告與自然流請分開，不要寫成「投廣告會提升自然推播」。

請輸出 Slide 1–30：

Slide 1｜封面：三平台影音變現演算法實戰
Slide 2｜為什麼不能只看播放量、按讚、發片頻率
Slide 3｜三平台一句話差異
Slide 4｜官方訊號、可信公開說法、實務推論的差別
Slide 5｜YouTube 核心邏輯：搜尋意圖 × 觀看體驗 × 滿意度
Slide 6｜YouTube 內容設計：CTR Promise / Retention / Satisfaction
Slide 7｜YouTube Shorts：views vs engaged views
Slide 8｜Instagram 核心邏輯：Reels 拉新 × 分享 × 原創性
Slide 9｜Instagram 內容設計：Watch-Time-Hook / Send-Worthy / Originality
Slide 10｜Instagram 變現承接：Profile / Stories / DM
Slide 11｜Facebook 核心邏輯：True Interest / UTIS / MSI
Slide 12｜Facebook 內容設計：Discussion-Starter / Meaningful Interaction
Slide 13｜Facebook 變現承接：Groups / Messenger / Live
Slide 14｜Facebook 粉絲專頁不是單一演算法
Slide 15｜Page Feed：粉絲不一定會看到，Feed 依個人化排序決定
Slide 16｜Page Reels：Reels AI system、UTIS 與未追蹤受眾觸及
Slide 17｜Page Video：長影片與 Video Tab 的主動觀看情境
Slide 18｜Page 承接：Groups / Messenger / Live 是變現漏斗，不是官方權重
Slide 19｜粉專廣告與自然流：Paid / Organic 必須分開看
Slide 20｜粉專內容設計檢查表：True-Interest-Fit / MSI / Engagement-Bait-Guard
Slide 21｜三平台推播訊號比較表
Slide 22｜Pre-check：發布前可以設計的訊號
Slide 23｜Post-check：發布後才能觀察的數據
Slide 24｜常見錯誤與不能過度宣稱
Slide 25｜如何把演算法轉成內容腳本
Slide 26｜如何銜接 Screenwriter / v6.5 工具系統
Slide 27｜最終行動路線
Slide 28｜Appendix A｜YouTube Sources
Slide 29｜Appendix B｜Instagram Sources
Slide 30｜Appendix C｜Facebook / Meta / Page Sources
Slide 31｜Appendix D｜Practical Inference / Conversion Handoff

每頁格式：
- 畫面主標
- 畫面副標
- 投影片 bullet
- 講師備註
- 圖表 / 視覺建議
- Claim Level
- 來源對應 source_id

Appendix 格式：
| source_id | source_name | URL | Claim Level | Supports Slides | 可佐證說法 | 不可過度推論 |
```
