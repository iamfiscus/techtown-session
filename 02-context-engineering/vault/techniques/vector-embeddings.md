---
aliases: [embeddings, vectors, semantic coordinates, meaning-space]
tags: [technique, context-engineering, technical]
---

# Vector Embeddings

> "GPS coordinates for ideas — similar ideas have nearby coordinates."

## What Are Embeddings?

Vector embeddings are a way to convert text (words, sentences, documents) into **numbers that capture meaning**. In this number-space, similar concepts are close together and different concepts are far apart.

## The Simple Explanation

> "The word 'king' is near 'queen' and far from 'bicycle' in meaning-space."

Imagine every idea has a location on a map. Related ideas are neighbors. Unrelated ideas are on different continents. Embeddings create this "meaning map."

## Why They Matter for [[context-engineering]]

Embeddings enable **semantic search** — finding content by meaning rather than exact keywords.

### Keyword search
Query: "pricing strategy" → Only finds notes that contain those exact words.

### Semantic search (with embeddings)
Query: "pricing strategy" → Also finds notes about "revenue model," "monetization approach," "how much to charge," "freemium vs paid."

## How They Work (Non-Technical)

1. **Take a piece of text** — "We decided to offer a free tier"
2. **Convert to numbers** — [0.23, -0.87, 0.45, ...] (hundreds of dimensions)
3. **Store the numbers** — In a vector database
4. **When searching** — Convert query to numbers, find nearby vectors
5. **Return matches** — Notes with similar meaning-coordinates

## Connection to Tools

| Tool | How It Uses Embeddings |
|------|----------------------|
| [[obsidian-vector-brain]] | Creates embeddings of your notes for semantic search |
| [[rag]] | Retrieves relevant document chunks via embedding similarity |
| [[notebooklm]] | Uses embeddings internally to find relevant passages |

## Connection to Operations

- [[select-operation]] — Embeddings make selection **smarter** (by meaning, not keywords)
- [[write-operation]] — Write content → embed it → it's searchable by meaning forever
- [[second-brain]] — Embeddings are what make a second brain actually searchable

## For Founders

You don't need to understand the math. You need to understand the implication:

> **AI can find your notes by what they MEAN, not just what words they contain.**

This changes how you organize information. Instead of perfect folder structures and tags, you can just write naturally and let embeddings handle discovery.

---

**See also:** [[obsidian-vector-brain]], [[rag]], [[second-brain]], [[knowledge-graphs]]

#technique #technical
