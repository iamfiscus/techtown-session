---
aliases: [tool, tool output, connected systems, external tools]
tags: [context-type, context-engineering]
---

# Tool Context

> Analogy: **Calling someone to ask a question** — getting information from an external source in real-time.

## Definition

Tool context is **information retrieved from connected systems** — the outputs AI gets when it reaches out to external tools, APIs, databases, or services. It transforms AI from "answering with what it knows" to "answering with what it can look up."

## Examples

- Slack message search results
- Database query responses
- API responses from external services
- File system reads
- Calendar lookups
- Web search results
- CRM record lookups
- Code repository searches

## Why It's Transformative

Without tool context, AI is limited to:
1. Its training data (potentially outdated)
2. What you manually paste in
3. Its own reasoning

With tool context, AI can:
1. Look up real answers in real-time
2. Access your actual data, not hypotheticals
3. Take actions (not just suggest them)
4. Stay current with live information

## How It Works

In the [[message-queue]], tool outputs appear as **TOOL** messages:

```
USER: "What's our top support ticket this week?"
TOOL: [Zendesk API] "Password reset failures — 47 tickets"
ASSISTANT: "Your top issue is password reset failures with 47 tickets..."
```

## The Key Technology: [[mcp]]

**Model Context Protocol** is what makes tool context practical. Before MCP, every AI-tool connection was custom-built. MCP provides a universal standard — like [[usb-c-analogy|USB-C for AI]].

## Tools That Provide Tool Context

| Tool | What It Connects |
|------|-----------------|
| [[mcp]] | Slack, calendar, databases, files, APIs — anything |
| [[n8n]] | 400+ integrations via workflow automation |
| [[rag]] | Document retrieval from vector databases |

## Connection to Dynamic Context

Tool context and [[dynamic-context]] are closely related:
- Dynamic context is the **type** of information (live, changing data)
- Tool context is the **mechanism** for getting it (AI reaching out to systems)

MCP enables AI to access dynamic context through tool context.

## Connection to Operations

- Tool context is the result of [[select-operation]] — AI selects which tool to query
- [[context-hydration]] can use tool context to auto-fill the [[context-window]]
- [[n8n]] automates tool context gathering into [[workflow-automation|workflows]]

## Compared to Other Types

| Type | Changes? | Example |
|------|----------|---------|
| [[static-context]] | Rarely | Brand guidelines |
| [[dynamic-context]] | Constantly | CRM data, metrics |
| [[episodic-context]] | Accumulates | Conversation history |
| **Tool** | On-demand | API responses |

---

**See also:** [[mcp]], [[dynamic-context]], [[message-queue]], [[ai-agents]]

#context-type
