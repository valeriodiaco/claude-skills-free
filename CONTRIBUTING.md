# Contributing to Claude Skills — Free Collection

Thank you for your interest in contributing. This guide covers how to submit a skill to the collection.

## Skill Requirements

Every submitted skill must:

1. **Be self-contained** — a single `SKILL.md` file that works without external dependencies
2. **Be tested** — you should have used it in real work before submitting
3. **Include clear documentation** — trigger command, description, expected behavior, examples
4. **Follow the structure** below

## Skill Structure

Create a directory under `skills/` with a descriptive kebab-case name:

```
skills/your-skill-name/
└── SKILL.md
```

### SKILL.md Format

```markdown
# Skill Name

> One-line description of what this skill does.

## Trigger

`/your-skill-name`

## Instructions

[Detailed instructions for Claude. Be specific about:
- What input to expect
- What output to produce
- What format to use
- What constraints to follow]

## Examples

### Input
[Example input]

### Output
[Example output]
```

## Submission Process

1. Fork this repository
2. Create a branch: `git checkout -b add-skill/your-skill-name`
3. Add your skill directory and `SKILL.md`
4. Update the table in `README.md` with your skill's entry
5. Open a Pull Request with:
   - A clear title: `Add skill: Your Skill Name`
   - A brief description of what the skill does and how you have used it

## Quality Standards

- Skills should solve a real, recurring problem
- Instructions must be clear enough that Claude produces consistent results
- Avoid overly niche use cases — skills should be useful to a broad audience
- No hardcoded API keys, tokens, or credentials

## License

By contributing, you agree that your contribution is licensed under the MIT License.
