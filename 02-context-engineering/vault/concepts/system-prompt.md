---
aliases: [system message, system instructions, hidden instructions]
tags: [core-concept, technical]
---

# System Prompt

The system prompt is the **hidden instruction layer** that sits at the top of every AI conversation's [[message-queue]]. Users typically don't see it, but it profoundly shapes AI behavior.

## What It Does

- Defines AI's role and personality
- Sets behavioral constraints (what AI should/shouldn't do)
- Provides persistent context that applies to every message
- Establishes rules, tone, and formatting preferences

## Example

```
SYSTEM: "You are a helpful startup advisor. You specialize in early-stage
SaaS companies. Always provide actionable advice. Never give legal or
financial advice — suggest consulting a professional instead."
```

## Connection to Context Engineering

The system prompt is the **most powerful piece of [[static-context]]** because:
- It's always present (first in the [[message-queue]])
- It shapes every response
- It consumes [[tokens]] from the [[context-window]]
- It's a form of persistent [[context-hydration]]

## Tools That Leverage System Prompts

- [[notebooklm]] — Custom goals/personas act as system prompt customization
- [[mcp]] — Tools inject their capabilities into the system prompt
- [[ai-agents]] — Each agent has a specialized system prompt

## As [[static-context]]

The system prompt is the purest form of static context — it doesn't change during the conversation and provides the foundational instructions that everything else builds on.

## For Founders

When you use tools like Claude or ChatGPT, you can customize system prompts via:
- Custom instructions (ChatGPT)
- Project instructions (Claude)
- System prompts in API calls

This is a form of [[write-operation]] — you're writing persistent context that applies to every conversation.

---

**See also:** [[message-queue]], [[static-context]], [[context-window]], [[prompt-engineering]]

#core-concept #technical
