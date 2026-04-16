---
aliases: [RAG, retrieval augmented generation, retrieval, grounded generation]
tags: [technique, context-engineering, technical]
---

# RAG — Retrieval Augmented Generation

> Give AI access to YOUR data by retrieving relevant pieces before generating a response.

## What Is RAG?

RAG is a technique where AI **retrieves relevant information** from a knowledge base **before** generating its response. Instead of relying solely on training data, it grounds answers in your actual documents.

## How It Works

```
1. You ask a question
2. System searches your documents (using [[vector-embeddings]])
3. Relevant chunks are retrieved
4. Those chunks are injected into the [[context-window]]
5. AI generates answer grounded in YOUR data
```

## Why It Matters

Without RAG:
- AI answers from training data (potentially outdated or wrong)
- No grounding in your specific business context
- Hallucination risk is higher

With RAG:
- Answers grounded in your actual documents
- Can cite sources
- Stays current with your latest information
- Much lower hallucination risk

## RAG Is Context Engineering

RAG is fundamentally a [[select-operation]] technique:
- It **selects** the most relevant pieces from your knowledge base
- Injects only those pieces into the [[context-window]] ([[context-hydration]])
- Respects the [[attention-budget]] by retrieving only what's relevant
- Prevents [[context-rot]] by fetching fresh from source every time

## How RAG Relates to the Tools

| Tool | RAG Connection |
|------|---------------|
| [[notebooklm]] | IS a RAG system — retrieves from uploaded docs per query |
| [[obsidian-vector-brain]] | Vector brain enables RAG over your notes |
| [[mcp]] | Can connect to RAG systems as a tool |
| [[n8n]] | Can orchestrate RAG pipelines in workflows |

## The Flow

```
Your Knowledge Base (documents, notes, transcripts)
        ↓
    Embedded into [[vector-embeddings]]
        ↓
    Stored in vector database
        ↓
    [You ask a question]
        ↓
    Query embedded → nearest vectors found
        ↓
    Retrieved chunks injected into [[context-window]]
        ↓
    AI responds with grounded, relevant answer
```

## For Founders

RAG is what makes AI work with YOUR data instead of generic training data. You've already used it if you've ever:
- Uploaded documents to [[notebooklm]] and asked questions
- Used "search my files" in any AI tool
- Asked AI about content in your uploaded documents

## Limitations

- Quality depends on what's in your knowledge base
- Retrieval can miss relevant content if embeddings aren't great
- Chunk size matters — too small loses context, too big wastes [[tokens]]

---

**See also:** [[vector-embeddings]], [[select-operation]], [[notebooklm]], [[context-hydration]]

#technique #technical
