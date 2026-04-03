# Changelog — mvc-showcase

## [Unreleased]

---

## [2026-04-03]

### Fixed
- Update project badges to accurate tech stacks
  - UltraTrading: remove Streamlit / FastAPI / Redis / Docker → add Supabase Edge Functions / pandas-numpy / Discord Bot
  - PolyRobot: `wagmi` → `wagmi + RainbowKit` to reflect browser wallet plugin

### Changed
- `Unstructured Document ETL` replaces `PPTX Parser` badge in TWST card and Tech Stack

---

## [2026-04-03] — Data Engineering Positioning

### Added
- Hero subtitle: `Financial Data Engineering · LLM Signal Systems · Full-Stack Delivery`
- Tech Stack: new **Data Engineering** column (ETL Pipeline Design, Multi-source Aggregation, Unstructured Document ETL, Financial APIs, Closed-loop Feedback, Cron Orchestration)

### Changed
- TWST card description rewritten to angle-3 narrative: end-to-end pipeline framing
- TWST badges: replace `TWSE MIS` / `OpenAI / Gemini` → `Claude / Gemini` / `Unstructured Document ETL` / `Exchange APIs`
- Tech Stack grid: 5 columns → 6 columns

---

## [2026-04-02] — Content & Protection

### Added
- Disable right-click, text selection, and copy shortcuts (contextmenu / keydown / CSS user-select)

### Changed
- CTA quote replaced with MBA advisor LinkedIn recommendation (資管系碩士班指導教授)
- Quote trimmed: removed "— I congratulate his CTO position." line, reduced font size

---

## [2026-04-02] — Initial Deploy Fix

### Fixed
- Removed `mvc.softwidom.com` from Vercel custom domains (caused 404 due to DNS conflict with nginx reverse proxy)

---

## [2026-03-xx] — Portfolio Buildout

### Added
- Initial portfolio site — static HTML + Tailwind CDN
- Avatar photo with Ghibli badge
- GoatCounter analytics
- Patents section (7 patents)
- Career timeline section
- Project cards: TWST, UltraTrading, PolyRobot, Saria, BabyPet, 4URBABE, Neo4j-OpenAI, Crypto Wallet
- AI Workflow section
- Orange CTA banner with professor quote
- Mobile nav fixes, footer with social icons
- Scroll animations
