# MVC-Showcase: 個人開發者作品集網站

## 實施計畫

### 專案概述

一個雙語（英文/中文）個人作品集網站，展示 Marvin Chang 的開發專案與 AI 輔助編程能力。網站彙整 `~/Projects/` 目錄中的所有專案，打造精美的 Vercel 部署應用。

---

### 作品集專案清單

| # | 專案 | 技術棧 | 分類 |
|---|------|--------|------|
| 1 | **Polyrobot** | Next.js, TypeScript, wagmi, Supabase, Polygon | 區塊鏈 / 預測市場 |
| 2 | **Neo4j_Graphiti** | Python, Neo4j, OpenAI, Docker | AI 記憶系統 |
| 3 | **BabyPet** | Flutter, Firebase, 跨平台 | 行動應用 / 寵物健康 |
| 4 | **BabyPet iOS** | Swift, Firebase, iOS 原生 | 行動應用 / iOS |
| 5 | **企業銀行平台** *(NDA)* | Node.js, Express, Swift, Kotlin, Flutter | 金融科技 / 企業銀行 |
| 6 | **Saria** | Python, OpenAI GPT-4o, Flatlib, LINE Bot | AI / 星座內容 |
| 7 | **UltraDing** | Python, FastAPI, Streamlit, PostgreSQL, Redis | 加密貨幣交易平台 |
| 8 | **4URBABE** | HTML5, CSS3, Bootstrap, jQuery | 寵物社群平台 |
| 9 | **MVC-Claude** | Claude Code 整合 | AI 開發工具 |
| 10 | **MVC-Showcase** | Next.js（本專案） | 作品集網站 |

---

### 技術選型

| 層級 | 技術 | 選用原因 |
|------|------|---------|
| 框架 | **Next.js 15 (App Router)** | Vercel 原生支援、SSG、效能優異 |
| 語言 | **TypeScript** | 型別安全、開發體驗佳 |
| 樣式 | **Tailwind CSS 4** | 快速 UI 開發、響應式設計 |
| 動畫 | **Framer Motion** | 流暢過場、滾動觸發效果 |
| 國際化 | **next-intl** | 雙語支援（EN/ZH）、App Router 相容 |
| 內容 | **MDX** | 富文本專案描述、可嵌入元件 |
| 部署 | **Vercel** | 零設定 Next.js 託管、邊緣網路 |
| 分析 | **Vercel Analytics** | 內建效能追蹤 |
| 圖示 | **Lucide React** | 一致性佳、輕量圖示庫 |

---

### 網站架構

```
/                          → 首頁 / Hero + 精選作品
/projects                  → 專案展示（可篩選方格）
/projects/[slug]           → 個別專案詳細頁面
/about                     → 關於我 + 技能 + 時間軸
/blog（Phase 2 可選）       → 技術部落格文章
```

#### 雙語路由設計

```
/en/...                    → 英文版本
/zh/...                    → 中文（繁體）版本
/（根路徑）                 → 自動偵測或預設英文
```

---

### 專案目錄結構

```
mvc-showcase/
├── public/
│   ├── images/
│   │   └── projects/          # 專案截圖與縮圖
│   ├── og/                    # Open Graph 圖片
│   └── favicon.ico
├── src/
│   ├── app/
│   │   ├── [locale]/
│   │   │   ├── layout.tsx
│   │   │   ├── page.tsx           # 首頁
│   │   │   ├── projects/
│   │   │   │   ├── page.tsx       # 專案展示
│   │   │   │   └── [slug]/
│   │   │   │       └── page.tsx   # 專案詳細
│   │   │   └── about/
│   │   │       └── page.tsx       # 關於頁面
│   │   ├── layout.tsx             # 根佈局
│   │   └── globals.css
│   ├── components/
│   │   ├── layout/
│   │   │   ├── Header.tsx
│   │   │   ├── Footer.tsx
│   │   │   ├── Navigation.tsx
│   │   │   └── LanguageSwitcher.tsx
│   │   ├── home/
│   │   │   ├── Hero.tsx
│   │   │   ├── FeaturedProjects.tsx
│   │   │   ├── SkillsOverview.tsx
│   │   │   └── TechStackCloud.tsx
│   │   ├── projects/
│   │   │   ├── ProjectCard.tsx
│   │   │   ├── ProjectGrid.tsx
│   │   │   ├── ProjectFilter.tsx
│   │   │   └── ProjectDetail.tsx
│   │   ├── about/
│   │   │   ├── Timeline.tsx
│   │   │   └── SkillRadar.tsx
│   │   └── shared/
│   │       ├── AnimatedSection.tsx
│   │       ├── TechBadge.tsx
│   │       └── ThemeToggle.tsx
│   ├── data/
│   │   └── projects.ts            # 專案資料與描述
│   ├── i18n/
│   │   ├── request.ts
│   │   └── routing.ts
│   ├── messages/
│   │   ├── en.json                # 英文翻譯
│   │   └── zh.json                # 中文翻譯
│   └── lib/
│       └── utils.ts
├── claude/
│   └── docs/                      # 實施文件（本檔案）
├── next.config.ts
├── tailwind.config.ts
├── tsconfig.json
├── package.json
├── vercel.json
└── README.md
```

---

### 實施階段

#### 第一階段：專案初始化

- [ ] 初始化 Next.js 15 專案（TypeScript + Tailwind CSS）
- [ ] 設定 `next-intl` 雙語路由（EN/ZH）
- [ ] 建立專案目錄結構
- [ ] 設定 ESLint、Prettier
- [ ] 初始化 Git 倉庫
- [ ] 建立 `vercel.json` 設定檔
- [ ] 建立基本佈局（Header、Footer、Navigation）

#### 第二階段：核心頁面

- [ ] **首頁**：Hero 動畫介紹區塊、精選專案輪播、技術棧總覽
- [ ] **專案展示**：依分類篩選的方格（AI、行動、金融科技、區塊鏈、網頁）、搜尋功能
- [ ] **專案詳細頁**：截圖、技術標籤、描述、連結（GitHub/線上 Demo）、AI 編程亮點
- [ ] **關於頁面**：個人介紹、技能時間軸、技術棧雷達圖

#### 第三階段：內容與資料

- [ ] 建立所有 8 個活躍專案的雙語描述資料結構
- [ ] 準備專案截圖與縮圖
- [ ] 撰寫所有頁面的雙語內容
- [ ] 建立雙語翻譯 JSON 檔案（en.json、zh.json）

#### 第四階段：視覺美化與動畫

- [ ] 深色/淺色主題切換
- [ ] 滾動觸發動畫（Framer Motion）
- [ ] 頁面切換過場動畫
- [ ] 響應式設計（行動裝置優先）
- [ ] 載入狀態與骨架 UI
- [ ] 專案上的「AI Vibe Coding」視覺標記

#### 第五階段：SEO 與效能

- [ ] Open Graph 中繼標籤（雙語）
- [ ] 動態 OG 圖片生成
- [ ] 結構化資料（JSON-LD）
- [ ] Sitemap 生成
- [ ] 效能優化（圖片優化、延遲載入）
- [ ] Lighthouse 分數目標：效能 95+、無障礙 100

#### 第六階段：部署上線

- [ ] Vercel 專案設定與連結
- [ ] 環境變數設定
- [ ] 自訂網域設定（可選）
- [ ] Vercel Analytics 整合
- [ ] 正式部署與驗證

#### 第七階段：進階功能（可選）

- [ ] MDX 部落格區塊
- [ ] GitHub 活動整合
- [ ] 聯絡表單
- [ ] RSS 訂閱
- [ ] PDF 履歷下載（雙語）

---

### 專案分類篩選

| 分類 | 專案 | 標籤顏色 |
|------|------|---------|
| AI / 機器學習 | Neo4j_Graphiti, Saria | 紫色 |
| 區塊鏈 / Web3 | Polyrobot | 藍色 |
| 行動開發 | BabyPet, BabyPet iOS | 綠色 |
| 金融科技 / 交易 | 企業銀行平台, UltraDing | 琥珀色 |
| 網頁平台 | 4URBABE | 青色 |
| 開發工具 | MVC-Claude, Neo4j_Graphiti | 灰色 |

---

### AI Vibe Coding 展示策略

每個專案卡片與詳細頁面應突顯：

1. **使用的 AI 工具** — 輔助開發的 AI 工具（Claude、GPT-4、Copilot 等）
2. **人機協作比例** — 視覺化呈現協作程度
3. **Vibe Coding 亮點** — AI 加速開發的關鍵時刻
4. **前後對比** — 展示 AI 賦能 vs. 傳統開發的差異

---

### 設計準則

- **主題**：現代、極簡、開發者導向，帶有微妙的 AI 美學
- **配色方案**：深色模式為主、淺色模式為輔。各專案分類對應強調色
- **字型**：Inter（內文）、JetBrains Mono（程式碼）、Noto Sans TC（中文）
- **版面**：Bento grid 風格、不對稱卡片、充裕留白
- **動態效果**：細微、有意義的動畫，避免花俏效果
- **行動裝置**：完整行動裝置最佳化、觸控友善互動

---

### 主要套件依賴

```json
{
  "next": "^15.x",
  "react": "^19.x",
  "typescript": "^5.x",
  "tailwindcss": "^4.x",
  "next-intl": "^4.x",
  "framer-motion": "^11.x",
  "lucide-react": "^0.4xx",
  "@vercel/analytics": "^1.x"
}
```

---

### 成功標準

- Lighthouse 效能分數：95+
- Lighthouse 無障礙分數：100
- 完整雙語支援（EN/ZH）含語言切換器
- 展示所有 8 個活躍專案，含描述、截圖、技術棧
- 成功部署並可於 Vercel 存取
- 跨所有斷點的響應式設計
- 深色/淺色主題支援
- 3G 網路下頁面載入 < 2 秒（通過 Core Web Vitals）
