---
name: standup-summarizer
description: Summarize daily standup meetings into structured notes. Use when user provides standup transcripts, chat logs, or meeting notes and asks to "summarize standup", "generate standup report", "standup summary", "站会总结", "站会纪要", or wants to extract progress/blockers/plans from team updates. Also triggers on "what did the team do", "team status update", or "sprint progress".
---

# Standup Summarizer

Summarize daily standup meetings into clear, actionable reports.

## Workflow

1. Accept input in any format: raw transcript, chat messages, bullet points, or voice-to-text
2. Identify each team member's update
3. Extract three categories per person:
   - ✅ **Done** — What they completed since last standup
   - 🚧 **In Progress** — What they're currently working on
   - 🚫 **Blockers** — What's blocking them (if any)
   - 📋 **Next** — What they plan to do next
4. Generate a structured summary with optional action items

## Output Format

Use this template for the summary:

```markdown
# Daily Standup Summary — [Date]

## Team Updates

### [Person Name]
- ✅ Done: [completed items]
- 🚧 In Progress: [current work]
- 🚫 Blockers: [blocking issues, or "None"]
- 📋 Next: [planned items]

(repeat for each person)

## Action Items
- [ ] [action] — Owner: [name], Due: [date if mentioned]

## Blockers Summary
| Person | Blocker | Severity |
|--------|---------|----------|
| [name] | [issue] | High/Medium/Low |

## Sprint Health
- **Team velocity**: [on track / at risk / behind]
- **Key risks**: [list if any]
```

## Input Handling

- **Chat logs**: Parse message-by-message, group by sender
- **Transcripts**: Identify speakers by name patterns (e.g., "John:", "[John]", "John said")
- **Bullet points**: Map items to the correct person and category
- **Mixed languages**: Support both English and Chinese standup formats

## Guidelines

- Keep summaries concise — no fluff
- Preserve technical details (ticket numbers, PR links, etc.)
- Flag urgent blockers prominently
- If someone didn't provide all three categories, note what's missing
- When input is ambiguous, make reasonable inferences and mark with "[inferred]"
- For recurring blockers across standups, note the pattern

## Advanced Features

### Trend Analysis
When provided with multiple days of standup data, identify:
- Tasks that have been "in progress" for too long (>3 days)
- Recurring blockers that need escalation
- Team members who may need help (many blockers, slow progress)

### Custom Formats
If the user specifies a preferred format (Jira, Notion, Slack, Feishu doc), adapt the output accordingly. Read `references/output-formats.md` for platform-specific templates.
