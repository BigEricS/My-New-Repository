# llms.txt Generator

> **Note:** `llms.txt` is useful for AI developer tools and coding assistants
> (like Claude Code reading docs), but the AgriciDaniel/claude-seo skill and
> Google both confirm it is NOT a citation lever for consumer AI search
> (ChatGPT, Perplexity, Google AI Overviews). Don't pitch it as a GEO tactic.
> Real GEO signals: passage citability, question-based headings, entity presence.

`llms.txt` is a file at the root of your website that helps AI coding assistants
understand your site's structure and documentation.

---

## Prompt: Generate llms.txt for Any Website

```
Generate an llms.txt file for my website.

Business name: [NAME]
Website: [URL]
What we do: [1-2 sentence description]
Primary services/products: [LIST]
Target audience: [WHO YOU SERVE]
Most important pages (with URLs):
- Homepage: [URL]
- Services: [URL]
- About: [URL]
- Blog/Resources: [URL]
- Contact: [URL]

The llms.txt should:
1. Open with a clear, factual description of the business (2-3 sentences)
2. List the most important pages with a one-line description of each
3. Include key facts AI should know (founding year, location, specialties)
4. Note any pages to exclude from AI answers (login, checkout, etc.)
5. Follow the emerging llms.txt standard format
```

---

## Standard llms.txt Format

```
# [Business Name]

> [One sentence describing what the business does and who it serves.]

[2-3 sentences of factual context: location, founding, specialties, 
credentials, or unique positioning. This is what AI will cite.]

## Key Pages

- [Page Title]: [URL]
  [One sentence describing what this page covers and why it matters]

- [Page Title]: [URL]
  [One sentence describing what this page covers and why it matters]

## About

[Business name] was founded in [YEAR] and specializes in [SERVICES].
[Any credentials, certifications, awards, or trust signals.]

## Contact

[City, State] | [Phone] | [Email]

## Exclude

The following pages should not be used for AI-generated answers:
- /login
- /checkout
- /account
```

---

## Where to Place It

Upload to: `https://yourdomain.com/llms.txt`

Verify it's live: `curl https://yourdomain.com/llms.txt`

---

## Prompt: Generate llms.txt From Audit Results

```
Based on the SEO audit report at SEO-Project/Reports/audits/[filename].md,
generate an optimized llms.txt file for [URL].

Use the E-E-A-T signals, schema data, and content structure from the audit
to write factual, citation-ready descriptions for each key page.

Output the complete llms.txt file ready to upload to the site root.
```
