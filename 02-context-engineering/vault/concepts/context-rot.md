---
aliases: [rot, context decay, context degradation, conversation decay]
tags: [core-concept, context-engineering, problem]
---

# Context Rot

> "If your AI is getting dumber the longer you talk, it's not broken. It's rotting."

## The Concept

Context rot is the **gradual degradation of AI performance** as a conversation gets longer. The more messages in a chat, the more noise accumulates, and the harder it becomes for AI to find and use the important information.

## The Analogy

See: [[phone-call-analogy]]

You're on a 2-hour phone call. By minute 90, you've forgotten what was said in minute 10. AI has the same problem.

## Symptoms

- Long conversations get **worse** over time
- Important instructions from early in the chat get **"buried"**
- AI starts **contradicting** its own earlier answers
- Stale information **misleads** decisions
- AI "forgets" constraints you set at the beginning

## Why It Happens

1. **[[attention-budget]] dilution** — More tokens means less attention per token
2. **Noise accumulation** — Bad prompts, retries, tangents all stay in context
3. **Instruction burial** — Early instructions get pushed further from current focus
4. **Stale context** — Information that was true 30 messages ago may no longer be relevant

## Connection to Session 1

> "Every bad prompt, every retry, every 'that's not what I meant' **stays in context** and pollutes future responses." — Session 1, Slide 6

This is the **mechanical explanation** for why that happens. [[prompt-engineering]] taught you what happens. [[context-engineering]] teaches you the mechanics and fixes.

## The Fixes

| Fix | Operation | Tool |
|-----|-----------|------|
| Start fresh conversations for new tasks | [[isolate-operation]] | New chat |
| Summarize and carry forward key decisions | [[compress-operation]] | Manual or AI summary |
| Store context externally, re-inject as needed | [[write-operation]] + [[select-operation]] | [[obsidian-vector-brain]], docs |
| Use tools that auto-refresh context | [[dynamic-context]] | [[mcp]], [[n8n]] |

## Prevention Strategies

1. **One topic per chat** — Don't mix projects in one conversation
2. **Periodic summarization** — Compress long threads into key points
3. **External storage** — Save decisions to [[obsidian-vector-brain]] or docs
4. **Fresh starts with re-injection** — Start new chat, paste in just the relevant context
5. **Automated hydration** — Let [[n8n]] assemble fresh context each time

## Related Problems
- [[common-context-mistakes]] — Most mistakes are context rot in disguise
- [[attention-budget]] — Rot depletes the budget faster

---

**See also:** [[context-window]], [[isolate-operation]], [[compress-operation]], [[phone-call-analogy]]

#core-concept #problem
