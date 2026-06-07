# SEO Audit — 7 Parallel Agents

Run a full SEO + GEO audit on a URL using 7 specialized agents in parallel.

**Usage:** `/seo audit https://example.com`

Source skill: `AgriciDaniel/claude-seo` on GitHub

---

When this command is invoked with a URL, launch all 7 agents simultaneously using the Agent tool.
All 7 must run in parallel in a single message — do NOT run them sequentially.

## Agent Definitions

### Agent 1 — Technical SEO
Analyze `$URL` for technical SEO issues:
- Page load speed signals (render-blocking resources, image sizes, minification)
- Mobile-friendliness indicators
- HTTPS and security headers
- Crawlability (robots meta, canonical tags, noindex risks, sitemap presence)
- Core Web Vitals indicators visible in the HTML
- Broken or redirect-chained internal links visible in source
Output: numbered list of issues with severity (Critical / High / Medium / Low) and exact fix.
Target score: 80+

### Agent 2 — On-Page Analysis
Analyze `$URL` for on-page SEO:
- Title tag: length, keyword placement, click appeal
- Meta description: length, keyword, CTA presence
- H1/H2/H3 structure and keyword usage
- Keyword density and natural usage in body copy
- Internal linking anchor text quality
- URL slug structure
Output: numbered list of issues with severity and exact recommended fix or rewrite.
Target score: 75+

### Agent 3 — Content Quality (E-E-A-T)
Analyze `$URL` for E-E-A-T signals:
- Author credentials and bio presence
- First-hand experience signals in copy
- External citations and source links
- Trust signals (awards, press mentions, case studies)
- Content depth vs. top-ranking competitors
- Outdated information risks
Output: E-E-A-T score (1–10) per dimension with specific improvement actions.
Target score: 70+

### Agent 4 — Schema Markup
Analyze `$URL` for structured data:
- Existing schema types detected (JSON-LD, Microdata)
- Missing schema opportunities (Article, FAQ, LocalBusiness, Product, HowTo, BreadcrumbList)
- Schema errors or incomplete implementations
Output: list of missing schema types + ready-to-use JSON-LD code blocks for top 3 opportunities.

### Agent 5 — Image Optimization
Analyze `$URL` for image SEO:
- Missing or weak alt text on all images
- Images without width/height attributes (CLS risk)
- Non-WebP formats in use
- Large images that need compression
- Decorative images missing aria-hidden
Output: image-by-image audit table with current state and recommended fix.

### Agent 6 — AI Search / GEO (Generative Engine Optimization)
Analyze `$URL` for visibility in AI search engines (ChatGPT, Claude, Perplexity, Google AI Overviews):
- Is content structured for direct answer extraction?
- Clear definition statements, lists, and tables AI can cite?
- Question-format H2/H3 headings?
- Entity clearly defined with consistent brand signals?
- Direct answer to primary query in first 100 words?
- Citation-worthiness: unique data, stats, or original research?
- AI crawler access (llms.txt present?)
- Brand mentions on platforms AI systems cite (YouTube, Reddit)
Output: GEO score (1–10) with specific rewrites and structural changes to improve AI citation rate.

### Agent 7 — Strategic Planning
Create a prioritized 30-day SEO action plan for `$URL`:
- **Week 1:** Foundation — fix critical crawl errors, broken links, sitemaps
- **Week 2:** On-page quick wins — title tags, H1 hierarchy, schema markup
- **Week 3:** Content upgrades — top 3 keyword gaps, lowest E-E-A-T pages
- **Week 4:** AI search visibility — build brand presence on YouTube/Reddit, generate llms.txt
For each action: effort (Low/Med/High), impact (Low/Med/High), owner (Dev/Content/SEO).

---

## Output Format

After all 7 agents complete, compile into a single audit report:

```
# SEO Audit Report — [URL]
Date: [DATE]

## Executive Summary
[3-sentence summary of biggest opportunities]

## Health Scores
- Technical SEO: [X]/100 (target: 80+)
- On-Page: [X]/100 (target: 75+)
- Content/E-E-A-T: [X]/100 (target: 70+)
- GEO/AI Search: [X]/10

## Critical Issues (fix this week)
[Highest severity items from all agents]

## Agent Reports
### 1. Technical SEO
### 2. On-Page Analysis
### 3. Content Quality (E-E-A-T)
### 4. Schema Markup
### 5. Image Optimization
### 6. AI Search / GEO
### 7. Strategic 30-Day Plan

## Quick Win Code Snippets
[Schema JSON-LD, meta tag rewrites, alt text fixes — copy-paste ready]
```

Save the completed report to `SEO-Project/Reports/audits/[domain]-audit-[YYYY-MM-DD].md`.

---

## Automate the Fixes

After reviewing the audit, run this follow-up prompt:

```
Based on the SEO audit results in SEO-Project/Reports/audits/[filename].md,
build me an agent that implements the top 10 highest-priority fixes.
Outputs should include:
- Auto-generated meta tags for every flagged page
- JSON-LD schema markup ready to inject
- Content briefs for the top 3 keyword gaps identified
```

---

## MCP Integrations for Live Data

Connect these MCP servers for real data instead of HTML analysis:

| Tool | MCP | What It Adds |
|---|---|---|
| DataForSEO | `dataforseo` | Live SERPs & keyword volumes |
| Semrush | `semrush` | Competitor intel & position tracking |
| Google Search Console | `gsc` | Real click & impression data |
| PageSpeed Insights | `pagespeed` | Core Web Vitals scoring |
