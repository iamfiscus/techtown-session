# The Prompt Engineering Workflow
## Plan → Interview → Spec → Build

---

## Visual Diagram (ASCII)

```
╔═══════════════════════════════════════════════════════════════════════════╗
║                     THE PROMPT ENGINEERING WORKFLOW                        ║
╠═══════════════════════════════════════════════════════════════════════════╣
║                                                                           ║
║   ┌─────────────┐     ┌─────────────┐     ┌─────────────┐     ┌─────────┐ ║
║   │             │     │             │     │             │     │         │ ║
║   │    PLAN     │────►│  INTERVIEW  │────►│    SPEC     │────►│  BUILD  │ ║
║   │             │     │             │     │             │     │         │ ║
║   └─────────────┘     └─────────────┘     └─────────────┘     └─────────┘ ║
║         │                   │                   │                   │     ║
║         ▼                   ▼                   ▼                   ▼     ║
║   ┌─────────────┐     ┌─────────────┐     ┌─────────────┐     ┌─────────┐ ║
║   │ Know what   │     │ AI asks YOU │     │ Document    │     │ Focused │ ║
║   │ you want    │     │ questions   │     │ emerges     │     │ prompt  │ ║
║   │ (roughly)   │     │             │     │             │     │         │ ║
║   └─────────────┘     └─────────────┘     └─────────────┘     └─────────┘ ║
║         │                   │                   │                   │     ║
║         ▼                   ▼                   ▼                   ▼     ║
║   ┌─────────────┐     ┌─────────────┐     ┌─────────────┐     ┌─────────┐ ║
║   │    FREE     │     │    FREE     │     │ FREE/CHEAP  │     │  PAID   │ ║
║   │  (your      │     │  (ChatGPT,  │     │  (ChatGPT,  │     │(Lovable,│ ║
║   │   brain)    │     │   Claude)   │     │   Claude)   │     │ Cursor) │ ║
║   └─────────────┘     └─────────────┘     └─────────────┘     └─────────┘ ║
║                                                                           ║
╚═══════════════════════════════════════════════════════════════════════════╝
```

---

## Step-by-Step Breakdown

### Step 1: PLAN (2 minutes)
**Tool:** Your brain
**Cost:** Free

Before touching any AI tool, answer:
- What feature am I building?
- Who is it for?
- What's the core function?

**Example:**
> "I want to add a partner invite feature to my pregnancy app so expecting mothers can share their journey with their partners."

*You don't need details yet. Just direction.*

---

### Step 2: INTERVIEW (15-20 minutes)
**Tool:** ChatGPT, Claude, or Gemini
**Cost:** Free

Use the golden prompt:
```
I want you to interview me one question at a time
about [YOUR FEATURE].

Give me an example of a response to make me think
and explain the technical terms in a non-technical way.
```

**What happens:**
- AI asks smart questions you wouldn't think of
- You provide context only YOU know
- Details emerge naturally through conversation
- You learn terminology as you go

**Example questions AI might ask:**
- How does a user send an invite?
- What can the partner see vs. not see?
- What happens if they break up?
- Email or phone invite?
- Does partner need an account?

---

### Step 3: SPEC (5 minutes)
**Tool:** Same ChatGPT/Claude conversation
**Cost:** Free

After the interview, ask:
```
Based on our conversation, create a specification
document I can use to build this feature. Include:
- Requirements
- User flow
- Permissions model
- Edge cases
```

**What you get:**
A structured document that captures everything from the interview in a format ready for building.

---

### Step 4: BUILD (varies)
**Tool:** Lovable, Cursor, Claude Code
**Cost:** Paid (but efficient!)

Take your spec to your building tool:
```
I'm adding a partner invite feature to my existing app.
Here's the specification: [PASTE SPEC]

Please implement this feature, starting with the
invite UI component.
```

**Why this works:**
- AI has full context from your spec
- No guessing, no confusion
- Builds what YOU actually need
- Fewer iterations, less cost

---

## The Math

### Without the workflow:
```
Vague prompt           →  5 tokens
Confused AI response   →  500 tokens
Your clarification     →  100 tokens
Still confused         →  500 tokens
More clarification     →  200 tokens
Wrong output           →  800 tokens
Starting over          →  1000+ tokens
────────────────────────────────────
TOTAL: 3,000+ tokens of waste
```

### With the workflow:
```
Interview (free)       →  0 paid tokens
Spec (free)            →  0 paid tokens
Focused build prompt   →  50 tokens
Correct output         →  500 tokens
────────────────────────────────────
TOTAL: ~550 tokens (efficient!)
```

---

## Common Questions

**Q: Can I skip the interview if I know what I want?**
A: You think you know. The interview uncovers details you forgot. Do the interview.

**Q: What if the AI asks something I don't know?**
A: Say "I don't know" or "What would you recommend?" The AI will help you decide.

**Q: How long should the interview be?**
A: Until you feel like the AI understands your feature. Usually 10-15 questions.

**Q: Can I do this in Lovable directly?**
A: You can, but you're paying for planning. Do planning in free tools.

---

## Slide-Ready Version

For presentations, use this simplified visual:

```
    PLAN          INTERVIEW         SPEC           BUILD
      │               │               │               │
      ▼               ▼               ▼               ▼
  ┌───────┐      ┌───────┐      ┌───────┐      ┌───────┐
  │ What  │  ──► │  AI   │  ──► │ Your  │  ──► │ One   │
  │ do I  │      │ asks  │      │ blue- │      │ clear │
  │ want? │      │ YOU   │      │ print │      │ build │
  └───────┘      └───────┘      └───────┘      └───────┘
     FREE          FREE        FREE/CHEAP        PAID
```

---

*TechTown Start Studio | January 2026*
