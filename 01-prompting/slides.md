# Prompting Methods for Founders
## 15 Techniques That Actually Work

**JD Fiscus | TechTown Start Studio | January 2026**

---

## Slide 2: The Problem — Sound Familiar?

| 3 | 10+ | $47 | 0 |
|---|-----|-----|---|
| Hours Wasted | Retry Attempts | Burned in Credits | Usable Output |

> "Why won't it just do what I want?"

---

## Slide 3: The AI Lifecycle

**How AI Actually Works**

1. **You Type** — Your prompt
2. **Tokenized** — Text → numbers
3. **Processed** — Model thinks
4. **Response** — Token by token

> AI doesn't "understand" — it predicts the next most likely token

---

## Slide 4: What Are Tokens?

**Your Text:** `Build me a landing page`

**AI Sees Tokens:** `[Build]` `[me]` `[a]` `[land]` `[ing]` `[page]`

| ~4 | 100k–200k | $$$ |
|----|-----------|-----|
| Chars per token | Context window | You pay per token |

More tokens = more cost + slower responses + less room for context

---

## Slide 5: The Message Queue

AI sees your conversation as a structured list:

| Role | Description |
|------|-------------|
| **SYSTEM** | "You are a helpful coding assistant..." (hidden instructions) |
| **USER** | "Build me a landing page with..." |
| **ASSISTANT** | "I'll create that for you. Here's the code..." |
| **TOOL** | [File written] [Command executed] [Screenshot taken] |
| **USER** | "Now add a contact form..." |

> Each message adds to the context window — AI reads ALL of this every turn

---

## Slide 6: Why Planning Matters

### Without Planning
`[Bad prompts 40%] [Retries 35%] [Work 25%]`
Context full of mistakes & confusion

### With Planning
`[Clear spec 15%] [Productive work 85%]`
Clean context = better results

> **The Key Insight:** Every bad prompt, every retry, every "that's not what I meant" **stays in context** and pollutes future responses.

---

## Slide 7: What You'll Learn

- **Core 5 Methods** — The foundation every founder needs
- **5 Power Methods** — Level up your prompting game
- **Before/After Examples** — See the difference in action
- **Live Practice** — Apply these to your own projects

---

## Slide 8: Two Tiers of Techniques

| Tier 1: Core 5 | Tier 2: Power 5 |
|-----------------|------------------|
| 1. Markdown Headers | 6. Give 3 Options |
| 2. ALL CAPS for Constraints | 7. Comparison Matrix |
| 3. Constraint Sandwich | 8. Critique Yourself |
| 4. Interview Method | 9. 5 Whys |
| 5. Reference + Modify | 10. Pre-Mortem |

> Master these 10 and you'll outprompt 90% of users

---

# TIER 1: The Core 5 Methods

*Master these first — they work every time*

---

## Method 1: Markdown Headers

**Create visual hierarchy with # symbols**

> **Why it works:** AI models are trained on millions of markdown documents. Headers signal "this is a new section" and "this is important." It forces YOU to organize your thinking.

- `# Main Title` — Top-level heading
- `## Section` — Major sections
- `### Subsection` — Details within sections

### Before & After

**BEFORE — Wall of Text:**
```
I need a landing page with a hero section and it should have a headline and subheadline and a CTA button and also a features section with 3 features and each feature should have an icon and title and description and also a pricing section with 3 tiers
```

**AFTER — Structured:**
```markdown
# Landing Page

## Hero Section
- Headline: "Ship faster with AI"
- Subheadline: "Build apps in hours"
- CTA button: "Start Free Trial"

## Features Section
3 features, each with icon, title, description

## Pricing Section
3 tiers: Free, Pro, Enterprise
```

**Key principle:** One concept per header. If you're cramming multiple ideas under one header, split them.

---

## Method 2: ALL CAPS for Constraints

**Signal non-negotiable requirements**

> **Why it works:** In a sea of lowercase text, ALL CAPS stands out. AI models weight emphasized text more heavily. Use for things the AI might otherwise ignore.

- **MUST** — Required behavior
- **NEVER** — Forbidden actions
- **ALWAYS** — Consistent rules
- **IMPORTANT** — Critical notes

**Warning:** Don't overuse. If everything is ALL CAPS, nothing is. Reserve for 2–4 critical items max.

### Before & After

**BEFORE — Easy to Miss:**
```
Build a contact form. Make sure it validates email addresses and please don't let users submit without filling required fields.
```
AI might skip validation, allow empty submissions

**AFTER — Crystal Clear:**
```
Build a contact form.

REQUIRED:
- Email field MUST validate format
- NEVER allow empty required fields
- ALWAYS show inline error messages

IMPORTANT: Form must work on mobile
```
Constraints are impossible to miss

---

## Method 3: Constraint Sandwich

**Context — Ask — Constraints**

```
CONTEXT → ASK → CONSTRAINTS
(What exists, who it's for) → (The specific request) → (Limits and requirements)
```

> **Why it works:** AI needs context to make good decisions. The "sandwich" ensures it knows the situation before acting, then respects your limits.

### Before & After

**BEFORE — No Context:**
```
Add a search bar
```
AI doesn't know: What kind of app? What to search? How should it look?

**AFTER — Full Context:**
```markdown
## Context
E-commerce site built with React. Product catalog has 500+ items in Supabase.

## Request
Add a search bar to the header that filters products by name.

## Constraints
- MUST debounce input (300ms delay)
- Search should be case-insensitive
- Show "No results" state when empty
- DO NOT make API call on every keystroke
```

---

## Method 4: Interview Method

**Conversation beats mega-prompts**

> **Why it works:** You can course-correct early. AI can ask clarifying questions. Less overwhelming for complex features. Catches misunderstandings before they compound.

| Mega-Prompt Risk | Interview Benefits |
|------------------|-------------------|
| All-or-nothing | Iterative refinement |
| Hidden assumptions | Early course correction |
| Expensive mistakes | YOU stay in control |

### Before & After

**BEFORE — Mega-Prompt (Risky):**
```
Build me a complete user authentication system with email/password login, Google OAuth, password reset via email, remember me checkbox, rate limiting on failed attempts, session management, and a profile page where users can update their info and change password.
```

**AFTER — Interview Approach:**
```
Turn 1: "I need user authentication. Let's start with basic email/password. What do you need to know?"
Turn 2: AI asks questions, you answer
Turn 3: "Good, now let's add Google OAuth"
Turn 4: "Now add password reset"
Turn 5: "Finally, add a profile page"
```

### The Interview Prompt (Screenshot This!)

> **I want you to interview me one question at a time about [WHAT YOU'RE BUILDING]. Give me an example of a response to make me think and explain the technical terms in a non-technical way.**

**This one prompt will save you hours.**

---

## Method 5: Reference + Modify

**"Like X but with Y"**

> **Why it works:** A reference is worth 1000 words. Instead of describing from scratch, you leverage shared understanding. AI knows what Stripe's pricing page looks like.

**What you can reference:** Famous websites, competitor sites, design systems, your own screenshots

**Examples:** "Like Linear's homepage" | "Similar to Notion's sidebar" | "Use shadcn/ui style"

### Before & After

**BEFORE — Vague Description:**
```
Build a pricing page with modern design, good typography, a professional look, three columns for different tiers, toggle for monthly/annual billing...
```
"Modern" and "professional" mean different things to everyone

**AFTER — Clear Reference:**
```
Build a pricing page like Stripe's pricing page, but with:
- Only 2 tiers instead of 3
- Our brand colors: #2563EB, #7C3AED
- No enterprise "Contact us" tier
- Add a FAQ section below cards
```
AI knows exactly what you're aiming for

---

## Core 5 Recap

| # | Method | Key Phrase |
|---|--------|-----------|
| 1 | Markdown Headers | `# Section ## Subsection` |
| 2 | ALL CAPS | `MUST, NEVER, REQUIRED` |
| 3 | Constraint Sandwich | Context — Ask — Constraints |
| 4 | Interview Method | "Ask me one question at a time" |
| 5 | Reference + Modify | "Like X but with Y" |

> Use these 5 on **every single prompt**

---

# TIER 2: The Power 5 Methods

*Level up with these advanced techniques*

---

## Method 6: Give Me 3 Options

**Force alternatives, avoid tunnel vision**

> **Why it works:** Avoids tunnel vision on the first idea. Reveals tradeoffs you didn't know existed. YOU make the choice, AI provides options. Often surfaces a better approach.

- **Option A** — Simple / Quick
- **Option B** — Balanced
- **Option C** — Production-Ready

### Before & After

**BEFORE — Single Answer:**
```
How should I structure my database for a todo app?
```
AI gives ONE answer. You don't know if there are better options.

**AFTER — Multiple Options:**
```
Give me 3 different ways to structure the database for a todo app.

For each option:
- Show the schema
- Pros and cons
- When you'd choose this approach
```
Now YOU can compare and choose wisely

**Variations:** "Simple vs. complex version" | "Quick-and-dirty vs. production-ready" | "Beginner vs. expert approach"

---

## Method 7: Comparison Matrix

**Side-by-side evaluation in a table**

> **Why it works:** Forces systematic comparison. Easy to scan and compare. Reveals which option wins on which criteria. Makes decision rationale transparent.

**Perfect for:**
- Choosing between tools or services
- Evaluating architecture options
- Comparing pricing strategies
- Any decision with multiple factors

### Example

```
I'm choosing between Supabase, Firebase, and PlanetScale for my database.

Create a comparison matrix with these criteria:
- Ease of setup
- Pricing for small scale
- Real-time capabilities
- SQL vs NoSQL
- Auth built-in
- Free tier limits

Format as a table with ratings (Good/Medium/Poor) for each.
```

| Criteria | Supabase | Firebase | PlanetScale |
|----------|----------|----------|-------------|
| Ease of setup | Good | Good | Medium |
| Real-time | Good | Good | Poor |

---

## Method 8: Critique Yourself First

**Ask AI to find problems BEFORE you implement**

> **Why it works:** Catches issues before you build. AI knows weaknesses but won't mention them unless asked. Builds your critical thinking. Cheaper to fix problems in planning than in code.

- **Use it when:** After getting a solution, before implementing it
- **What to ask for:** Weaknesses, edge cases, what could break, senior engineer pushback

### The Prompt

```
Before we implement this, critique your own solution:
- What are the weaknesses?
- What edge cases might break this?
- What would a senior engineer push back on?
- What's the biggest risk?
```

Or after getting a solution:

```
You just suggested [X approach].

Now argue against it. What's wrong with this approach?
What would you do differently if you had more time?
```

---

## Method 9: 5 Whys

**Drill down to root cause**

> **Why it works:** Surfaces the REAL problem, not symptoms. Prevents fixing the wrong thing. Simple but powerful debugging technique. Works for technical AND product problems.

**The method:** Keep asking "Why?" until you reach the root cause (usually 5 times).

### Technical Example

| Step | Finding |
|------|---------|
| **Problem** | The page is slow |
| **Why 1?** | The API call takes 3 seconds |
| **Why 2?** | We're fetching all 10,000 products |
| **Why 3?** | There's no pagination |
| **Why 4?** | We didn't think the catalog would grow this big |
| **Root Cause** | **No scale requirements defined upfront. Fix: Add pagination.** |

### Product Example

| Step | Finding |
|------|---------|
| **Problem** | Users aren't completing onboarding |
| **Why 1?** | They drop off at step 3 |
| **Why 2?** | Step 3 asks for credit card |
| **Why 3?** | We require payment upfront |
| **Why 4?** | We assumed it would reduce tire-kickers |
| **Root Cause** | **Never tested free trial vs. paid upfront. Fix: Test free trial model.** |

---

## Method 10: Pre-Mortem

**"How could this fail?"**

> **Why it works:** Easier to spot risks when you assume failure happened. Overcomes optimism bias. Surfaces concerns people are hesitant to voice. Creates actionable prevention list.

**The technique:** Imagine it's 3 months from now and this feature completely failed. What went wrong?

### The Prompt

```
Imagine it's 3 months from now and this feature completely failed.
Users hate it, it's full of bugs, we had to roll it back.

What went wrong? List the 5 most likely causes of failure.
```

Then follow up:

```
For each failure cause, what could we do NOW to prevent it?
```

### Example Output

| Potential Failure | Prevention |
|-------------------|------------|
| Performance — didn't handle scale | Load test with 10x expected users |
| Edge cases — broke for certain users | Define and test edge cases upfront |
| Scope creep — took 3x longer | Lock scope, cut features aggressively |
| User confusion — too complex | User testing before full build |
| Integration issues — broke other features | Integration tests, staged rollout |

> Now you have a **risk mitigation checklist** before you start

---

## Power 5 Recap

| # | Method | When to Use |
|---|--------|-------------|
| 6 | Give 3 Options | Decision points, architecture choices |
| 7 | Comparison Matrix | Evaluating tools, services, approaches |
| 8 | Critique Yourself | Before implementing any solution |
| 9 | 5 Whys | Debugging, root cause analysis |
| 10 | Pre-Mortem | Risk planning, before major builds |

---

# PUTTING IT TOGETHER: The Complete Workflow

---

## The Workflow That Works

```
PLAN (Free) → INTERVIEW (Free) → SPEC (Free) → BUILD (Paid)
(What do I want?)  (AI asks YOU)  (Document emerges)  (One focused prompt)
```

> Plan for **free**, build with **confidence**

---

## Powerful Combinations

| Scenario | Methods |
|----------|---------|
| **Planning a Feature** | Interview Method + Pre-Mortem + Constraint Sandwich |
| **Choosing Architecture** | Give 3 Options + Comparison Matrix + Critique Yourself |
| **Debugging Issues** | 5 Whys + Explain Before Fixing + ALL CAPS |
| **Building UI** | Reference + Modify + Markdown Headers + Screenshots |

---

## Quick Reference Card

| Method | When to Use | Key Phrase |
|--------|-------------|-----------|
| Markdown Headers | Always for structure | `# Section` |
| ALL CAPS | Critical constraints | `MUST, NEVER` |
| Constraint Sandwich | Every request | Context — Ask — Constraints |
| Interview Method | Complex features | "Ask me one question..." |
| Reference + Modify | UI/design work | "Like X but with Y" |
| Give 3 Options | Decisions | "Show me 3 ways..." |
| Comparison Matrix | Evaluating choices | "Create a table comparing..." |
| Critique Yourself | Before implementing | "What's wrong with this?" |
| 5 Whys | Root cause | "Why? Why? Why?..." |
| Pre-Mortem | Risk planning | "How could this fail?" |

---

## Common Mistakes to Avoid

- **Too vague:** "Make it better" → Use Constraint Sandwich
- **Too much at once:** "Build everything" → Use Interview Method
- **No context:** "Add a button" → Use Reference + Modify
- **No alternatives:** Accept first answer → Use Give 3 Options
- **No validation:** Build immediately → Use Critique Yourself

---

## Your Homework

1. **Today:** Pick ONE feature you need to build
2. **This week:** Use the Interview Prompt to create a spec
3. **Next time:** Apply Critique Yourself before building

> **I want you to interview me one question at a time about [YOUR FEATURE]. Give me an example of a response to make me think and explain the technical terms in a non-technical way.**

---

## Q&A

*What questions do you have?*

---

## Thank You

**JD Fiscus**
TechTown Start Studio

*Don't pray. Plan.*

---

# Bonus Methods

---

## Bonus: Numbered Steps

**For sequential processes, use explicit ordering**

**BEFORE:**
```
The checkout flow should collect shipping info, show order summary, process payment, and send confirmation email.
```

**AFTER:**
```
Checkout flow — exact order:

1. Shipping info form
2. Order summary with totals
3. Payment form (Stripe)
4. Processing spinner
5. Success page with order #
6. Trigger confirmation email
```

---

## Bonus: Chunking

**One feature per message**

**BEFORE:**
```
Add user authentication, a dashboard with charts, notification system, and dark mode toggle.
```

**AFTER:**
```
Message 1: "Add user auth"     → [verify it works]
Message 2: "Add dashboard page" → [verify it works]
Message 3: "Add line chart"     → [verify it works]
Message 4: "Add dark mode toggle" → [verify it works]
```

**Rule of thumb:** If you're using "and" more than twice, you're bundling too much.

---

## Bonus: Explain Before Fixing

**For debugging — diagnose before prescribing**

**BEFORE:**
```
[paste error]
Fix this
```

**AFTER:**
```
[paste error]

Before you fix this:
1. Explain what's causing this error
2. Why might this be happening?
3. Then show me the fix
```

**Even better:** "What are the 3 most likely causes? Which one applies to my situation?"

---

## Bonus: Screenshot as Input

**A picture is worth 1000 words of description**

**What to screenshot:**
- Figma mockups
- Competitor sites to emulate
- Current app state
- Error screens

**How to use:** "Build a layout like this screenshot, but with: [your changes]"

> Visual information is **dense** — use it!

---

## Bonus: Role Assignment

**"Act as..." for specialized perspectives**

- **Security Review:** "Act as a security engineer. What vulnerabilities do you see?"
- **UX Critique:** "Act as a UX designer. How can this flow be simpler?"
- **User Perspective:** "Act as a first-time user. Walk through this."

**Combine:** "Review from 3 perspectives: first-time user, power user, and developer maintaining this code."

---

## Resources & Next Steps

**TechTown Support:**
- Start Studio mentors available
- Office hours TBD
- Follow-up sessions

[QR Code — Scan for cheat sheet]
