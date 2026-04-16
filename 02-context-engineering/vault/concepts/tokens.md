---
aliases: [token, tokenization, tokenized]
tags: [core-concept, context-engineering, technical]
---

# Tokens

Tokens are the **fundamental unit of AI processing**. Every piece of text AI reads or generates is broken into tokens first.

## What Is a Token?

A token is roughly **4 characters** or **3/4 of a word**. AI doesn't see words — it sees tokens.

**Example:**
`Build me a landing page` → `[Build]` `[me]` `[a]` `[land]` `[ing]` `[page]`

That's 6 tokens for 5 words.

## Why Tokens Matter

1. **Cost** — You pay per token (both input and output)
2. **Speed** — More tokens = slower responses
3. **[[context-window]]** — Measured in tokens, not words
4. **[[attention-budget]]** — Every token competes for AI's attention

## Token Economics

| What | Tokens | Cost Implication |
|------|--------|-----------------|
| A short prompt | ~50 tokens | Cheap |
| A full page of text | ~500 tokens | Moderate |
| A long document | ~10,000 tokens | Expensive |
| A full codebase | ~100,000+ tokens | Very expensive + [[attention-budget]] depleted |

## Connection to Context Engineering

Every context engineering decision is ultimately about **token management**:

- [[select-operation]] — Choose which tokens enter the [[context-window]]
- [[compress-operation]] — Reduce token count while preserving meaning
- [[isolate-operation]] — Start with a clean token slate
- [[write-operation]] — Store tokens externally so you can selectively re-inject them

## The Insight

> "More tokens = more cost + slower responses + less room for context."

This is why [[optimal-context]] matters — every token you add that isn't helping is actively hurting.

---

**See also:** [[context-window]], [[attention-budget]], [[optimal-context]]

#core-concept #technical
