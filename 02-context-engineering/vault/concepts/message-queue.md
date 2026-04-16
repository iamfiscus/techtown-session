---
aliases: [conversation structure, chat history, message list]
tags: [core-concept, technical]
---

# Message Queue

The message queue is how AI **actually sees your conversation** — as a structured list of messages with defined roles.

## Structure

Every conversation is a sequence of typed messages:

| Role | What It Is | Example |
|------|-----------|---------|
| **SYSTEM** | Hidden instructions (you don't see these) | "You are a helpful coding assistant..." |
| **USER** | Your messages | "Build me a landing page with..." |
| **ASSISTANT** | AI's responses | "I'll create that for you. Here's the code..." |
| **TOOL** | Results from connected tools | [File written] [Search results] [API response] |

## Why It Matters

- AI reads the **entire queue** every turn
- Every message adds [[tokens]] to the [[context-window]]
- Old messages don't disappear — they accumulate
- This is why [[context-rot]] happens — the queue fills with noise

## The [[system-prompt]]

The system prompt sits at the top of every message queue. It's the hidden instruction layer that shapes AI behavior. Think of it as the "personality and rules" injected before you ever type anything.

## Connection to Context Engineering

The message queue IS the [[context-window]] in practice. Every operation in [[context-engineering]] is about managing what goes into this queue:

- [[write-operation]] — Save important info from the queue to external storage
- [[select-operation]] — Choose what to inject into the queue
- [[compress-operation]] — Summarize parts of the queue to save space
- [[isolate-operation]] — Start a new queue (fresh conversation)

## Practical Implication

> "Each message adds to the context window — AI reads ALL of this every turn."

This means every bad prompt, every retry, every tangent stays in the queue and pollutes all future responses. This is the mechanical reason why [[prompt-engineering]] matters so much.

---

**See also:** [[context-window]], [[system-prompt]], [[tokens]], [[context-rot]]

#core-concept #technical
