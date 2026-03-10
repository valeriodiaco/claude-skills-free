# SEO Meta Generator

> Generate optimized meta titles, descriptions, and Open Graph tags from any page content.

## Trigger

`/seo-meta-generator`

## Instructions

When invoked, analyze the provided page content (URL, HTML, or raw text) and generate:

1. **Meta Title** — max 60 characters, include primary keyword, compelling for CTR
2. **Meta Description** — max 155 characters, include call-to-action, summarize value proposition
3. **Open Graph Tags** — og:title, og:description, og:type
4. **Twitter Card** — twitter:title, twitter:description, twitter:card

### Rules

- Prioritize search intent alignment over keyword stuffing
- Use active voice and power words where natural
- Never exceed character limits
- If the content is multilingual, generate meta tags in the same language as the content
- Output as ready-to-paste HTML tags

## Output Format

```html
<!-- Primary Meta Tags -->
<title>{generated title}</title>
<meta name="description" content="{generated description}">

<!-- Open Graph -->
<meta property="og:type" content="{type}">
<meta property="og:title" content="{generated title}">
<meta property="og:description" content="{generated description}">

<!-- Twitter -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="{generated title}">
<meta name="twitter:description" content="{generated description}">
```

## Examples

### Input

"A blog post about how to set up a home espresso station for under $500, covering grinder selection, machine options, and workflow tips."

### Output

```html
<!-- Primary Meta Tags -->
<title>Home Espresso Station Under $500: Complete Setup Guide</title>
<meta name="description" content="Build a café-quality espresso station for under $500. Expert picks for grinders, machines, and workflow tips to pull perfect shots at home.">

<!-- Open Graph -->
<meta property="og:type" content="article">
<meta property="og:title" content="Home Espresso Station Under $500: Complete Setup Guide">
<meta property="og:description" content="Build a café-quality espresso station for under $500. Expert picks for grinders, machines, and workflow tips to pull perfect shots at home.">

<!-- Twitter -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Home Espresso Station Under $500: Complete Setup Guide">
<meta name="twitter:description" content="Build a café-quality espresso station for under $500. Expert picks for grinders, machines, and workflow tips to pull perfect shots at home.">
```
