---
aliases: [tool mapping, context to tool map, problem-tool map]
tags: [framework, context-engineering, reference]
---

# Tool Map

> One reference mapping context problems → operations → tools.

## The Map

| Context Problem | Operation | Tool |
|----------------|-----------|------|
| "I need to research across many docs" | [[select-operation]] | [[notebooklm]] |
| "I need persistent memory across sessions" | [[write-operation]] | [[obsidian-vector-brain]] |
| "I need AI to access my live tools & data" | [[dynamic-context]] | [[mcp]] |
| "I need context to flow automatically" | [[context-hydration]] | [[n8n]] |
| "I need to plan/structure before building" | [[compress-operation]] + [[isolate-operation]] | [[superdesign]] |

## Expanded Map

| Problem | Root Cause | Operation | Tool | Context Type |
|---------|-----------|-----------|------|-------------|
| AI gives generic responses | Missing context | [[context-hydration]] | All tools | All types |
| Conversations get worse over time | [[context-rot]] | [[isolate-operation]] | New chats | N/A |
| Losing track of decisions | No external storage | [[write-operation]] | [[obsidian-vector-brain]] | [[episodic-context]] |
| Can't find patterns in research | Too much data, no search | [[select-operation]] | [[notebooklm]] | [[static-context]] |
| Manually copy-pasting data | No tool connections | [[dynamic-context]] access | [[mcp]] | [[tool-context]] |
| Repeating the same manual work | No automation | [[context-hydration]] | [[n8n]] | [[dynamic-context]] |
| UI descriptions are too vague | Verbal → visual gap | [[compress-operation]] | [[superdesign]] | [[static-context]] |
| Too much context, AI confused | [[attention-budget]] depleted | [[compress-operation]] | Manual or AI summary | N/A |

## Visual Relationships

```
         [Context Types]          [Operations]          [Tools]
         ─────────────           ──────────────        ────────
         Static      ──────────→  Select      ──────→  NotebookLM
         Dynamic     ──────────→  (Dynamic)   ──────→  MCP
         Episodic    ──────────→  Write       ──────→  Obsidian
         Tool        ──────────→  Hydration   ──────→  N8N
                                  Compress    ──────→  SuperDesign
                                  Isolate     ──────→  (Fresh chats)
```

## Using the Map

See: [[decision-framework]] for the decision tree.
See: [[context-audit]] for applying this to your own workflow.

---

**See also:** [[decision-framework]], [[context-audit]], [[context-engineering]]

#framework #reference
