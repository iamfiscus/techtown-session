---
aliases: [hydration, context loading, pre-loading context]
tags: [core-concept, context-engineering]
---

# Context Hydration

> Deliberately filling the [[context-window]] with the right information **before** AI acts.

## The Concept

Context hydration is the act of **pre-loading AI with relevant information** before asking it to do work. It's like briefing an employee before a meeting — the more relevant the briefing, the better they perform.

## Simple Analogy

See: [[500-page-manual-analogy]]

Reading a 500-page manual to fix a leaky faucet vs. reading the 2-page section on faucets. Both are "context" — but one helps and one hurts.

## How to Hydrate

### Manual Hydration
- Copy-paste relevant docs into the chat
- Upload files before asking questions
- Include background information in your prompt ([[prompt-engineering]])

### Automated Hydration
- [[n8n]] assembles context from multiple sources automatically
- [[mcp]] pulls live data from connected tools
- [[rag]] retrieves relevant documents based on your query
- [[notebooklm]] searches across uploaded sources

## The Danger of Over-Hydration

More context isn't always better. See: [[attention-budget]].

When you add too much context:
- AI's attention gets diluted
- Irrelevant info competes with relevant info
- Quality actually **decreases** past the peak

This is why you want [[optimal-context]], not maximum context.

## Connection to Operations

| Operation | Role in Hydration |
|-----------|------------------|
| [[select-operation]] | Choose WHAT to hydrate with |
| [[compress-operation]] | Trim to only what matters |
| [[write-operation]] | Store context so it's available for hydration |
| [[isolate-operation]] | Start fresh so hydration is clean |

## The Tool

[[n8n]] is specifically the **hydration engine** — it automates the assembly of context from multiple sources and delivers it to AI without manual work.

---

**See also:** [[attention-budget]], [[optimal-context]], [[n8n]], [[context-window]]

#core-concept #operation
