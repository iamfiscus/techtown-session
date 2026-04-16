---
aliases: [episodic, history, memory, past decisions]
tags: [context-type, context-engineering]
---

# Episodic Context

> Analogy: **Your memory of past meetings** — what was discussed, decided, and learned.

## Definition

Episodic context is **history and past decisions** — the accumulated knowledge from previous conversations, experiments, and experiences. It's what makes the difference between AI that treats every interaction as day one vs. AI that builds on what came before.

## Examples

- Previous conversation history with AI
- Lessons learned from past projects
- Decisions made and their rationale
- Mistakes and what you learned from them
- Prior feedback from users or stakeholders
- Historical performance data
- Previous versions of a document and why they changed

## Why It Matters

Without episodic context, AI:
- Re-suggests ideas you've already rejected
- Doesn't know what you've tried before
- Can't build on previous decisions
- Treats every conversation as brand new

With episodic context, AI:
- Remembers your preferences
- Avoids repeating past mistakes
- Builds incrementally on prior work
- Provides continuity across sessions

## The Problem

Most AI chats **don't persist episodic context** between sessions. When you start a new chat, all history is gone. This is a fundamental challenge that requires external tools.

This is why [[write-operation]] matters — you need to **save** episodic context somewhere that persists.

## Tools That Provide Episodic Context

| Tool | How |
|------|-----|
| [[obsidian-vector-brain]] | Store decisions, lessons, and history as searchable notes |
| [[notebooklm]] | Saved conversation history persists across sessions |
| [[second-brain]] | External memory system that AI can access |

## Connection to Context Rot

[[context-rot]] is partly an episodic context problem. As conversations get long, early episodic context (decisions made, constraints agreed upon) gets buried under newer messages. The fix is to [[compress-operation|compress]] and externalize key decisions.

## Building Episodic Context

1. **After every important conversation** — Write down key decisions ([[write-operation]])
2. **Document the WHY** — Not just what you decided, but why
3. **Store in a searchable system** — [[obsidian-vector-brain]], not random docs
4. **Re-inject when starting new chats** — [[select-operation]] + [[context-hydration]]

## Compared to Other Types

| Type | Changes? | Example |
|------|----------|---------|
| [[static-context]] | Rarely | Brand guidelines |
| [[dynamic-context]] | Constantly | CRM data, metrics |
| **Episodic** | Accumulates | Conversation history |
| [[tool-context]] | On-demand | API responses |

---

**See also:** [[obsidian-vector-brain]], [[second-brain]], [[write-operation]], [[context-rot]]

#context-type
