---
name: content-quality-checker
description: Analyze any text for readability, structure, E-E-A-T signals, and SEO alignment. Returns a quality score with prioritized suggestions. Use when reviewing articles, blog posts, landing pages, or documentation.
---

# Content Quality Checker

Perform a comprehensive quality audit on the provided content.

Accept via `$ARGUMENTS`: raw text, file path, or URL.

## 1. Readability Analysis

- **Flesch-Kincaid grade level** (estimate from sentence/word length)
- **Average sentence length** in words
- **Long sentences** (>30 words) — list them with line reference
- **Passive voice percentage** — flag if >15%
- **Jargon density** — flag unexplained technical terms

Score: 1-10

## 2. Structure Analysis

- **Heading hierarchy** — H1 > H2 > H3, no skipped levels
- **First paragraph** — does it earn the second? (hook quality 1-5)
- **Paragraph length** — flag any >5 sentences
- **Scannable elements** — lists, bold, subheadings per 500 words
- **Content flow** — logical progression, clear transitions
- **Conclusion** — present and actionable?

Score: 1-10

## 3. E-E-A-T Signals

- **Experience** — first-person examples, specific data, real scenarios
- **Expertise** — technical depth appropriate to topic
- **Authoritativeness** — citations, references, credentials mentioned
- **Trustworthiness** — balanced view, limitations acknowledged, sources cited

Score: 1-10

## 4. SEO Alignment

- **Primary keyword** — detected, present in title/H1/first paragraph/subheadings?
- **Semantic coverage** — related topics addressed vs missing
- **Content length** — appropriate for topic depth?
- **Internal/external links** — count and quality
- **Featured snippet potential** — has definition/list/table that could be featured?

Score: 1-10

## 5. AI Citation Readiness

- **Passage citability** — are there self-contained, quotable passages?
- **Factual density** — specific data points AI can cite
- **Structure for extraction** — clear Q&A, definitions, lists
- **Unique insight** — content that adds value beyond what AI already knows

Score: 1-10

## Output format

```
## Content Quality Report

**Overall Score: {X}/50** ({excellent/good/needs work/poor})

| Category | Score | Status |
|----------|-------|--------|
| Readability | {X}/10 | {emoji} |
| Structure | {X}/10 | {emoji} |
| E-E-A-T | {X}/10 | {emoji} |
| SEO Alignment | {X}/10 | {emoji} |
| AI Citation Ready | {X}/10 | {emoji} |

### Key Metrics
- Grade level: {X} | Passive voice: {X}% | Avg sentence: {X} words
- Word count: {X} | Paragraphs: {X} | Headings: {X}
- Primary keyword: "{keyword}" | Density: {X}%

### Top 5 Improvements (prioritized)

1. **[HIGH]** {specific suggestion} — {section/line reference}
2. **[HIGH]** {specific suggestion} — {section/line reference}
3. **[MED]** {specific suggestion} — {section/line reference}
4. **[MED]** {specific suggestion} — {section/line reference}
5. **[LOW]** {specific suggestion} — {section/line reference}

### What's Working Well
- {specific strength}
- {specific strength}
```

## Rules

- Be direct — no filler praise
- Every suggestion must reference a specific section or line
- Never rewrite the content — only suggest improvements
- If the content is excellent, say so briefly and focus on what would make it outstanding
- Adapt language to match the content's language
