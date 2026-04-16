---
aliases: [attention, focus budget, attention limit]
tags: [core-concept, context-engineering]
---

# Attention Budget

> AI has a limited budget for paying attention. Every [[tokens|token]] you add depletes it. After a certain point, adding MORE context makes AI WORSE.

## The Concept

Even though AI models have large [[context-window|context windows]] (100K+ tokens), they don't pay equal attention to everything. There's a curve:

1. **Rising phase** — Adding relevant context improves accuracy
2. **Peak** — [[optimal-context]] reached
3. **Declining phase** — Noise drowns out signal, accuracy drops

## The Analogy

See: [[500-page-manual-analogy]]

Reading a 500-page manual to fix a faucet vs. reading just the 2-page faucet section. The 500-page version has "more context" but worse outcomes.

## In Practice

### What depletes the budget:
- Irrelevant documents pasted in
- Long conversation history with retries and mistakes ([[context-rot]])
- Boilerplate text that doesn't help the task
- Multiple topics mixed in one chat (needs [[isolate-operation]])

### What spends the budget well:
- Relevant source documents ([[select-operation]])
- Clear specifications and constraints
- Focused conversation on one topic
- Compressed summaries instead of raw transcripts ([[compress-operation]])

## The Founder Version

**Entire codebase pasted in:** AI gets lost, gives generic advice, misses the actual problem.

**Relevant file + error message:** AI focuses, identifies the bug, suggests the exact fix.

## Key Insight

> "The goal isn't maximum context. It's [[optimal-context]]."

## Strategies

1. Be selective — use [[select-operation]] to include only relevant context
2. Compress — use [[compress-operation]] to summarize verbose content
3. Isolate — use [[isolate-operation]] to keep separate tasks in separate chats
4. Hydrate deliberately — use [[context-hydration]] with intention

---

**See also:** [[optimal-context]], [[context-window]], [[context-rot]], [[tokens]]

#core-concept
