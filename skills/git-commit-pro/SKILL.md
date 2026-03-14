---
name: git-commit-pro
description: Generate structured, meaningful git commit messages from staged changes. Follows Conventional Commits, analyzes diffs, and suggests scope. Use when committing code or reviewing commit history.
---

# Git Commit Pro

Generate a professional commit message from the current staged changes.

## Process

### Step 1 — Gather context
Run these commands to understand the changes:
```bash
git diff --cached --stat
git diff --cached
git log --oneline -5
```

### Step 2 — Analyze changes

Classify the change:
| Type | When |
|------|------|
| `feat` | New feature or capability |
| `fix` | Bug fix |
| `refactor` | Code restructuring without behavior change |
| `docs` | Documentation only |
| `style` | Formatting, whitespace, semicolons (no logic change) |
| `test` | Adding or updating tests |
| `chore` | Build, CI, dependencies, tooling |
| `perf` | Performance improvement |
| `revert` | Reverting a previous commit |

Determine scope from the primary directory or module affected.

### Step 3 — Generate commit message

Format: **Conventional Commits**

```
<type>(<scope>): <subject>

<body>

<footer>
```

#### Subject line rules
- Max 72 characters
- Imperative mood ("add" not "added", "fix" not "fixes")
- No period at end
- Lowercase after type/scope prefix
- Focus on WHAT and WHY, not HOW

#### Body rules (if changes are non-trivial)
- Wrap at 72 characters
- Explain WHY the change was made, not what changed (the diff shows what)
- Separate from subject with blank line
- Use bullet points for multiple changes

#### Footer rules
- `BREAKING CHANGE:` if the change breaks backward compatibility
- `Closes #N` or `Fixes #N` if it resolves an issue
- Never add Co-Authored-By lines

### Step 4 — Validate

Before presenting:
- [ ] Subject under 72 chars?
- [ ] Type is correct for the change?
- [ ] Scope matches the primary area affected?
- [ ] Imperative mood used?
- [ ] No sensitive data in the message?
- [ ] Recent commit style followed? (match the repo's convention)

## Output format

Present the commit message ready to use:

```
feat(auth): add OAuth2 PKCE flow for mobile clients

Replace implicit grant with PKCE authorization code flow
to comply with OAuth 2.1 draft specification:
- Add code verifier/challenge generation
- Update token exchange endpoint
- Add PKCE validation middleware

Closes #142
```

Then show:
```
Characters: {N}/72 | Type: {type} | Scope: {scope}
Alternative subjects:
1. {alternative 1}
2. {alternative 2}
```

## Multi-commit detection

If the staged changes cover multiple unrelated concerns, suggest splitting:

```
WARNING: These changes touch 2+ unrelated areas.
Consider splitting into separate commits:
1. `fix(api): handle null response from payment gateway` — files: src/api/payment.ts
2. `test(api): add edge case tests for payment flow` — files: tests/payment.test.ts
```

## Arguments

- No arguments: analyze current `git diff --cached`
- `$ARGUMENTS` as text: use as additional context for the commit message
