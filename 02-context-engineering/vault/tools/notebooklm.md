---
aliases: [NotebookLM, Google NotebookLM, notebook lm, research brain]
tags: [tool, context-engineering, google]
---

# NotebookLM — "The Research Brain"

> **Solves:** [[select-operation]] — pulling the right context from many sources.

## What It Is

NotebookLM is Google's AI-powered research assistant that lets you upload multiple documents and ask questions across all of them. It's the ultimate [[select-operation]] tool.

## Kitchen Table Analogy

Imagine you could upload every book you've ever read and ask questions across all of them at once. That's NotebookLM.

## Key Features

| Feature | What It Means |
|---------|--------------|
| **1M token [[context-window]]** | ~750K words — upload entire research libraries |
| **Saved conversation history** | [[episodic-context]] persists across sessions |
| **Custom goals & personas** | Shape responses to your role and needs |
| **Audio overview** | Turn research into a podcast for learning on the go |
| **Source citations** | Every answer links back to the original document |

## Founder Use Cases

- Upload pitch deck + market research + competitor analysis + 20 customer interview transcripts → Ask "What's my biggest blind spot?"
- Upload all documentation → Ask "What are the contradictions across these docs?"
- Upload user research → Ask "What are the top 3 unmet needs?"
- Upload meeting notes from the last quarter → Ask "What decisions did we reverse?"

## Context Engineering Connection

NotebookLM is a **[[select-operation]] engine**:
- Takes massive amounts of [[static-context]]
- Lets you pull out exactly what you need via natural language queries
- Prevents [[context-rot]] because it retrieves fresh from source docs every time (not from a decaying conversation)
- Source citations let you verify (no hallucination)

## How It Differs from Regular Chat

| Regular AI Chat | NotebookLM |
|----------------|------------|
| You paste context manually | Upload docs once, query forever |
| [[context-rot]] over time | Fresh retrieval every query |
| Limited [[context-window]] | 1M token window |
| No source tracking | Citations link to original docs |

## When to Use NotebookLM

Use the [[decision-framework]]:
- "I need to research across many docs" → **NotebookLM**
- You have lots of [[static-context]] (documents, transcripts, reports)
- You need to find patterns across multiple sources
- You want answers grounded in YOUR data, not AI's training data

## Limitations

- Primarily for [[static-context]] — not great for [[dynamic-context]] that changes hourly
- Upload-based — you manually add documents
- Google ecosystem — requires Google account

---

**See also:** [[select-operation]], [[static-context]], [[rag]], [[tool-map]]

#tool
