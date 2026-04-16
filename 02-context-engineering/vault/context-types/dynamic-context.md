---
aliases: [dynamic, live data, real-time context]
tags: [context-type, context-engineering]
---

# Dynamic Context

> Analogy: **Today's calendar** — it's different every day.

## Definition

Dynamic context is **live, changing data** that reflects the current state of your business, tools, or environment. It's the context that makes AI responses timely and relevant rather than generic.

## Examples

- CRM data (current pipeline, recent interactions)
- Current metrics and KPIs
- Inventory levels
- Calendar availability
- Live pricing and exchange rates
- Recent Slack conversations
- Current support tickets
- Active user sessions

## Why It's Powerful

Static context tells AI what your brand voice IS. Dynamic context tells AI what's happening RIGHT NOW.

**Without dynamic context:** "Here's a generic welcome email template."
**With dynamic context:** "Hi Sarah, I see you just signed up after viewing our pricing page 3 times. Here's a personalized welcome with the Pro plan highlighted since that's what you viewed most."

## The Challenge

Dynamic context is harder to provide because:
1. It changes constantly — manual copy-pasting becomes stale immediately
2. It lives in different systems — CRM, calendar, database, Slack
3. It requires **connections** — AI can't access it without tools

This is exactly why [[mcp]] and [[n8n]] exist.

## Tools That Solve Dynamic Context

| Tool | How |
|------|-----|
| [[mcp]] | Connects AI directly to live systems (Slack, calendar, database) |
| [[n8n]] | Automatically gathers dynamic data and delivers it to AI |
| [[rag]] | Retrieves the latest relevant documents on-demand |

## Connection to Operations

- Dynamic context is the primary use case for [[tool-context]]
- [[mcp]] enables AI to **pull** dynamic context on demand
- [[n8n]] enables dynamic context to be **pushed** to AI automatically
- [[context-hydration]] with dynamic data produces the most relevant results

## Compared to Other Types

| Type | Changes? | Example |
|------|----------|---------|
| [[static-context]] | Rarely | Brand guidelines |
| **Dynamic** | Constantly | CRM data, metrics |
| [[episodic-context]] | Accumulates | Conversation history |
| [[tool-context]] | On-demand | API responses |

---

**See also:** [[mcp]], [[n8n]], [[tool-context]], [[context-hydration]]

#context-type
