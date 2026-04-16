---
aliases: [external memory, persistent memory, knowledge base, personal knowledge management, PKM]
tags: [technique, context-engineering, knowledge-management]
---

# Second Brain

> A persistent external memory system that AI can access across sessions and tools.

## The Concept

A second brain is an **organized external knowledge store** — your notes, decisions, insights, and learnings — stored outside of any single AI conversation so they persist indefinitely and can be accessed by any tool.

## Why You Need One

AI conversations are **ephemeral**. When you close a chat:
- Decisions disappear
- Lessons are forgotten
- Context is lost
- You start from zero

A second brain solves this by giving AI access to your **accumulated knowledge** — [[episodic-context]] that survives across sessions.

## The Building Blocks

| Component | What It Does | Tool |
|-----------|-------------|------|
| **Notes** | Raw knowledge capture | [[obsidian-vector-brain\|Obsidian]] |
| **Links** | Connect related ideas | `[[wikilinks]]` in Obsidian |
| **[[vector-embeddings]]** | Enable semantic search | Embedding tools |
| **Storage** | Persistent, accessible | GitHub repo/gist |
| **Retrieval** | Find relevant notes | [[rag]], semantic search |

## How to Build One

1. **Write consistently** — After every important conversation, capture key decisions ([[write-operation]])
2. **Link freely** — Use `[[wikilinks]]` to connect related notes ([[knowledge-graphs]])
3. **Embed for search** — Create [[vector-embeddings]] so AI can search by meaning
4. **Store persistently** — GitHub repo or gist that AI can read
5. **Retrieve when needed** — [[select-operation]] to inject relevant context into new conversations

## What Goes in a Second Brain

- **Decisions** — What was decided and WHY
- **Lessons learned** — What worked, what didn't
- **Research** — Customer insights, market analysis
- **Preferences** — Your brand voice, coding style, communication preferences
- **Project state** — Current status, open questions, next steps
- **Prompt library** — Effective prompts you've used

## Connection to Context Engineering

The second brain is the **physical manifestation** of the [[write-operation]] + [[select-operation]] loop:

```
Experience → Write to second brain → Time passes →
New task → Select from second brain → AI has episodic context
```

It prevents [[context-rot]] because the knowledge is stored **outside** the decaying conversation.

## For Founders

Think of it as **institutional memory for a company of one**. As you make decisions, learn from mistakes, and build knowledge — it all gets captured in a system that AI can access.

Six months from now, when you ask AI about your pricing strategy, it can read your actual decision notes instead of guessing.

---

**See also:** [[obsidian-vector-brain]], [[write-operation]], [[episodic-context]], [[knowledge-graphs]], [[vector-embeddings]]

#technique #knowledge-management
