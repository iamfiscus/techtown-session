---
aliases: [N8N, n8n, workflow automation tool, autopilot]
tags: [tool, context-engineering, automation]
---

# N8N — "The Autopilot"

> **Solves:** [[context-hydration]] — automatically assembling the right context.

## What It Is

N8N is a **visual workflow automation platform** that connects triggers to actions. It watches for events and automatically gathers data, processes it with AI, and takes action — without you manually copying and pasting.

## Kitchen Table Analogy

You hire a virtual assistant who watches for triggers and takes action: "When X happens, gather Y, and do Z." That's a workflow. That's N8N.

## Key Features

| Feature | Detail |
|---------|--------|
| **Visual drag-and-drop** | Build workflows without code |
| **400+ integrations** | Connects to virtually any tool |
| **Built-in AI agent builder** | Create [[ai-agents]] inside workflows |
| **Self-hostable** | Keep your data on your own servers |
| **Open source** | Free to use, community-driven |

## Founder Examples

### Content Autopilot
```
Article link → Spreadsheet → AI Summary → Social Media → Track Engagement
```
One input triggers an entire content distribution pipeline.

### Lead Hydration
```
New lead signs up
  → Grab LinkedIn profile + company info + past interactions
  → Hydrate AI agent with all context
  → Draft personalized welcome email
```
The AI gets pre-loaded with [[dynamic-context]] about the lead before it writes anything.

### Support Triage
```
New support ticket arrives
  → Pull customer history from CRM
  → Check knowledge base for similar issues
  → AI drafts response with full context
  → Route to right team member
```

## Context Engineering Connection

N8N is the **hydration engine** for [[context-hydration]]:
- It **automatically assembles context** from multiple sources
- Delivers it to AI without manual work
- Ensures AI always has fresh [[dynamic-context]]
- Replaces the manual copy-paste workflow

Instead of you:
1. Opening Slack → copying relevant messages
2. Opening CRM → copying customer info
3. Opening docs → copying product details
4. Pasting all 3 into AI
5. Writing your prompt

N8N does steps 1-4 automatically.

## How N8N Relates to [[mcp]]

| | [[mcp]] | N8N |
|---|---|---|
| **Direction** | AI **pulls** data on demand | Data is **pushed** to AI |
| **Trigger** | User asks AI to look something up | An event triggers the workflow |
| **Timing** | Real-time, interactive | Event-driven, automated |
| **Best for** | Interactive conversations | Background automation |

They're complementary: MCP for interactive context, N8N for automated context.

## When to Use N8N

Use the [[decision-framework]]:
- "I need context to flow automatically" → **N8N**
- You're doing the same manual data gathering repeatedly
- You want [[workflow-automation]] that includes AI
- You need [[context-hydration]] to happen without you

---

**See also:** [[context-hydration]], [[workflow-automation]], [[mcp]], [[ai-agents]], [[dynamic-context]]

#tool #automation
