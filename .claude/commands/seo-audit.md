# SEO Audit — 7 Parallel Agents

Run a full SEO + GEO audit using the AgriciDaniel/claude-seo skill.

**Usage:** `/seo audit https://example.com`
**Runtime:** 8–12 minutes (not 3 — the marketing deck overstates this)
**Source:** `AgriciDaniel/claude-seo` (MIT, open-source, free core)

---

## Install

**Option A — Plugin marketplace (Claude Code 1.0.33+, recommended):**
```
/plugin marketplace add AgriciDaniel/claude-seo
/plugin install claude-seo@agricidaniel-claude-seo
```

**Option B — Manual clone (macOS/Linux):**
```
git clone --depth 1 https://github.com/AgriciDaniel/claude-seo.git
bash claude-seo/install.sh
```

**Option B — Manual clone (Windows):**
```
git clone --depth 1 https://github.com/AgriciDaniel/claude-seo.git
powershell -ExecutionPolicy Bypass -File claude-seo\install.ps1
```

Verify: open Claude Code and type `/seo` — should list 16 commands.

**First run:**
```
/seo audit https://your-site.com
```

---

## Scoring Breakdown (7 Weighted Categories)

| Category | Weight | Target |
|---|---|---|
| Content Quality (E-E-A-T) | 23% | 70+ |
| Technical SEO | 22% | 80+ |
| On-Page SEO | 20% | 75+ |
| Schema Markup | 10% | — |
| Performance / Core Web Vitals (incl. INP) | 10% | — |
| AI Search Readiness (GEO) | 10% | — |
| Images | 5% | — |

Auto-detects business type from homepage: SaaS, local service, e-commerce, publisher, agency.

---

## Full Command Reference

All commands: `/seo <command> <url>`

| Command | What it does |
|---|---|
| `audit` | Full-site audit, parallel analysis across all sub-agents |
| `page` | Deep single-page analysis |
| `technical` | Technical SEO audit across 9 categories |
| `content` | E-E-A-T and content quality analysis |
| `schema` | Schema markup detection, validation, generation |
| `geo` | AI Overviews / Generative Engine Optimization |
| `images` | Image optimization analysis |
| `sitemap` | Analyze existing XML sitemap |
| `sitemap-gen` | Generate new sitemap with industry templates |
| `plan` | Strategic SEO planning |
| `compete` | Competitor comparison page generation |
| `hreflang` | International SEO / hreflang audit and generation |
| `programmatic` | Analysis/planning for pages generated at scale |
| `local` | Local SEO — Google Business Profile, citations, reviews, map pack |
| `maps` | Maps intelligence (requires DataForSEO extension) |

**Most relevant for SDM local service clients:** `/seo local` and `/seo maps`
The skill auto-suggests `/seo local` when it detects local-business signals.

---

## Optional Extensions

**DataForSEO** (priority install for live data):
```
./extensions/dataforseo/install.sh
```
Key commands:
```
/seo dataforseo serp <keyword>          # Google organic results
/seo dataforseo serp-youtube <keyword>  # YouTube search results
/seo dataforseo content <keyword/url>   # Content analysis and trends
/seo dataforseo listings <keyword>      # Business listings search
/seo dataforseo ai-scrape <query>       # ChatGPT web scraper for GEO
/seo dataforseo ai-mentions <keyword>   # LLM mention tracking
```

**Firecrawl** — full-site crawl, used by `audit` for URL discovery:
```
./extensions/firecrawl/install.sh
```

**Banana** — AI image generation (OG images, hero graphics, schema images):
```
./extensions/banana/install.sh
```

---

## What GEO Actually Scores

The skill follows Google's position: AI Overviews run on the same ranking
systems as classic search. GEO is not a separate discipline — it's good SEO.

What it actually measures:
- **Passage citability** — 134–167 word self-contained answer blocks
- **Question-based heading hierarchy** — H2/H3 as questions
- **Attribution density** — external citations and sources
- **Entity presence** — Wikipedia, Reddit, YouTube, LinkedIn

What it does NOT treat as GEO levers (pushes back on these claims):
- `llms.txt` as a citation driver
- "Content chunking" as an AI-specific tactic
- Separate keyword strategy for AI search

---

## Automate the Fixes

After the audit, feed results back into Claude:

```
Based on the SEO audit results in SEO-Project/Reports/audits/[filename].md,
build me an agent that implements the top 10 highest-priority fixes.
Outputs should include:
- Auto-generated meta tags for every flagged page
- JSON-LD schema markup ready to inject
- Content briefs for the top 3 keyword gaps identified
```

---

## Notes for SDM

- Run on 2–3 real client sites before pitching — calibrate what you promise based on actual output
- `/seo local` + `/seo maps` are the two sub-skills most directly applicable to local service clients
- DataForSEO extension is the priority add-on for live SERP/keyword data
- The 30-day plan in `SEO-Project/Prompts/` still applies as the rollout framework
