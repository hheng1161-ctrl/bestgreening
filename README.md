# 益福和生醫科技｜品牌官網（合併版）

線上預覽：<https://hheng1161-ctrl.github.io/bestgreening/>

## 這一版是什麼

**設計與內容**來自 2026-10-31（週六）AI 課實作的「益福和生醫科技網站」，
**SEO 層與公司資訊區塊**由愛夏加入。目標是產出一份**可以直接取代 bestgreening.com 首頁**的版本。

| 來源 | 內容 |
|---|---|
| 課堂版本 | 視覺設計、版面結構、inline SVG Logo、品牌文案、無障礙標記（skip-link、focus-visible、`<details>` 手機選單、prefers-reduced-motion） |
| 本次加入 | favicon（沿用同一顆 SVG Logo）、canonical、Open Graph／Twitter Card、JSON-LD 結構化資料、「公司資訊」區塊（NAP／營業時間／社群） |

---

## 為什麼需要這一版（官方網站現況）

實測 `bestgreening.com` 的原始碼：

| 項目 | 現況 |
|---|---|
| `<h1>` 標籤 | **0 個** |
| `meta description` | ❌ 沒有 |
| `viewport` | ❌ **沒有 → 手機開啟會以桌面寬度縮小顯示** |
| Open Graph | ❌ 沒有（分享無預覽） |
| JSON-LD 結構化資料 | ❌ 沒有 |
| `canonical` | ❌ 沒有 |
| `lang` 屬性 | ❌ 沒有 |

同樣的問題也存在於 `agsbio.com`、`flowergene.com`、`flower4skin.com`、`ifher31.com` —— **五個網站的 H1 全部是 0**。

---

## NAP 一致性（本版為準）

```
名稱：益福和生醫科技股份有限公司（BESTGREENING BIOMEDICAL CORPORATION）
地址：433 臺中市沙鹿區鹿寮里錦華街13號1樓
電話：04-2662-7278
統編：53127816
```

| 平台 | 電話 |
|---|---|
| 官網、Google 商家、台中通、本頁 | **04-2662-7278** ✅ |
| 經濟部工商登記 | 02-2708-1765 ❌ **已停用，待辦變更登記** |

## 營業時間

週一～週五 08:30–17:30；週六、週日休息。

---

## ⚠️ 上線到 bestgreening.com 前必須修改

本版目前指向 `hheng1161-ctrl.github.io`，**搬到正式網域時要改這 6 處**（否則 canonical 與分享預覽會指向錯誤網址）：

| 位置 | 現在的值 | 應改為 |
|---|---|---|
| `<link rel="canonical">` | `https://hheng1161-ctrl.github.io/bestgreening/` | `https://www.bestgreening.com/` |
| `og:url` | 同上 | 同上 |
| `og:image` | `.../bestgreening/assets/hero-banner.jpg` | `https://www.bestgreening.com/assets/hero-banner.jpg` |
| JSON-LD `@id` | `.../bestgreening/#store` | `https://www.bestgreening.com/#store` |
| JSON-LD `image` | 同上 | 同上 |
| `sitemap.xml` 的 `<loc>` | 同上 | `https://www.bestgreening.com/` |

**其餘內容（設計、文案、NAP、結構化資料欄位）不需要動。**

---

## 素材

| 檔案 | 說明 |
|---|---|
| `assets/hero-banner.jpg` | 980×280，重編碼 147 → 81 KB |
| `assets/brand-ags.jpg` | 980×320，123 → 27 KB |
| `assets/brand-yifuhe.jpg` | 1800×468，255 → 151 KB |
| `assets/brand-flower4skin.jpg` | 1800×468，350 → 207 KB |

原圖保留在 `learning\周六AI-20261031\益福和生醫科技網站\assets\`。
HTML 的 `width`／`height` 已依實際尺寸校正（避免版面位移）。

**Logo 不需要圖片檔** —— 標題列使用 inline SVG（向量、透明背景、任意縮放不失真），
favicon 也沿用同一組 path 轉成 data URI，因此只有一份視覺資產。

---

## 為什麼結構化資料裡沒有 `aggregateRating`

Google 的評論摘要政策要求：標記的評價必須來自**頁面上實際可見的評論**。
自行在自家網站標註「5.0 分、48 則評論」屬於自我評價，可能被判定為不實標記。
因此本頁不寫入 `aggregateRating`；若要呈現評價，請以文字連結到 Google 地圖。

---

## 後續建議

1. **合併重複的 Google 商家檔案**：`FLOWER 4SKIN 花草植萃` 與本公司在同一地址、同一電話、同一網站，
   屬重複地點。建議保留「益福和生醫科技股份有限公司」（48 則 5.0 評價），另一個申請合併。
2. 統一郵遞區號為 **433**（曾出現 423）。
3. 辦理工商登記電話變更（台北 02 那支已停用）。
4. 四個品牌網站也比照補上 H1 與 meta description。
5. 用 [Rich Results Test](https://search.google.com/test/rich-results) 驗證結構化資料。

---

## 變更紀錄

| 日期 | 內容 |
|---|---|
| 2026-10-31 | 以週六 AI 課版本為底合併：加入 favicon／canonical／Open Graph／JSON-LD／公司資訊區塊；圖片重編碼 |
