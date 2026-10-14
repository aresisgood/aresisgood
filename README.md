# 嗨，我是 Ares Lai

**資料工程方向。** 於資展國際（iSpan）完成 Python AI 應用工程師培訓（2026/3–2026/8），專注於 Python 資料 Pipeline、資料品質驗證與 API 開發。

轉職前有 6 年以上大型購物中心營運經驗，長期以 KPI 數據支援品牌決策，熟悉從業務需求定義資料需求。

---

## 精選專案

### [JustMarket｜台股新聞事件分析平台](https://github.com/our-best-project/Justmarket)（團隊專案）

把大量重複的台股新聞收斂成可驗證的事件，產出摘要、事件重要度與市場驗證分數。

**我負責：資料 Pipeline 與事件分群**

- 以文章狀態流（`pending → vectorized → clustered`）串接各處理段，每段只處理上一個狀態的資料；中斷後可整條重跑或單段重跑（Idempotent）
- 處理 2026/1–7 鉅亨網新聞 5,409 篇，依新聞 ID 去重後保留 4,486 篇
- 新聞向量化：BGE-M3 產生 4,486 × 1024 維 Embedding，寫入 Metadata 與處理狀態
- 事件分群產出 3,070 個事件，其中 295 個由多篇重複報導合併而成
- 支援 PostgreSQL／JSON 雙資料來源、CPU／CUDA 雙執行環境
- 建立 64 篇新聞、40 個事件的 Golden Set，以 Pairwise Precision / Recall / F1 量化分群品質
- 分析誤判案例，加入日期 Gate、股票代號 Gate 與 Template Detection 規則降低事件誤合併

**分群品質：** Precision 0.949 ｜ Recall 0.881 ｜ F1 0.914

`Python` · `PostgreSQL` · `BGE-M3` · `Vector Embedding` · `Clustering`

---

### [PTCG Pocket DataBrowser｜卡牌與賽事資料 ETL 及 API](https://github.com/aresisgood/PTCG_Pocket_DataBrowser)

從 Limitless TCG 蒐集卡牌與賽事資料，經 ETL 處理後以 REST API 提供查詢與分析。

- ETL 流程：Fetch → Parse → Validate → Checkpoint → Output，蒐集 22 個系列共 3,900 張卡牌（失敗 URL 0 筆）
- 可中斷續跑（Checkpoint），失敗 URL 獨立記錄追蹤
- 彙整 40 場賽事、12,434 筆對局，將 411 種牌組原型篩選為 103 種有效原型
- FastAPI＋SQLModel（SQLite）提供牌組 CRUD、環境分析、預測等 API
- 162 個 pytest 測試；GitHub Actions 於 Python 3.11／3.12 執行 CI
- Docker 映像以非 root 使用者執行，並設定 HEALTHCHECK

`Python` · `FastAPI` · `SQLModel` · `SQLite` · `pytest` · `Docker` · `GitHub Actions`

---

### 其他作品

- [ReplyMate](https://github.com/aresisgood/ReplyMate)：本機優先的 AI 回覆草稿系統，匯入 LINE 聊天記錄並產生回覆草稿（Next.js、TypeScript、SQLite、Anthropic API）

---

## 技術能力

| 類別       | 技術                                                                                          |
| ---------- | --------------------------------------------------------------------------------------------- |
| 資料處理   | `Python` · `SQL` · `Pandas` · `NumPy`                                              |
| 資料庫     | `PostgreSQL` · `SQLite` · `SQLModel`                                                  |
| API        | `FastAPI` · `Flask` · `RESTful API`                                                   |
| 品質與部署 | `pytest` · `GitHub Actions` · `Docker` · `Git` · `Linux / WSL`                  |
| AI／ML     | `scikit-learn` · `BGE-M3` · `Vector Embedding` · `Clustering` · `Anthropic API` |

---

## 轉職前

- 大型購物中心營運 6 年以上（環球購物中心、統一百華夢廣場）
- Dream Plaza B2 美食街 11 個品牌開幕專案唯一營運窗口
- 帶領 6 人團隊，管理約 20 個品牌營運
- 以 Excel 樞紐分析追蹤品牌 KPI，作為續約與樓面調整的決策依據
