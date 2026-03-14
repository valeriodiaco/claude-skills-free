---
name: seo-meta-generator
description: Generate optimized meta titles, descriptions, Open Graph and Twitter Card tags from any page content. Use when creating or improving meta tags for web pages, blog posts, or landing pages.
---

# SEO Meta Generator

Analyze the provided content and generate complete, optimized meta tags.

## What to analyze

Accept any of: URL, HTML, raw text, file path, or content description via `$ARGUMENTS`.

## Generation rules

### Meta Title
- Max 60 characters (hard limit — truncate if needed)
- Include primary keyword naturally, front-loaded when possible
- Use power words that drive CTR: "Guide", "How to", numbers, current year
- Match search intent (informational, transactional, navigational)

### Meta Description
- Max 155 characters (hard limit)
- Include a clear value proposition in the first 80 characters (mobile truncation)
- End with implicit or explicit call-to-action
- Include primary keyword once, naturally
- Use active voice

### Open Graph Tags
- `og:title` — can be slightly longer/different than meta title (max 95 chars)
- `og:description` — can expand on meta description (max 200 chars)
- `og:type` — article, website, product, etc. based on content

### Twitter Card
- `twitter:card` — use `summary_large_image` unless no image available
- `twitter:title` — max 70 characters
- `twitter:description` — max 200 characters

## Additional checks

After generating tags:
1. **Character count** — show count next to each tag
2. **Keyword check** — confirm primary keyword appears in title + description
3. **Uniqueness** — flag if title/description are too similar to each other
4. **Language** — generate in the same language as the source content

## Output format

```html
<!-- Primary Meta Tags -->
<title>{title} ({char count})</title>
<meta name="description" content="{description} ({char count})">

<!-- Open Graph / Facebook -->
<meta property="og:type" content="{type}">
<meta property="og:title" content="{og title}">
<meta property="og:description" content="{og description}">

<!-- Twitter -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="{twitter title}">
<meta name="twitter:description" content="{twitter description}">
```

Then add:
```
## Analysis
- Primary keyword: {detected keyword}
- Search intent: {informational/transactional/navigational}
- Title length: {N}/60 chars
- Description length: {N}/155 chars
- Suggestions for improvement: {if any}
```

## Example

**Input**: "A blog post about how to set up a home espresso station for under $500"

**Output**:
```html
<title>Home Espresso Station Under $500: Complete Setup Guide (52 chars)</title>
<meta name="description" content="Build a cafe-quality espresso setup for under $500. Expert grinder picks, machine comparisons, and pro workflow tips for perfect shots at home. (143 chars)">
<meta property="og:type" content="article">
<meta property="og:title" content="How to Build a Home Espresso Station for Under $500">
<meta property="og:description" content="Everything you need to pull cafe-quality espresso at home without breaking the bank. Grinder picks, machine options, and daily workflow tips.">
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Home Espresso Station Under $500: Complete Setup Guide">
<meta name="twitter:description" content="Build a cafe-quality espresso setup for under $500. Expert grinder picks, machine comparisons, and workflow tips.">
```
