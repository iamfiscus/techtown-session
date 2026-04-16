---
aliases: [MCP, Model Context Protocol, universal adapter]
tags: [tool, context-engineering, protocol, standard]
---

# MCP — "The Universal Adapter"

> **Solves:** [[dynamic-context]] — connecting AI to live data and tools.

## What It Is

Model Context Protocol (MCP) is an **open standard** that connects AI models to external tools and data sources. It's a universal API layer that lets any AI talk to any tool through one protocol.

## Kitchen Table Analogy

See: [[usb-c-analogy]]

Remember when every phone had a different charger? USB-C fixed that. MCP is **USB-C for AI** — one standard plug that connects AI to any tool.

## The Diagram

```
[Slack]  [Calendar]  [Database]  [Files]  [APIs]
   \         |          |          |        /
    \        |          |          |       /
     +---------+  MCP  +---------+
                  |
    +-------------+-------------+
    |             |             |
 [Claude]    [ChatGPT]    [Cursor]
```

"Instead of copy-pasting data INTO AI, MCP lets AI reach OUT and grab it."

## Key Stats

| Metric | Value |
|--------|-------|
| Monthly downloads | **97M** |
| Major platforms adopted | ChatGPT, Claude, Gemini, Cursor, VS Code, 6+ more |
| Governance | Donated to **Linux Foundation** — industry standard |
| MCP Apps (Jan 2026) | Interactive dashboards & forms inside AI chats |

## Why It Matters

Before MCP, connecting AI to a tool required:
- Custom API integration per tool per AI
- N tools x M AI platforms = N*M integrations

With MCP:
- Build one MCP server per tool
- Every AI platform can connect to it
- N tools + M platforms = N+M integrations

This is why it's an industry standard, not a fad.

## What MCP Enables

| Capability | Example |
|-----------|---------|
| **Read from tools** | Search Slack messages, query databases, read files |
| **Write to tools** | Send messages, create records, update files |
| **[[tool-context]]** | AI gets real-time data from your actual systems |
| **[[ai-agents]]** | Agents can autonomously use tools to complete tasks |

## Context Engineering Connection

MCP solves the **[[dynamic-context]]** problem:
- [[static-context]] can be uploaded manually
- [[episodic-context]] can be stored in notes
- But **live, changing data** needs a real-time connection
- MCP provides that connection

It also enables [[tool-context]] — AI goes from "answering with what it knows" to "answering with what it can look up."

## When to Use MCP

Use the [[decision-framework]]:
- "I need AI to access my live tools & data" → **MCP**
- You're tired of copy-pasting data into AI
- You want AI to take actions in your tools (not just suggest them)
- You're building [[ai-agents]] that need tool access

## For Founders

You don't need to build MCP servers yourself. Popular tools already have MCP servers:
- Slack, Google Drive, GitHub, databases, file systems
- More being added daily as the ecosystem grows

---

**See also:** [[dynamic-context]], [[tool-context]], [[usb-c-analogy]], [[ai-agents]], [[n8n]]

#tool #protocol
