---
aliases: [Obsidian, vector brain, second brain tool, obsidian vault]
tags: [tool, context-engineering, knowledge-management]
---

# Obsidian + Vector Brain — "The Second Brain"

> **Solves:** [[write-operation]] — persistent context that survives across sessions.

## What It Is

Obsidian is a markdown-based note-taking app that stores everything locally. Combined with [[vector-embeddings]], it becomes a "vector brain" — a knowledge base that AI can search by **meaning**, not just keywords.

## Kitchen Table Analogy

See: [[filing-cabinet-analogy]]

Your notes are scattered Post-its on the fridge. A vector brain is a filing cabinet that also understands what the notes **MEAN** and how they connect.

## How It Works

1. **Take notes in Obsidian** — All markdown, all local, all yours
2. **Create [[vector-embeddings]]** — Convert notes to mathematical meaning-coordinates
3. **Store in GitHub/Gist** — Persistent, version-controlled, accessible by AI
4. **AI searches by meaning** — "What decisions have I made about pricing?" finds answers from notes 6 months ago

## What Makes It Special

### Obsidian's Graph View
Your notes form a [[knowledge-graphs|knowledge graph]] — visual connections between linked ideas. `[[wikilinks]]` create the web of relationships.

### Vector Brain Layer
[[vector-embeddings]] add **semantic search** — finding notes by meaning rather than exact keywords. See: [[vector-embeddings]] for how this works.

### GitHub as Persistence
Store your vault (or processed embeddings) in a GitHub repo or gist. Now any AI tool (Claude, ChatGPT, Cursor) can read your [[second-brain]] across sessions and platforms.

## Founder Use Cases

- **Decision journal** — Save every major decision + rationale. Query later.
- **Research notes** — Store insights from customer interviews, competitor analysis.
- **Project memory** — What was tried, what worked, what failed.
- **Prompt library** — Save effective prompts for reuse.
- **Meeting notes** — Summarize meetings, link to related projects.

## Context Engineering Connection

This is the **[[write-operation]] at scale**:
- You build a **permanent context store** outside any single conversation
- When [[context-rot]] degrades a chat, your second brain doesn't rot
- Future conversations can [[select-operation|select]] from your stored knowledge
- [[episodic-context]] persists indefinitely

## The Write → Select Loop

1. **Write** decisions and insights to Obsidian during/after AI conversations
2. **Later**, when starting a new conversation, **Select** relevant notes
3. Inject them as [[context-hydration]]
4. AI has [[episodic-context]] without [[context-rot]]

## When to Use Obsidian + Vector Brain

Use the [[decision-framework]]:
- "I need persistent memory across sessions" → **Obsidian + Vector Brain**
- You want to build institutional knowledge over time
- You need AI to "remember" past decisions
- You're working across multiple tools and need a central knowledge store

---

**See also:** [[write-operation]], [[second-brain]], [[vector-embeddings]], [[knowledge-graphs]], [[episodic-context]]

#tool
