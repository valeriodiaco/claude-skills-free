---
name: meeting-notes
description: Transform meeting transcripts, voice notes, or raw notes into structured summaries with action items, decisions, and follow-ups. Use after meetings, calls, or brainstorming sessions.
---

# Meeting Notes

Transform raw meeting input into a structured, actionable summary.

## Input

Accept via `$ARGUMENTS`: transcript text, audio transcription, file path, or rough notes.

## Processing rules

### 1. Identify participants
Extract names from the transcript. If names aren't clear, use Speaker 1, Speaker 2, etc.

### 2. Extract key elements

**Decisions made** — concrete choices that were finalized
- What was decided
- Who decided it
- Any conditions or caveats

**Action items** — tasks assigned to specific people
- What needs to be done (specific, not vague)
- Who is responsible (one person, not "the team")
- Deadline if mentioned (convert relative dates to absolute: "next Friday" -> specific date)

**Discussion points** — topics covered but not resolved
- What was discussed
- Different positions expressed
- Why it wasn't resolved

**Key insights** — important information shared
- Data points, metrics, numbers mentioned
- New information that changes context
- Risks or blockers identified

### 3. Summarize

Write a 2-3 sentence executive summary that captures:
- What was the meeting about?
- What was the most important outcome?
- What happens next?

## Output format

```
## Meeting Summary — {topic/title}
**Date**: {date if available}
**Participants**: {names}
**Duration**: {if available}

### Executive Summary
{2-3 sentences}

### Decisions
1. {decision} — decided by {who}
2. {decision} — decided by {who}

### Action Items
| # | Task | Owner | Deadline | Status |
|---|------|-------|----------|--------|
| 1 | {specific task} | {name} | {date} | Pending |
| 2 | {specific task} | {name} | {date} | Pending |

### Discussion Points (unresolved)
- **{topic}**: {summary of positions}. Next step: {what needs to happen}

### Key Information
- {data point or insight}
- {risk or blocker identified}

### Follow-up
- Next meeting: {if scheduled}
- Items deferred: {if any}
```

## Rules

- Action items must be SPECIFIC ("Send pricing proposal to Acme Corp" not "Follow up on pricing")
- Each action item needs ONE owner (not "the team")
- Convert all relative dates to absolute dates using today's date
- If the transcript is unclear or contradictory, flag it rather than guessing
- Keep the summary under 1 page — brevity is the point
- Adapt language to match the transcript's language
- Do NOT add information not present in the source material
