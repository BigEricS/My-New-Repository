# Claude SEO Prompts — Technical SEO

## 1. Schema Markup Generator
```
Generate JSON-LD schema markup for this page:
- Page type: [Article / FAQ / Product / LocalBusiness / HowTo]
- Title: [TITLE]
- Description: [DESCRIPTION]
- URL: [URL]
- [Additional fields depending on type]

Output only valid JSON-LD ready to paste into <head>.
```

## 2. robots.txt Audit
```
Review this robots.txt file and identify any issues:
[PASTE robots.txt]

Check for:
- Accidentally blocked important pages
- Missing sitemap reference
- Crawl budget waste
- Correct disallow patterns
```

## 3. Internal Linking Audit Prompt
```
Here is my site's page list with their target keywords:
[PASTE PAGE LIST WITH KEYWORDS]

Suggest an internal linking strategy:
- Which pages should link to which (and why)
- Anchor text recommendations
- Pages that are orphaned and need links
```

## 4. Page Speed & Core Web Vitals Checklist
```
Audit this page for Core Web Vitals improvements:
URL: [URL]
Current LCP: [X]s  CLS: [X]  FID/INP: [X]ms

Give me a prioritized list of fixes with estimated impact.
```
