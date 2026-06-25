# Claude SEO — Full Reference

**Repo:** `AgriciDaniel/claude-seo` (MIT, open-source, 9.8k stars, 1.4k forks)
**Runtime:** 10–15 minutes for full audit
**Requirements:** Python 3.10+, Claude Code CLI

---

## Install

**Option A — Plugin marketplace (recommended, Claude Code 1.0.33+):**
```
/plugin marketplace add AgriciDaniel/claude-seo
/plugin install claude-seo@agricidaniel-claude-seo
```

**Option B — Manual (macOS/Linux):**
```
git clone --depth 1 https://github.com/AgriciDaniel/claude-seo.git
bash claude-seo/install.sh
```

**Option B — Manual (Windows):**
```
git clone --depth 1 https://github.com/AgriciDaniel/claude-seo.git
powershell -ExecutionPolicy Bypass -File claude-seo\install.ps1
```

**Uninstall:**
```
curl -fsSL https://raw.githubusercontent.com/AgriciDaniel/claude-seo/main/uninstall.sh | bash
```

Verify install: type `/seo` in Claude Code — should list 16+ commands.

---

## Scoring Breakdown (7 Weighted Categories)

| Category | Weight |
|---|---|
| Content Quality (E-E-A-T) | 23% |
| Technical SEO | 22% |
| On-Page SEO | 20% |
| Schema Markup | 10% |
| Performance / Core Web Vitals (LCP, INP, CLS) | 10% |
| AI Search Readiness (GEO) | 10% |
| Images | 5% |

Auto-detects business type from homepage: SaaS, local service, e-commerce, publisher, agency.

---

## Full Command Reference

All commands: `/seo <command> <url>`

| Command | What it does |
|---|---|
| `audit <url>` | Full-site audit — parallel across all 18 sub-agents |
| `page <url>` | Deep single-page analysis |
| `technical <url>` | Technical SEO across 9 categories |
| `content <url>` | E-E-A-T and content quality (QRG-aligned, Sept 2025) |
| `schema <url>` | Detect, validate, and generate Schema.org markup |
| `geo <url>` | AI Overviews / Generative Engine Optimization |
| `images <url>` | Image optimization analysis |
| `local <url>` | Local SEO — GBP, citations, reviews, map pack |
| `backlinks <url>` | Backlink profile analysis |
| `ecommerce <url>` | E-commerce and marketplace intelligence |
| `cluster <keyword>` | SERP-based semantic keyword clustering |
| `drift [stage] <url>` | SEO regression monitoring |
| `sitemap <url>` | Analyze existing XML sitemap |
| `sitemap-gen <url>` | Generate new sitemap with industry templates |
| `plan <url>` | Strategic SEO planning |
| `compete <url>` | Competitor comparison page generation |
| `hreflang <url>` | International SEO / hreflang audit and generation |
| `programmatic <url>` | Analysis/planning for pages generated at scale |
| `google <command>` | GSC, PageSpeed, CrUX, GA4, PDF reports |
| `maps <url>` | Maps intelligence (requires DataForSEO extension) |
| `firecrawl <command>` | Full-site crawling (requires Firecrawl extension) |
| `dataforseo <command>` | Live SEO data (requires DataForSEO extension) |

**Most relevant for SDM local service clients:** `/seo local` + `/seo maps`
Skill auto-suggests `/seo local` when it detects local-business signals.

---

## Google API Integration (4-Tier)

| Tier | APIs | What You Get |
|---|---|---|
| 0 | PageSpeed Insights, CrUX, CrUX History | Core Web Vitals (no auth needed) |
| 1 | Search Console, Indexing API | Real impressions, clicks, index status |
| 2 | GA4 | Organic traffic data |
| 3 | Keyword Planner | Search volume |

---

## Optional Extensions

Install each separately — each requires its own API key.

| Extension | Install | What It Adds |
|---|---|---|
| **DataForSEO** | `./extensions/dataforseo/install.sh` | Live SERPs, keyword volumes, backlinks, AI mention tracking |
| **Firecrawl** | `./extensions/firecrawl/install.sh` | Full-site crawl + URL discovery for audit |
| **Banana** | `./extensions/banana/install.sh` | AI image generation (OG images, hero graphics) |
| **Ahrefs** | `./extensions/ahrefs/install.sh` | Backlink and organic data |
| **SE Ranking** | `./extensions/seranking/install.sh` | AI Share-of-Voice across ChatGPT, Gemini, Perplexity |
| **Profound** | `./extensions/profound/install.sh` | LLM citation tracking |
| **Bing Webmaster** | `./extensions/bing/install.sh` | Bing indexation + IndexNow |
| **Unlighthouse** | `./extensions/unlighthouse/install.sh` | Multi-page Lighthouse runner |

**Priority for SDM:** DataForSEO (live data) + SE Ranking (AI share-of-voice tracking)

Key DataForSEO commands:
```
/seo dataforseo serp <keyword>
/seo dataforseo serp-youtube <keyword>
/seo dataforseo ai-scrape <query>
/seo dataforseo ai-mentions <keyword>
/seo dataforseo listings <keyword>
```

---

## What GEO Actually Scores

Aligned with Google's AI Optimization Guide: AEO and GEO are rebranded SEO.
AI Overviews run on the same ranking systems as classic search.

What it scores:
- **Passage citability** — 134–167 word self-contained answer blocks
- **Question-based heading hierarchy** — H2/H3 phrased as questions
- **Attribution density** — external citations and credible sources
- **Entity presence** — Wikipedia, Reddit, YouTube, LinkedIn

What it does NOT treat as GEO levers:
- `llms.txt` (not a consumer AI citation signal)
- "Content chunking" as an AI-specific tactic
- Separate keyword strategy for AI search

---

## 10-Principle Methodology (4 Phases)

Every recommendation includes: the first-principle observation behind it, dependency relationships, a "how would we know this failed?" check, and a leading indicator.

1. **PERCEIVE** — Collect signals; audit assumptions
2. **ANALYZE** — First principles; lateral and system connections
3. **VALIDATE** — UX/brand fit; pressure-test findings
4. **ACT** — Ship artifacts; close feedback loops

---

## vs. Alternatives

| | Manual | Agency | Commercial Tool | Claude SEO |
|---|---|---|---|---|
| Time per audit | 4–8 hrs | 1–3 weeks | 10–45 min | 10–15 min |
| Cost | High | $2K–$15K+/mo | $99–$999/mo | Free |
| AI search awareness | Varies | Lagging | Lagging | Current |
| Falsifiability | No | No | No | Yes (per finding) |

---

## Automate the Fixes

After reviewing the audit output:

```
Based on the SEO audit results in SEO-Project/Reports/audits/[filename].md,
build me an agent that implements the top 10 highest-priority fixes.
Outputs should include:
- Auto-generated meta tags for every flagged page
- JSON-LD schema markup ready to inject
- Content briefs for the top 3 keyword gaps identified
```

---

## SDM Notes

- Run on 2–3 real client sites before pitching — calibrate what you promise from actual output
- `/seo local` + `/seo maps` are the most directly applicable for local service clients
- SE Ranking extension tracks AI share-of-voice across ChatGPT, Gemini, Perplexity — strong upsell data point
- Profound extension tracks LLM citations — useful for the "are you showing up in AI answers?" pitch
- The 30-day plan in `SEO-Project/Prompts/` is still the right rollout framework
