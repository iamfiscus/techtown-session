---
aliases: [which tool, tool decision, decision tree]
tags: [framework, context-engineering, practical]
---

# Decision Framework

> "Which tool solves my context problem?"

## By Need

```
What do I need?
│
├── Research across many docs? --------→ [[notebooklm]]
├── Remember things across sessions? --→ [[obsidian-vector-brain]]
├── Connect AI to live tools & data? --→ [[mcp]]
├── Automate context assembly? --------→ [[n8n]]
└── Plan visually before building? ----→ [[superdesign]]
```

## By Operation

```
What operation am I performing?
│
├── Need to save context? ----→ [[write-operation]] (Obsidian, docs, GitHub)
├── Need to retrieve context? → [[select-operation]] (NotebookLM, search, RAG)
├── Need to trim context? ----→ [[compress-operation]] (summarize, fresh chats)
└── Need to separate tasks? --→ [[isolate-operation]] (new chats, project separation)
```

## Quick Decision Matrix

| If you're... | You need... | Use... |
|-------------|-------------|--------|
| Drowning in docs | [[select-operation]] | [[notebooklm]] |
| Losing decisions between sessions | [[write-operation]] | [[obsidian-vector-brain]] |
| Tired of copy-pasting data | [[dynamic-context]] | [[mcp]] |
| Doing the same manual work repeatedly | [[context-hydration]] | [[n8n]] |
| Describing UI in words | [[compress-operation]] | [[superdesign]] |
| Getting worse output over time | Fix [[context-rot]] | [[isolate-operation]] + [[compress-operation]] |
| AI gives generic responses | Missing context | [[context-hydration]] + relevant type |

## For Multi-Tool Workflows

Many real tasks need multiple tools. See [[adoption-app-case-study]] for an example:

1. **Research phase:** [[notebooklm]] (Select)
2. **Memory phase:** [[obsidian-vector-brain]] (Write)
3. **Design phase:** [[superdesign]] (Compress)
4. **Build phase:** [[mcp]] (Dynamic)
5. **Iterate phase:** Fresh conversations (Isolate)

## Starting Point

If you're new to [[context-engineering]], start with:
1. **[[notebooklm]]** — Easiest to try. Upload docs, ask questions.
2. **[[isolate-operation]]** — Free. Just start new chats for new tasks.
3. **Then explore** [[obsidian-vector-brain]], [[mcp]], [[n8n]] as you get comfortable.

See also: [[context-audit]], [[tool-map]]

---

**See also:** [[tool-map]], [[context-audit]], [[context-engineering]]

#framework #practical
