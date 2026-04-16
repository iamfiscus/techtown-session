# Prompt Engineering Cheat Sheet
## TechTown Start Studio | January 2026

---

## The Golden Prompt

```
I want you to interview me one question at a time
about [WHAT YOU'RE BUILDING].

Give me an example of a response to make me think
and explain the technical terms in a non-technical way.
```

**Why it works:**
- AI asks the questions (you don't need to know what to ask)
- One at a time prevents overwhelm
- Examples help you understand what "good" looks like
- Technical terms get explained as you go

---

## The Workflow

```
┌──────────┐    ┌─────────────┐    ┌──────────┐    ┌─────────┐
│   PLAN   │ ─► │  INTERVIEW  │ ─► │   SPEC   │ ─► │  BUILD  │
│          │    │             │    │          │    │         │
│ Know what│    │ AI asks YOU │    │ Document │    │ Focused │
│ you want │    │ questions   │    │ emerges  │    │ prompt  │
│ (roughly)│    │             │    │          │    │         │
└──────────┘    └─────────────┘    └──────────┘    └─────────┘
    FREE            FREE           FREE/CHEAP        PAID
```

**Do planning in free tools. Build in paid tools.**

---

## Outcome vs Process Prompting

| Don't Do This (Outcome) | Do This (Process) |
|------------------------|-------------------|
| "Build me an e-commerce site" | "Interview me about my e-commerce requirements" |
| "Add user authentication" | "What questions should I answer before adding auth?" |
| "Make it better" | "What specific improvements would have the most impact?" |
| "Fix the bugs" | "Help me understand what's causing this behavior" |

**Outcome = Pray | Process = Plan**

---

## The Tool Ladder

| Level | Tool | Best For | Cost |
|-------|------|----------|------|
| 1 | ChatGPT / Claude / Gemini | Planning, interviews, specs | Free-ish |
| 2 | Lovable / Bolt | Quick prototypes, visual building | Credits |
| 3 | Cursor / Replit | Real development, more control | Subscription |
| 4 | Claude Code | Full autonomy, complex features | API costs |

**Start at Level 1. Graduate up over time.**

---

## Token Economics

**1 token ≈ 4 characters ≈ 0.75 words**

| What | Token Cost |
|------|------------|
| "Build me an app" | ~5 tokens |
| AI's confused response | ~500 tokens |
| Your clarification | ~100 tokens |
| AI's second attempt | ~500 tokens |
| **Wasted total** | **~1,100 tokens** |

**vs.**

| What | Token Cost |
|------|------------|
| Interview (free tool) | 0 paid tokens |
| Spec document | 0 paid tokens |
| Focused build prompt | ~50 tokens |
| AI builds correctly | ~500 tokens |
| **Efficient total** | **~550 tokens** |

---

## Useful Prompts

**To generate a spec from interview:**
```
Based on our conversation, create a specification
document I can use to build this feature. Include:
- Requirements
- User flow
- Edge cases
- Technical considerations
```

**To start building from spec:**
```
I'm adding [FEATURE] to my existing app.
Here's the specification: [PASTE SPEC]

Please implement this feature, starting with
[SPECIFIC COMPONENT].
```

**To debug issues:**
```
This isn't working as expected. Here's what I see:
[DESCRIBE PROBLEM]

Here's what I expected:
[DESCRIBE EXPECTATION]

Help me understand what might be causing this.
```

---

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Too vague | Add specific details and constraints |
| Too much at once | Break into smaller pieces |
| No context | Explain your app, users, and goals |
| Expecting perfection | Iterate and refine |
| Fighting the AI | Work with it, clarify, guide |

---

## Key Terms

| Term | Plain English |
|------|---------------|
| **Token** | A chunk of text (~4 characters) that costs money |
| **Context window** | AI's "memory" - how much it can hold at once |
| **Prompt** | Your instructions to the AI |
| **System prompt** | Hidden instructions the tool gives the AI |
| **Temperature** | Randomness setting (low = predictable, high = creative) |
| **Spec** | A document describing what to build |

---

## Quick Reference

**Before you prompt, ask yourself:**
- [ ] Do I know what feature I'm building?
- [ ] Have I been interviewed about the details?
- [ ] Do I have a spec document?
- [ ] Am I asking for ONE thing, not everything?

**If something goes wrong:**
1. Don't blame the AI
2. Clarify what you meant
3. Provide more context
4. Break it into smaller pieces
5. Try a different approach

---

## Resources

- **TechTown Start Studio**: [Your mentors and support]
- **ChatGPT**: chat.openai.com (free tier available)
- **Claude**: claude.ai (free tier available)
- **Lovable**: lovable.dev

---

*Don't pray. Plan.*
