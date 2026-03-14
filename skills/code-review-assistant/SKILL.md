---
name: code-review-assistant
description: Structured code review with severity ratings, security checks, performance analysis, and suggested fixes. Use when reviewing code files, diffs, or pull requests.
---

# Code Review Assistant

Perform a structured code review on the provided code.

Accept via `$ARGUMENTS`: file path, git diff, PR number, or pasted code.

## Review categories

### 1. Security (CRITICAL priority)
- Input validation and sanitization
- Authentication/authorization gaps
- Secrets, credentials, or API keys in code
- Injection vectors (SQL, XSS, command, path traversal)
- Insecure dependencies or deprecated crypto
- CORS, CSRF, or header misconfiguration

### 2. Correctness
- Logic errors and unhandled edge cases
- Error handling completeness (try/catch, error returns)
- Race conditions or concurrency issues
- Type safety (null/undefined, type coercion)
- Off-by-one errors, boundary conditions
- Resource leaks (unclosed connections, file handles)

### 3. Maintainability
- Naming clarity — do names reveal intent?
- Function length — flag >30 lines
- Single responsibility — does each function do one thing?
- Code duplication — exact or structural
- Dead code — unreachable branches, unused imports/variables
- Test coverage gaps — untested paths

### 4. Performance
- Unnecessary allocations or copies
- N+1 queries or repeated DB/API calls
- Missing caching opportunities
- Algorithm complexity — flag O(n^2) or worse on unbounded input
- Bundle size impact (frontend) — large imports
- Memory leaks — event listeners, subscriptions not cleaned up

## Severity levels

| Level | Meaning | Action |
|-------|---------|--------|
| `CRITICAL` | Security vulnerability or data loss risk | Must fix before merge |
| `WARNING` | Bug or significant code smell | Should fix |
| `SUGGESTION` | Improvement opportunity | Consider fixing |
| `NITPICK` | Style or minor preference | Optional |

## Output format

```
## Code Review

**Files**: {list of files reviewed}
**Lines**: {total lines reviewed}
**Verdict**: {APPROVE / REQUEST CHANGES / DISCUSS}

### Findings

#### [CRITICAL] {title}
**{file}:{line}** — {description explaining WHY this is a problem}
```suggestion
{concrete fix}
```

#### [WARNING] {title}
**{file}:{line}** — {description}
```suggestion
{concrete fix}
```

### Summary
| Critical | Warnings | Suggestions | Nitpicks |
|----------|----------|-------------|----------|
| {N} | {N} | {N} | {N} |

### What's Done Well
- {specific positive observation}
```

## Rules

- Max 10 findings — prioritize by severity
- Every finding must include a suggested fix, not just the problem
- Explain WHY something is a problem, not just THAT it is
- Reference exact file and line numbers
- If the code is solid, say so — do not invent issues
- Adapt to the language/framework conventions of the code being reviewed
