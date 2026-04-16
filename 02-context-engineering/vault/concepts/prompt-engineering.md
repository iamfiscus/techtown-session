---
aliases: [prompting, prompt methods, session 1]
tags: [core-concept, session-1]
---

# Prompt Engineering

> Session 1 taught prompting. Session 2 builds on it with [[context-engineering]].

Prompt engineering is the practice of **crafting effective instructions** for AI. It focuses on WHAT you say and HOW you say it.

## Session 1: The Core 10 Methods

### Tier 1: Core 5
1. **Markdown Headers** — Structure with `# Section ## Subsection`
2. **ALL CAPS for Constraints** — `MUST, NEVER, REQUIRED`
3. **Constraint Sandwich** — Context → Ask → Constraints
4. **Interview Method** — "Ask me one question at a time"
5. **Reference + Modify** — "Like X but with Y"

### Tier 2: Power 5
6. **Give 3 Options** — Force alternatives, avoid tunnel vision
7. **Comparison Matrix** — Side-by-side evaluation
8. **Critique Yourself** — Find problems before building
9. **5 Whys** — Drill to root cause
10. **Pre-Mortem** — "How could this fail?"

## Session 1's Key Insight

> "Every bad prompt, every retry, every 'that's not what I meant' stays in context and pollutes future responses."

This directly connects to [[context-rot]] — Session 2 explains the MECHANICS of why this happens.

## The Relationship

| | Prompt Engineering | [[context-engineering|Context Engineering]] |
|---|---|---|
| **Focus** | What you SAY | What AI SEES |
| **Scope** | Single message | Entire conversation + external data |
| **Session** | Session 1 | Session 2 |
| **Analogy** | How you ask a question | How you brief someone before they answer |

## Both Are Necessary

Great prompts with bad context = bad output.
Bad prompts with great context = mediocre output.
Great prompts WITH great context = excellent output.

## Techniques That Bridge Both

- **Constraint Sandwich** — Context section is a form of [[context-hydration]]
- **Interview Method** — Manages [[context-rot]] by going step-by-step
- **Reference + Modify** — Leverages [[static-context]] (shared knowledge)

---

**See also:** [[context-engineering]], [[context-rot]], [[the-email-test]]

#core-concept #session-1
