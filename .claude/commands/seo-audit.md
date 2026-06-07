# SEO Audit — 7 Parallel Agents

Run a full SEO audit on a URL using 7 specialized agents in parallel.

**Usage:** `/seo-audit https://example.com`

---

When this command is invoked with a URL, launch all 7 agents simultaneously using the Agent tool. Do NOT run them sequentially — all 7 must run in parallel in a single message.

## Agent Definitions

### Agent 1 — Technical SEO
Analyze `$URL` for technical SEO issues:
- Page load speed signals (render-blocking resources, image sizes, minification)
- Mobile-friendliness indicators
- HTTPS and security headers
- Crawlability signals (robots meta, canonical tags, noindex risks)
- Core Web Vitals indicators visible in the HTML
- Broken or redirect-chained internal links visible in source
Output: numbered list of issues with severity (Critical / High / Medium / Low) and exact fix for each.

### Agent 2 — On-Page Analysis
Analyze `$URL` for on-page SEO:
- Title tag: length, keyword placement, click appeal
- Meta description: length, keyword, CTA presence
- H1/H2/H3 structure and keyword usage
- Keyword density and natural usage in body copy
- Internal linking anchor text quality
- URL slug structure
Output: numbered list of issues with severity and exact recommended fix or rewrite.

### Agent 3 — Content Quality (E-E-A-T)
Analyze `$URL` for E-E-A-T signals:
- Author credentials and bio presence
- First-hand experience signals in copy
- External citations and source links
- Trust signals (awards, press mentions, case studies)
- Content depth vs. top-ranking competitors (based on visible content)
- Outdated information risks
Output: E-E-A-T score (1–10) per dimension with specific improvement actions.

### Agent 4 — Schema Markup
Analyze `$URL` for structured data:
- Existing schema types detected (JSON-LD, Microdata)
- Missing schema opportunities for page type (Article, FAQ, LocalBusiness, Product, HowTo, BreadcrumbList, etc.)
- Schema errors or incomplete implementations
Output: list of missing schema types + ready-to-use JSON-LD code blocks for the top 3 opportunities.

### Agent 5 — Image Optimization
Analyze `$URL` for image SEO:
- Missing or weak alt text on all images
- Images without width/height attributes (CLS risk)
- Non-WebP formats still in use
- Large images that need compression
- Decorative images missing aria-hidden
Output: image-by-image audit table with current state and recommended fix.

### Agent 6 — AI Search / GEO (Generative Engine Optimization)
Analyze `$URL` for visibility in AI search engines (ChatGPT, Claude, Perplexity, Google SGE):
- Is content structured for direct answer extraction?
- Are there clear definition statements, lists, and tables AI can cite?
- Does the page have an About/FAQ section with question-format headings?
- Is the brand/entity clearly defined with consistent NAP or brand signals?
- Does the content directly answer the primary query in the first 100 words?
- Citation-worthiness: does the page demonstrate unique data, stats, or original research?
Output: GEO score (1–10) with specific rewrites and structural changes to improve AI citation rate.

### Agent 7 — Strategic Planning
Based on a full-page analysis of `$URL`, create a prioritized 30-day SEO action plan:
- Week 1: Quick wins (fixes under 1 hour each)
- Week 2: On-page and content improvements
- Week 3: Schema and technical fixes
- Week 4: GEO optimization and content expansion
For each action include: effort (Low/Med/High), impact (Low/Med/High), and owner (Dev/Content/SEO).

---

## Output Format

After all 7 agents complete, compile results into a single audit report:

```
# SEO Audit Report — [URL]
Date: [DATE]

## Executive Summary
[3-sentence summary of biggest opportunities]

## Critical Issues (fix this week)
[Pull highest severity items from all agents]

## Agent Reports
### 1. Technical SEO
### 2. On-Page Analysis
### 3. Content Quality (E-E-A-T)
### 4. Schema Markup
### 5. Image Optimization
### 6. AI Search / GEO
### 7. Strategic 30-Day Plan

## Quick Win Code Snippets
[Schema JSON-LD, meta tag rewrites, alt text fixes ready to copy-paste]
```

Save the completed report to `SEO-Project/Reports/audits/[domain]-audit-[date].md`.
