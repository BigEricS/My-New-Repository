# Claude SEO Prompts — GEO (Generative Engine Optimization)

## What is GEO?
Optimizing content to be cited and surfaced by AI search engines:
ChatGPT, Claude, Perplexity, Google AI Overviews, Bing Copilot.

**Key reality check (per AgriciDaniel/claude-seo + Google):**
AI Overviews run on the same ranking systems as classic search.
GEO is not a separate discipline — it's good SEO done well.

What actually moves GEO scores:
- **Passage citability** — 134–167 word self-contained answer blocks
- **Question-based headings** — H2/H3 phrased as questions
- **Attribution density** — external citations and credible sources
- **Entity presence** — Wikipedia, Reddit, YouTube, LinkedIn mentions

What does NOT move GEO scores (common myths):
- `llms.txt` files
- "Content chunking" as an AI-specific technique
- Separate keyword lists for AI search

---

## 1. AI Citation Audit
```
Analyze this page content for AI search engine citation potential:
[PASTE PAGE CONTENT]

Score each factor 1-10:
- Direct answer in first 100 words
- Clear entity definition (who/what is this page about?)
- Structured lists and tables for easy extraction
- Question-format headings (H2/H3 as questions)
- Unique data, statistics, or original research
- FAQ section presence
- Author expertise signals

For each low score, give the exact rewrite needed.
```

## 2. AI-Optimized FAQ Generator
```
The target keyword is: [KEYWORD]
The page is about: [TOPIC]

Generate 10 FAQ questions that:
1. Match how people ask this in ChatGPT/Perplexity
2. Have concise, direct answers (2-3 sentences each) that AI can extract
3. Cover related subtopics to capture long-tail AI queries
4. Are formatted as FAQ schema-ready JSON-LD

Output both the human-readable FAQ section AND the JSON-LD schema.
```

## 3. Entity Optimization
```
My business/brand: [NAME]
Location: [CITY, STATE]
Services: [SERVICES]
Website: [URL]

How should I define my entity across the web to maximize AI search visibility?
Give me:
1. The exact brand description to use consistently (50 words)
2. Where to publish it (Google Business, schema, about page, etc.)
3. Citation sources to target for AI training data
4. How to structure my About page for entity clarity
```

## 4. AI vs Google Content Gap
```
Here is my existing article: [PASTE ARTICLE]
Target keyword: [KEYWORD]

This article ranks well on Google but isn't being cited by AI search engines.
Identify what's missing and rewrite the intro, add an FAQ section, and
restructure one existing section to maximize AI citation potential.
```

## 5. GEO Competitive Analysis
```
Search for "[KEYWORD]" in ChatGPT or Perplexity and paste the AI answer here:
[PASTE AI SEARCH RESULT]

My page URL: [URL]
My page content summary: [SUMMARY]

Why is my page not being cited? What specific changes would get it cited instead?
```
