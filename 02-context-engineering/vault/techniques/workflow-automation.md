---
aliases: [automation, workflows, triggers, automated workflows]
tags: [technique, context-engineering, automation]
---

# Workflow Automation

> "When X happens, gather Y, and do Z." — The pattern behind every automation.

## What It Is

Workflow automation is the practice of **connecting triggers to actions** so that tasks happen automatically without manual intervention. In the context of [[context-engineering]], it's how you automate [[context-hydration]].

## The Pattern

Every workflow follows the same structure:

```
TRIGGER → GATHER CONTEXT → PROCESS → ACTION
```

### Example: Lead Nurture
```
New lead signs up (trigger)
  → Grab LinkedIn profile + company info (gather)
  → AI drafts personalized email (process)
  → Send email + log to CRM (action)
```

### Example: Content Distribution
```
New article published (trigger)
  → AI summarizes article (gather/process)
  → Post to Twitter, LinkedIn, newsletter (action)
  → Track engagement metrics (action)
```

## Why It's Context Engineering

Without automation, the context assembly process is manual:
1. Open Slack, copy relevant info
2. Open CRM, copy customer details
3. Open docs, copy product info
4. Paste all into AI
5. Write prompt

With automation, steps 1-4 happen automatically. The AI gets **pre-hydrated** with the right context every time.

This is [[context-hydration]] at scale.

## Tools

| Tool | Role |
|------|------|
| [[n8n]] | Primary workflow automation tool (400+ integrations) |
| [[mcp]] | Enables AI to interact with tools within workflows |
| Zapier | Alternative (simpler but less flexible) |
| Make.com | Alternative (visual, good for non-technical users) |

## Connection to Operations

| Operation | Automation Role |
|-----------|----------------|
| [[select-operation]] | Automation gathers the right context per trigger |
| [[context-hydration]] | Automation IS automated hydration |
| [[write-operation]] | Automation can save outputs to external stores |
| [[compress-operation]] | AI summarization step in workflows |

## For Founders

Start simple:
1. Identify a **manual process** you repeat weekly
2. Map the **trigger** → **context** → **action** pattern
3. Build it in [[n8n]] (visual, no-code)
4. Let it run and iterate

---

**See also:** [[n8n]], [[context-hydration]], [[ai-agents]], [[mcp]]

#technique #automation
