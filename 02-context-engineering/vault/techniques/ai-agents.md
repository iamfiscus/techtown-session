---
aliases: [agents, AI agent, autonomous agent, agentic AI]
tags: [technique, context-engineering, advanced]
---

# AI Agents

> Autonomous AI workers that can use tools, make decisions, and complete multi-step tasks.

## What Are AI Agents?

An AI agent is an AI system that can:
1. **Plan** — Break a goal into steps
2. **Use tools** — Access external systems via [[mcp]] or APIs
3. **Make decisions** — Choose which action to take based on results
4. **Iterate** — Adjust based on what it learns

Unlike a simple chatbot that responds to one message at a time, agents can complete **multi-step workflows** autonomously.

## How Agents Relate to Context Engineering

Agents are the **most demanding consumers** of context engineering:

- They need [[dynamic-context]] to make real-time decisions
- They need [[tool-context]] to interact with external systems
- They need [[episodic-context]] to remember what they've done
- Their [[context-window]] fills fast as they take multiple steps
- [[context-rot]] is a critical risk for long-running agents

**Good context engineering makes agents dramatically more capable.**

## What Enables Agents

| Enabler | Role |
|---------|------|
| [[mcp]] | Gives agents access to tools (read/write to external systems) |
| [[n8n]] | Orchestrates agent workflows, provides triggers and actions |
| [[system-prompt]] | Defines agent behavior, constraints, and goals |
| [[context-hydration]] | Pre-loads agents with relevant information |

## Agent Context Challenges

| Challenge | Context Engineering Solution |
|-----------|----------------------------|
| Agents lose focus over long tasks | [[compress-operation]] — summarize progress regularly |
| Agents don't know your business context | [[context-hydration]] — pre-load with relevant docs |
| Agents can't access live data | [[mcp]] — connect to real systems |
| Agents make decisions without enough info | [[select-operation]] — ensure relevant context is available |

## Founder Use Cases

- **Customer support agent** — Reads ticket, checks CRM, checks knowledge base, drafts response
- **Research agent** — Searches multiple sources, synthesizes findings, produces report
- **Content agent** — Reads brand voice, checks calendar, writes and schedules posts
- **Lead qualification agent** — Scores incoming leads based on CRM data and criteria

## For Founders

You don't need to build agents from scratch. Tools like [[n8n]] have built-in agent builders, and [[mcp]] provides the tool connections. The key is getting the **context** right — agents with bad context make bad autonomous decisions.

---

**See also:** [[mcp]], [[n8n]], [[tool-context]], [[workflow-automation]], [[context-hydration]]

#technique #advanced
