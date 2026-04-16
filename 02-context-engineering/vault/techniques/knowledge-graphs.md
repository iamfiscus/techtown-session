---
aliases: [knowledge graph, connected knowledge, graph view, linked notes]
tags: [technique, context-engineering, knowledge-management]
---

# Knowledge Graphs

> Connected webs of knowledge where relationships between ideas are as important as the ideas themselves.

## What Is a Knowledge Graph?

A knowledge graph is a network of **nodes** (concepts) connected by **edges** (relationships). Unlike a folder hierarchy, it represents how ideas actually connect — in webs, not trees.

## Why It Matters for Context Engineering

Knowledge graphs enable:
- **Discovery** — Find related concepts you didn't think to search for
- **Navigation** — Follow connections between ideas
- **[[select-operation]]** — Pull in related context along relationship paths
- **Understanding** — See the big picture of how concepts relate

## In Obsidian

Obsidian's graph view is a visual knowledge graph built from `[[wikilinks]]`:

- Each note is a node
- Each `[[link]]` is an edge
- Clusters form naturally around related topics
- Orphan notes (no connections) are easy to spot

## This Vault Is a Knowledge Graph

This very vault demonstrates the concept:
- [[context-engineering]] links to all 4 operations, 4 types, and 5 tools
- Each tool links back to the operations it solves
- Analogies link to the concepts they explain
- Everything forms a connected web

## How It Enhances AI

When AI accesses a knowledge graph (via [[obsidian-vector-brain]]):
1. Ask about "pricing" → finds pricing decision note
2. Follows links to → market research, competitor analysis, customer feedback
3. Returns a **connected answer** that draws on multiple related sources
4. This is richer than searching for "pricing" alone

## Compared to Folders

| Folders | Knowledge Graph |
|---------|----------------|
| One location per file | Multiple connections per file |
| Rigid hierarchy | Flexible web |
| Search by location | Search by relationship |
| Hard to discover connections | Connections are visible |

## For Founders

You don't need to build a perfect structure upfront. Just:
1. Write notes ([[write-operation]])
2. Link related notes with `[[wikilinks]]`
3. Over time, a graph emerges naturally
4. Use graph view to discover unexpected connections

## Connection to [[vector-embeddings]]

Knowledge graphs and embeddings are complementary:
- **Graph:** Explicit relationships you define (`[[links]]`)
- **Embeddings:** Implicit relationships discovered by meaning
- Together: both explicit and implicit connections available

---

**See also:** [[obsidian-vector-brain]], [[second-brain]], [[vector-embeddings]], [[select-operation]]

#technique #knowledge-management
