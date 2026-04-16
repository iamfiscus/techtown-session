---
aliases: [compress, summarize, trim, distill, condense]
tags: [operation, context-engineering]
---

# Compress Operation

> **Keep only what matters.**
> Analogy: Summarize a 2-hour meeting into 5 bullet points.

## Definition

The Compress operation is about **reducing the volume of context while preserving the essential meaning**. It's how you fit more signal into fewer [[tokens]], making your [[attention-budget]] go further.

## Why It's Needed

- Long conversations accumulate noise → [[context-rot]]
- Full documents contain lots of irrelevant sections
- Raw transcripts are verbose and unfocused
- The [[context-window]] has finite space

Compression lets you keep the MEANING without the bulk.

## What to Compress

| Source | Compressed To |
|--------|-------------|
| 2-hour meeting transcript | 5 key decisions + action items |
| 50-page research report | 2-page executive summary |
| Long conversation history | Key decisions + current status |
| Full codebase | Relevant file + error message |
| Customer interview transcripts | Themes + key quotes |

## How to Compress

### Manual Compression
- Ask AI: "Summarize this conversation into key decisions and open questions"
- Extract only the relevant section from a document
- Write a brief instead of pasting the full source

### AI-Assisted Compression
- Use [[notebooklm]] to summarize across multiple documents
- Ask AI to distill a long thread into bullet points
- Use [[compress-operation]] before [[write-operation]] — save the summary, not the raw content

### Automated Compression
- [[n8n]] can trigger AI summarization of incoming content
- [[rag]] inherently compresses by returning only relevant chunks, not full documents

## Relationship to Other Operations

| Combined With | Result |
|--------------|--------|
| [[write-operation]] | Compress → then Write the summary for future use |
| [[select-operation]] | Select relevant docs → then Compress them for injection |
| [[isolate-operation]] | Compress current state → Start fresh chat → Inject summary |

## The "Compress and Carry" Pattern

The most common anti-[[context-rot]] pattern:

1. Long conversation starts decaying
2. **Compress:** Ask AI to summarize key decisions + current status
3. **Carry:** Copy summary
4. **Isolate:** Start fresh conversation
5. **Inject:** Paste summary into new chat

Now you have all the important context without the noise.

## Connection to [[superdesign]]

Design is a form of compression — you compress your intent ("I want a dashboard that shows X, Y, Z") into a **visual artifact** that communicates far more than words with far fewer [[tokens]].

---

**See also:** [[attention-budget]], [[context-rot]], [[optimal-context]], [[superdesign]]

#operation
