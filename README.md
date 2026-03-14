# Claude Skills — Free Collection

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/valeriodiaco/claude-skills-free?style=social)](https://github.com/valeriodiaco/claude-skills-free/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/valeriodiaco/claude-skills-free?style=social)](https://github.com/valeriodiaco/claude-skills-free/network/members)

A curated collection of **free, production-ready skills** for [Claude Code](https://docs.anthropic.com/en/docs/claude-code), Anthropic's official CLI agent.

Each skill is tested, documented, and ready to drop into your workflow. No configuration required — just install and use.

---

## Available Skills

| Skill | Category | Description | Status |
|-------|----------|-------------|--------|
| [SEO Meta Generator](skills/seo-meta-generator/) | SEO | Generate optimized meta titles, descriptions, OG and Twitter Card tags | Ready |
| [Content Quality Checker](skills/content-quality-checker/) | Content | Analyze readability, E-E-A-T signals, SEO alignment, AI citation readiness | Ready |
| [Code Review Assistant](skills/code-review-assistant/) | Development | Structured reviews with severity ratings, security checks, suggested fixes | Ready |
| [Git Commit Pro](skills/git-commit-pro/) | Development | Generate Conventional Commits from staged changes with scope detection | Ready |
| [Meeting Notes](skills/meeting-notes/) | Productivity | Transform transcripts into structured summaries with action items and owners | Ready |

## Installation

### Quick Install (single skill)

Copy the skill file directly into your Claude skills directory:

```bash
# Global installation (available in all projects)
cp skills/seo-meta-generator/SKILL.md ~/.claude/skills/

# Project-level installation (available only in this project)
cp skills/seo-meta-generator/SKILL.md .claude/skills/
```

### Install All Skills

```bash
# Global
cp skills/*/SKILL.md ~/.claude/skills/

# Or project-level
mkdir -p .claude/skills && cp skills/*/SKILL.md .claude/skills/
```

### Using with Claude Code

Once installed, skills are automatically available. Invoke them by name:

```
> /seo-meta-generator
> /content-quality-checker
> /code-review-assistant
> /git-commit-pro
> /meeting-notes
```

Or reference them naturally in conversation — Claude will pick up the skill context automatically.

## Skill Categories

### SEO / GEO
Skills for search engine optimization, generative engine optimization, and technical SEO audits. Built from real-world production use across multilingual sites.

### Content
Writing analysis, quality scoring, readability checks, and editorial workflow tools. Designed for teams producing content at scale.

### Development
Code review, refactoring guidance, architecture analysis, and developer productivity. Battle-tested on production codebases.

### Productivity
Task management, documentation generation, meeting summaries, and workflow automation skills.

### More coming
Follow the repo for updates — new skills added regularly.

## Writing Your Own Skills

A Claude Skill is a Markdown file that gives Claude Code specialized instructions for a specific task. At minimum, a skill needs:

1. A clear **trigger** (slash command or natural language pattern)
2. **Instructions** that define behavior, output format, and constraints
3. **Examples** of expected input/output

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full guide on submitting skills to this collection.

## Premium Skills

Looking for advanced, specialized skills? The **Claude Skills Store** offers professionally built skills for complex workflows:

- Multi-step SEO audit pipelines
- Full content production systems
- Enterprise code review frameworks
- Custom skill development

[Browse the Claude Skills Store →](https://project-eva.ai/skills)

## Project Structure

```
claude-skills-free/
├── skills/
│   ├── seo-meta-generator/       — SEO meta tags generation
│   ├── content-quality-checker/   — Content quality + E-E-A-T audit
│   ├── code-review-assistant/     — Structured code review
│   ├── git-commit-pro/            — Conventional Commits from diffs
│   └── meeting-notes/             — Meeting transcript → action items
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.

You are free to use these skills in personal and commercial projects.

---

Built by [Valerio Diaco](https://github.com/valeriodiaco) · Part of the [Project EVA](https://project-eva.ai) ecosystem
