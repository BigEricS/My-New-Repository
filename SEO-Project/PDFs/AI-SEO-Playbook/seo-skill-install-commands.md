# Claude SEO — Install & Command Reference

> Repo: AgriciDaniel/claude-seo (MIT, open-source, public)
> Purpose: setup + command reference for installing the actual SEO audit skill in Claude Code. Pairs with `seo-audit-skill-brief.md` (the concept brief).

## What This Actually Is

A real, maintained Claude Code plugin — 25 sub-skills, 18 sub-agents, optional extensions. Free and open-source under MIT. No paid tier required for core functionality.

Scoring breakdown (7 weighted categories):
- Content Quality — 23%
- Technical SEO — 22%
- On-Page SEO — 20%
- Schema — 10%
- Performance / Core Web Vitals (incl. INP) — 10%
- AI Search Readiness (GEO) — 10%
- Images — 5%

Auto-detects business type from the homepage: SaaS, local service, e-commerce, publisher, agency — relevant since SDM targets local service businesses specifically.

## Install

**Prerequisites:** Python 3.10+, Claude Code CLI.

**Option A — Plugin marketplace (recommended, Claude Code 1.0.33+):**
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

Installer copies skills into your Claude Code skills directory and writes the slash commands. It's idempotent — safe to re-run anytime. Creates a venv at `~/.claude/skills/seo/.venv/`.

**Verify install:** open Claude Code and type `/seo` — should list 16 commands.

**First run:**
```
/seo audit https://your-site.com
```
Realistic runtime: 8–12 minutes (not the "3 minutes" the marketing deck claimed). Output is a 0–100 health score plus a prioritized action plan.

## Command Reference

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

**Most relevant for SDM's local service clients:** `local` and `maps`. The skill auto-suggests `/seo local` when it detects local-business signals (phone number, address, service area language, "serving [city]," Google Maps embed).

## Optional Extensions

Each requires its own install + API key.

**DataForSEO** (`./extensions/dataforseo/install.sh`) — 22 commands across 9 API modules. Live SERP data, keyword research, backlinks, AI mention tracking.
```
/seo dataforseo serp <keyword>          # Google organic results
/seo dataforseo serp-youtube <keyword>  # YouTube search results
/seo dataforseo content <keyword/url>   # Content analysis and trends
/seo dataforseo listings <keyword>      # Business listings search
/seo dataforseo ai-scrape <query>       # ChatGPT web scraper for GEO
/seo dataforseo ai-mentions <keyword>   # LLM mention tracking
```

**Firecrawl** (`./extensions/firecrawl/install.sh`) — full-site crawl, used by `audit` for URL discovery.
```
/seo firecrawl crawl https://example.com
/seo firecrawl map https://example.com
```

**Banana** (`./extensions/banana/install.sh`) — AI image generation via Gemini (nanobanana-mcp). OG images, hero graphics, product photos, schema images.

## What "GEO" Actually Means Here

Claude SEO follows Google's stated position: AEO and GEO are not a separate discipline from SEO — AI Overviews and AI Mode run on the same ranking systems as classic search, and the eligibility floor is normal indexation.

What it scores instead of buzzwords:
- Passage citability (134–167 word self-contained answer blocks)
- Question-based heading hierarchy
- Attribution density
- Entity presence across Wikipedia, Reddit, YouTube, LinkedIn

It explicitly pushes back on three common claims: that `llms.txt` is a citation lever, that "content chunking" helps AI specifically, and that AI search needs its own separate keyword strategy.

## Notes for SDM Application

- This is a real tool you can plug into client work today — not just a concept. The 30-day rollout plan from the concept brief still applies; this file is the "how to actually run it" companion.
- `seo-local` + `seo-maps` are the two sub-skills most directly reusable for your existing local-service client base.
- Before pitching this as a differentiator, run it on 2–3 real client sites first to see what the actual output and health scores look like — useful for calibrating what you promise in a sales conversation.
- If you want live SERP/keyword data instead of static crawl results, the DataForSEO extension is the one to prioritize installing.
