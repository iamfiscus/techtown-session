---
aliases: [right amount of context, goldilocks context]
tags: [core-concept, context-engineering, principle]
---

# Optimal Context

> "The goal isn't maximum context. It's optimal context."

## The Principle

There's a sweet spot for how much context AI needs. Too little and it lacks information. Too much and the [[attention-budget]] gets depleted by noise. Optimal context is the **minimum amount of highly relevant information** needed for the task.

## The Curve

```
AI Accuracy
    ^
    |        ___
    |      /     \
    |    /         \
    |  /             \
    | /                \
    |/                   \
    +-------------------------> Amount of Context

   [Too little]  [Optimal]  [Too much]
```

## Examples

### Too Little Context
- "Fix the bug" with no code provided
- AI guesses, gives generic advice

### Optimal Context
- Relevant file + error message + what you expected
- AI pinpoints the issue, gives exact fix

### Too Much Context
- Entire 50,000-line codebase pasted in
- AI gets confused, gives surface-level suggestions, misses the real issue

## How to Find Optimal

1. **Start with the task** — What does AI need to know to complete THIS task?
2. **[[select-operation]]** — Pull only relevant documents, not everything
3. **[[compress-operation]]** — Summarize verbose sources
4. **[[isolate-operation]]** — Keep separate tasks in separate chats
5. **Test and iterate** — If output is generic, add more targeted context

## The Operations That Create Optimal Context

| Operation | How It Helps |
|-----------|-------------|
| [[select-operation]] | Brings in only what's relevant |
| [[compress-operation]] | Reduces noise while keeping signal |
| [[isolate-operation]] | Prevents cross-contamination between tasks |
| [[context-hydration]] | Deliberately fills with the right info |

## Anti-Patterns

- Pasting everything "just in case" → depletes [[attention-budget]]
- Long running chats → [[context-rot]] fills window with noise
- Not providing enough context → AI hallucinates to fill gaps

---

**See also:** [[attention-budget]], [[context-hydration]], [[context-window]], [[500-page-manual-analogy]]

#core-concept #principle
