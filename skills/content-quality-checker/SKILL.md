# Content Quality Checker

> Analyze text for readability, structure, and SEO alignment with actionable suggestions.

## Trigger

`/content-quality-checker`

## Instructions

When invoked with a piece of content (article, blog post, landing page copy, documentation), perform a comprehensive quality analysis covering:

### 1. Readability Score
- Estimate Flesch-Kincaid grade level
- Flag sentences over 30 words
- Flag paragraphs over 5 sentences
- Identify passive voice usage (percentage)

### 2. Structure Analysis
- Heading hierarchy (H1 > H2 > H3 — no skipped levels)
- Paragraph length distribution
- Use of lists, bold, and other scannable elements
- Intro hook quality (does the first paragraph earn the second?)

### 3. SEO Alignment
- Keyword presence in title, H1, first paragraph, and subheadings
- Internal/external link suggestions
- Content length assessment relative to topic depth
- Missing semantic coverage (related topics not addressed)

### 4. Actionable Suggestions
- Provide exactly 3-5 specific, prioritized improvements
- Each suggestion must reference a specific line or section
- Rate each suggestion: high / medium / low impact

### Rules
- Be direct and specific — no vague praise
- If the content is good, say so briefly and focus on what would make it excellent
- Never rewrite the content — only suggest improvements
- Output in a structured, scannable format

## Output Format

```
## Quality Report

**Readability**: Grade {X} | Passive voice: {X}% | Avg sentence length: {X} words

**Structure**: {pass/needs work} — {one-line summary}

**SEO Alignment**: {strong/moderate/weak} — {one-line summary}

## Top Suggestions

1. **[HIGH]** {specific suggestion with reference to section}
2. **[HIGH]** {specific suggestion with reference to section}
3. **[MED]** {specific suggestion with reference to section}
```

## Examples

### Input

Any article, blog post, or documentation page — either as raw text or a file path.

### Output

A structured quality report following the format above, with specific line references and prioritized improvements.
