---
aliases: [write, save, persist, store, externalize]
tags: [operation, context-engineering]
---

# Write Operation

> **Save context outside the [[context-window]].**
> Analogy: Take notes so you don't forget.

## Definition

The Write operation is about **persisting important information externally** so it survives beyond a single AI conversation. It's how you combat [[context-rot]] and build a [[second-brain]].

## Why It's Necessary

AI conversations are **ephemeral by default**. When you close a chat:
- Decisions made are gone
- Lessons learned are lost
- Context established vanishes
- You start from zero next time

Writing solves this by creating a **persistent context store** that any future conversation can draw from.

## What to Write

- Key decisions and their rationale
- Lessons learned from experiments
- Brand voice and style guidelines ([[static-context]])
- Meeting notes and summaries
- Project specifications
- User research insights
- Anything you'd want AI to "remember" later

## How to Write

### Manual Writing
- Take notes in [[obsidian-vector-brain|Obsidian]] after important AI conversations
- Document decisions in markdown files
- Create specs and briefs before projects

### Automated Writing
- Use AI to summarize conversations ([[compress-operation]]) and save the summary
- [[n8n]] can auto-save outputs to files or databases
- MCP-connected tools can write to docs, databases, or repos

## Tools for Writing

| Tool | How It Helps |
|------|-------------|
| [[obsidian-vector-brain]] | Primary Write tool — persistent, searchable, linked notes |
| GitHub / Gist | Version-controlled storage AI can read |
| Google Docs | Collaborative static context store |
| [[notebooklm]] | Saved conversations provide episodic Write |

## Relationship to Other Operations

| Combined With | Result |
|--------------|--------|
| [[select-operation]] | Write → then Select later when needed |
| [[compress-operation]] | Compress first → then Write the summary |
| [[isolate-operation]] | Write key context before starting fresh chat |

## The Write + Select Loop

The most powerful pattern: **Write now, Select later.**

1. Have an important conversation → **Write** key decisions to Obsidian
2. Start a new project weeks later → **Select** relevant past decisions
3. AI has [[episodic-context]] without [[context-rot]]

This is the foundation of the [[second-brain]] approach.

## Founder Example

After a strategy session with AI:
```
Decision: Pricing will be freemium with Pro at $29/mo
Rationale: Based on competitor analysis showing...
Date: 2026-02-17
Context: Full analysis in [[pricing-strategy]]
```

Save this to Obsidian. Six months later when revisiting pricing, AI can read it.

---

**See also:** [[obsidian-vector-brain]], [[second-brain]], [[episodic-context]], [[select-operation]]

#operation
