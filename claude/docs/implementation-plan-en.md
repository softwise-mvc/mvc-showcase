# MVC-Showcase: Personal Developer Portfolio Website

## Implementation Plan

### Project Overview

A bilingual (English/Chinese) personal portfolio website showcasing Marvin Chang's development projects and AI-assisted coding capabilities. The site aggregates projects from the local `~/Projects/` directory into a polished, deployable Vercel application.

---

### Portfolio Projects Inventory

| # | Project | Tech Stack | Category |
|---|---------|-----------|----------|
| 1 | **Polyrobot** | Next.js, TypeScript, wagmi, Supabase, Polygon | Blockchain / Prediction Market |
| 2 | **Neo4j_Graphiti** | Python, Neo4j, OpenAI, Docker | AI Memory System |
| 3 | **BabyPet** | Flutter, Firebase, Cross-Platform | Mobile App / Pet Health |
| 4 | **BabyPet iOS** | Swift, Firebase, iOS Native | Mobile App / iOS |
| 5 | **Enterprise Banking Platform** *(NDA)* | Node.js, Express, Swift, Kotlin, Flutter | FinTech / Corporate Banking |
| 6 | **Saria** | Python, OpenAI GPT-4o, Flatlib, LINE Bot | AI / Astrology Content |
| 7 | **UltraDing** | Python, FastAPI, Streamlit, PostgreSQL, Redis | Crypto Trading Platform |
| 8 | **4URBABE** | HTML5, CSS3, Bootstrap, jQuery | Pet Community Platform |
| 9 | **MVC-Claude** | Claude Code Integration | AI Development Tooling |
| 10 | **MVC-Showcase** | Next.js (this project) | Portfolio Website |

---

### Tech Stack

| Layer | Technology | Rationale |
|-------|-----------|-----------|
| Framework | **Next.js 15 (App Router)** | Native Vercel support, SSG, performance |
| Language | **TypeScript** | Type safety, developer experience |
| Styling | **Tailwind CSS 4** | Rapid UI development, responsive design |
| Animation | **Framer Motion** | Smooth transitions, scroll-triggered effects |
| i18n | **next-intl** | Bilingual support (EN/ZH), App Router compatible |
| Content | **MDX** | Rich project descriptions with components |
| Deployment | **Vercel** | Zero-config Next.js hosting, edge network |
| Analytics | **Vercel Analytics** | Built-in performance tracking |
| Icons | **Lucide React** | Consistent, lightweight icon set |

---

### Site Architecture

```
/                          → Home / Hero + highlights
/projects                  → Project gallery (filterable grid)
/projects/[slug]           → Individual project detail page
/about                     → About me + skills + timeline
/blog (optional Phase 2)   → Technical blog posts
```

#### Bilingual Routing

```
/en/...                    → English version
/zh/...                    → Chinese (Traditional) version
/ (root)                   → Auto-detect or default to English
```

---

### Project Directory Structure

```
mvc-showcase/
├── public/
│   ├── images/
│   │   └── projects/          # Project screenshots & thumbnails
│   ├── og/                    # Open Graph images
│   └── favicon.ico
├── src/
│   ├── app/
│   │   ├── [locale]/
│   │   │   ├── layout.tsx
│   │   │   ├── page.tsx           # Home
│   │   │   ├── projects/
│   │   │   │   ├── page.tsx       # Project gallery
│   │   │   │   └── [slug]/
│   │   │   │       └── page.tsx   # Project detail
│   │   │   └── about/
│   │   │       └── page.tsx       # About page
│   │   ├── layout.tsx             # Root layout
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
│   │   └── projects.ts            # Project metadata & descriptions
│   ├── i18n/
│   │   ├── request.ts
│   │   └── routing.ts
│   ├── messages/
│   │   ├── en.json                # English translations
│   │   └── zh.json                # Chinese translations
│   └── lib/
│       └── utils.ts
├── claude/
│   └── docs/                      # Implementation docs (this file)
├── next.config.ts
├── tailwind.config.ts
├── tsconfig.json
├── package.json
├── vercel.json
└── README.md
```

---

### Implementation Phases

#### Phase 1: Project Initialization

- [ ] Initialize Next.js 15 project with TypeScript + Tailwind CSS
- [ ] Configure `next-intl` for EN/ZH bilingual routing
- [ ] Set up project directory structure
- [ ] Configure ESLint, Prettier
- [ ] Initialize Git repository
- [ ] Create `vercel.json` configuration
- [ ] Set up basic layout (Header, Footer, Navigation)

#### Phase 2: Core Pages

- [ ] **Home page**: Hero section with animated introduction, featured projects carousel, tech stack overview
- [ ] **Projects gallery**: Filterable grid by category (AI, Mobile, FinTech, Blockchain, Web), search functionality
- [ ] **Project detail page**: Screenshots, tech stack badges, description, links (GitHub/live demo), AI-coding highlights
- [ ] **About page**: Personal introduction, skills timeline, tech stack radar chart

#### Phase 3: Content & Data

- [ ] Create project data structure with bilingual descriptions for all 8 active projects
- [ ] Prepare project screenshots and thumbnails
- [ ] Write bilingual content for all pages
- [ ] Create bilingual translation JSON files (en.json, zh.json)

#### Phase 4: Visual Polish & Animation

- [ ] Dark/light theme toggle
- [ ] Scroll-triggered animations (Framer Motion)
- [ ] Page transition animations
- [ ] Responsive design (mobile-first)
- [ ] Loading states and skeleton UI
- [ ] "AI Vibe Coding" visual indicators on projects

#### Phase 5: SEO & Performance

- [ ] Open Graph meta tags (bilingual)
- [ ] Dynamic OG image generation
- [ ] Structured data (JSON-LD)
- [ ] Sitemap generation
- [ ] Performance optimization (image optimization, lazy loading)
- [ ] Lighthouse score targets: Performance 95+, Accessibility 100

#### Phase 6: Deployment

- [ ] Vercel project setup and linking
- [ ] Environment variables configuration
- [ ] Custom domain setup (optional)
- [ ] Vercel Analytics integration
- [ ] Production deployment and verification

#### Phase 7: Enhancements (Optional)

- [ ] Blog section with MDX posts
- [ ] GitHub activity integration
- [ ] Contact form
- [ ] RSS feed
- [ ] PDF resume download (bilingual)

---

### Project Categories for Filtering

| Category | Projects | Badge Color |
|----------|----------|-------------|
| AI / Machine Learning | Neo4j_Graphiti, Saria | Purple |
| Blockchain / Web3 | Polyrobot | Blue |
| Mobile Development | BabyPet, BabyPet iOS | Green |
| FinTech / Trading | Enterprise Banking Platform, UltraDing | Amber |
| Web Platform | 4URBABE | Teal |
| Dev Tooling | MVC-Claude, Neo4j_Graphiti | Gray |

---

### AI Vibe Coding Showcase Strategy

Each project card and detail page should highlight:

1. **AI Tools Used** — Which AI tools assisted development (Claude, GPT-4, Copilot, etc.)
2. **Human + AI Ratio** — Visual indicator showing collaboration level
3. **Vibe Coding Highlights** — Notable moments where AI accelerated development
4. **Before/After** — Where applicable, show what AI enabled vs. traditional approach

---

### Design Guidelines

- **Theme**: Modern, minimal, developer-focused with subtle AI aesthetic
- **Color Palette**: Dark mode primary, light mode secondary. Accent colors per project category
- **Typography**: Inter (body), JetBrains Mono (code), Noto Sans TC (Chinese)
- **Layout**: Bento grid inspired, asymmetric cards, generous whitespace
- **Motion**: Subtle, purposeful animations. No gratuitous effects
- **Mobile**: Full mobile optimization, touch-friendly interactions

---

### Key Dependencies

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

### Success Criteria

- Lighthouse Performance: 95+
- Lighthouse Accessibility: 100
- Fully bilingual (EN/ZH) with language switcher
- All 8 active projects showcased with descriptions, screenshots, tech stacks
- Deployed and accessible on Vercel
- Mobile responsive across all breakpoints
- Dark/light theme support
- Page load < 2s on 3G connection (Core Web Vitals pass)
