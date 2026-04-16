---
aliases: [context limit, token limit, window]
tags: [core-concept, context-engineering]
---

# Context Window

The context window is the **total amount of information AI can process at once** in a single conversation. Think of it as AI's working memory — everything it can "see" at any given moment.

## How It Works

- Measured in [[tokens]] (roughly 4 characters per token)
- Typical sizes: 100K–200K tokens for most models, up to 1M for [[notebooklm]]
- Includes EVERYTHING: [[system-prompt]], conversation history, uploaded files, tool outputs
- Once full, older content gets dropped or summarized

## Why It Matters

The context window is the **battlefield of [[context-engineering]]**. Every decision you make is about what goes IN this window and what stays OUT.

Too little → AI lacks the info it needs
Too much → [[attention-budget]] depleted, AI loses focus
Just right → [[optimal-context]]

## What Goes In The Window

```
[System Prompt]           ← Hidden instructions
[Conversation History]    ← Every message so far
[Uploaded Documents]      ← Files you provide
[Tool Outputs]            ← Results from MCP, searches
[Your Current Prompt]     ← What you just typed
```

See: [[message-queue]] for how AI structures this internally.

## The Problem

Every [[tokens|token]] competes for space. Bad prompts, retries, and irrelevant context all consume window space — leading to [[context-rot]].

This is why the [[compress-operation]] and [[isolate-operation]] exist — to keep the window clean and focused.

## Size Comparison

| Model / Tool | Context Window | Approximate Words |
|--------------|---------------|-------------------|
| GPT-4 | ~128K tokens | ~96K words |
| Claude | ~200K tokens | ~150K words |
| [[notebooklm]] | ~1M tokens | ~750K words |

## Strategies

- Use [[context-hydration]] to fill the window deliberately
- Apply [[compress-operation]] to keep only what matters
- Use [[isolate-operation]] to start fresh when needed
- Leverage [[write-operation]] to store context externally

---

**See also:** [[tokens]], [[attention-budget]], [[context-rot]], [[optimal-context]]

#core-concept
