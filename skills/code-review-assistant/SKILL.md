# Code Review Assistant

> Structured code reviews with severity ratings, security checks, and improvement patterns.

## Trigger

`/code-review-assistant`

## Instructions

When invoked with code (file path, diff, or pasted code), perform a structured review covering:

### 1. Security
- Input validation and sanitization
- Authentication/authorization gaps
- Secrets or credentials in code
- SQL injection, XSS, or other injection vectors
- Insecure dependencies or patterns

### 2. Correctness
- Logic errors and edge cases
- Error handling completeness
- Race conditions or concurrency issues
- Type safety concerns
- Off-by-one errors, null/undefined handling

### 3. Maintainability
- Naming clarity (variables, functions, classes)
- Function length and single responsibility
- Code duplication
- Comment quality (explain why, not what)
- Test coverage gaps

### 4. Performance
- Unnecessary allocations or copies
- N+1 queries or repeated computations
- Missing caching opportunities
- Algorithm complexity concerns

### Rules
- Rate each finding: `CRITICAL` / `WARNING` / `SUGGESTION` / `NITPICK`
- Be specific — reference exact line numbers or code snippets
- Explain *why* something is a problem, not just *that* it is
- If the code is solid, say so — do not invent issues
- Limit output to the most impactful findings (max 10)
- Suggest fixes, not just problems

## Output Format

```
## Code Review

**Files reviewed**: {list}
**Overall**: {summary in one sentence}

### Findings

#### [CRITICAL] {title}
**Line {X}**: {description}
```suggestion
{suggested fix}
```

#### [WARNING] {title}
**Line {X}**: {description}
```suggestion
{suggested fix}
```

### Summary
- Critical: {N} | Warnings: {N} | Suggestions: {N} | Nitpicks: {N}
- **Recommendation**: {approve / request changes / discuss}
```

## Examples

### Input

Any code file, git diff, or pasted code block.

### Output

A structured review following the format above, with severity ratings and specific suggested fixes for each finding.
