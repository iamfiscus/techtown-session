---
aliases: [isolate, separate, fresh start, new chat, partition]
tags: [operation, context-engineering]
---

# Isolate Operation

> **Split context for different tasks.**
> Analogy: Don't bring your grocery list to a board meeting.

See: [[grocery-list-analogy]]

## Definition

The Isolate operation is about **keeping separate tasks in separate contexts**. Each project, feature, or topic gets its own conversation so they don't contaminate each other.

## Why It's Critical

When you mix everything in one chat:
- Feature A's context confuses Feature B's work
- [[context-rot]] accelerates — more noise per topic
- [[attention-budget]] is split across unrelated topics
- Instructions for one task interfere with another

## When to Isolate

- **New project** → New conversation
- **New feature** → New conversation
- **Different domain** (marketing vs. code vs. strategy) → Separate conversations
- **Fresh start needed** → [[compress-operation|Compress]] key context, start new chat
- **After significant tangents** → Pull out, start clean

## The Pattern

```
Project A Chat → Only Project A context
Project B Chat → Only Project B context
Research Chat  → Only research context
Writing Chat   → Only writing context
```

NOT:
```
One Giant Chat → Everything mixed together → Context rot → Bad output
```

## Isolation + Re-injection

Isolation doesn't mean losing context. The pattern is:

1. **[[write-operation]]** — Save important context from current chat
2. **Isolate** — Start fresh conversation
3. **[[select-operation]]** — Bring in only what's relevant to the new task
4. **[[context-hydration]]** — Fill the new chat with targeted context

This gives you a clean [[context-window]] with only relevant information.

## Tools That Support Isolation

| Tool | How |
|------|-----|
| Any AI chat | Just start a new conversation |
| [[obsidian-vector-brain]] | External memory persists across isolated chats |
| [[mcp]] | Fresh tool connections in each chat |
| [[superdesign]] | Isolates "what it looks like" from "how to build it" |

## Connection to the Adoption App

See: [[adoption-app-case-study]]

The adoption app was built with isolation:
- Research chat → Design chat → Build chat → Each feature = separate chat
- Context from each phase was written externally and selectively re-injected

## Common Mistake

> "I don't want to lose my context by starting a new chat."

This fear causes people to keep decaying conversations going. The fix: **Write the important stuff externally first**, then start fresh. You lose the noise but keep the signal.

See: [[common-context-mistakes]]

---

**See also:** [[context-rot]], [[grocery-list-analogy]], [[write-operation]], [[compress-operation]]

#operation
