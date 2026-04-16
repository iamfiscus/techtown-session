---
aliases: [select, retrieve, pull, choose, curate]
tags: [operation, context-engineering]
---

# Select Operation

> **Pull the RIGHT context in.**
> Analogy: Grab only the relevant folder, not the whole filing cabinet.

## Definition

The Select operation is about **choosing which context to include** in the [[context-window]]. Not everything is relevant to every task. The skill is in selection — picking the high-signal pieces and leaving out the noise.

## Why It Matters

Your [[attention-budget]] is finite. Every piece of context you add either:
- **Helps** — relevant information that improves AI output
- **Hurts** — noise that dilutes attention and degrades output

Selection is the difference between [[optimal-context]] and context overload.

## How to Select

### Ask Yourself
1. "What does AI need to know for THIS specific task?"
2. "What's the minimum context for a good answer?"
3. "Am I adding this because it's relevant or just in case?"

### Selection Strategies
- **By task** — Only include docs relevant to the current task
- **By recency** — Prefer recent information over old
- **By relevance** — Use [[vector-embeddings]] to find semantically similar content
- **By role** — Include context that matches AI's current role/task

## Tools for Selection

| Tool | How It Selects |
|------|---------------|
| [[notebooklm]] | Searches across uploaded docs by meaning, returns relevant passages |
| [[rag]] | Retrieves semantically relevant chunks from a vector database |
| [[obsidian-vector-brain]] | Searches notes by meaning, not just keywords |
| [[mcp]] | AI selects which tools/data sources to query based on the task |

## Common Selection Mistakes

See: [[common-context-mistakes]]

| Mistake | Fix |
|---------|-----|
| Pasting EVERYTHING | Select only relevant docs |
| Including full documents | Extract relevant sections ([[compress-operation]]) |
| Not using search | Use [[rag]] or [[vector-embeddings]] to find relevant content |
| Selecting by keyword only | Select by MEANING (semantic search) |

## Relationship to Other Operations

| Combined With | Result |
|--------------|--------|
| [[write-operation]] | Write now → Select later when needed |
| [[compress-operation]] | Select relevant docs → then Compress them |
| [[context-hydration]] | Selection is the core of good hydration |

## The Filing Cabinet Analogy

See: [[filing-cabinet-analogy]]

You don't bring your entire filing cabinet to a meeting. You pull the relevant folder. Selection is the same — pull only what's needed.

---

**See also:** [[attention-budget]], [[optimal-context]], [[notebooklm]], [[rag]], [[filing-cabinet-analogy]]

#operation
