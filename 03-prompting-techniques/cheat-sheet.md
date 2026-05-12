# Prompting Cheat Sheet

**One page. Five techniques. Built for build time.**

---

## THE 4 LAYERS

### Layer 1 — V1: Just ask
Whatever you'd normally type. Almost always too vague.

### Layer 2 — V2: Role + Context + Task + Format

````
# Role
You are a senior product engineer...

# Context
- Business specifics
- Constraints
- Current state

# Task
The specific next step (not the whole app)

# Format
How the answer should come back
````

### Layer 3 — V3: Add Examples + Reasoning

Stack on top of V2:

````
# Examples
- Something similar that works (e.g., "booking flow on Acuity")
- Another reference

# Process
Before you write anything, think step-by-step about what
could break with this approach.
````

### Layer 4 — V4: XML Tags + Meta-Prompt

Wrap each section in tags:
````
<role>...</role>
<context>...</context>
<task>...</task>
<format>...</format>
<examples>...</examples>
````

Then **meta-prompt**:
````
Here's my prompt. What's missing? Rewrite it to get a
better result.
````
Run the AI's rewritten version.

---

## RESCUE MOVE — INTERVIEW TECHNIQUE

When you're stuck or vague:

````
I want to build [PROJECT]. Before we write anything,
interview me about my project. Ask one question at a
time. Wait for my answer. When you have enough,
summarize back and we'll start.
````

---

## AFTER V4 WORKS — 3 NEXT MOVES

1. **Iterate one section** — only update Context or Task, leave the rest. Cleaner deltas.
2. **Ask for variations** — "Give me 3 different approaches to [X]. Compare trade-offs."
3. **Ask AI to critique itself** — "What's wrong with what you just produced? How would you redo it?"

---

## ANTI-PATTERNS — DON'T

- "CRITICAL: YOU MUST..." — modern models get overcautious and refuse more
- Change 3 things at once when iterating — change one variable, test, then next
- Assume same prompt works in Claude and ChatGPT — they parse differently

---

Workshop assets: [Deployed URL placeholder — to be filled by QR target]
