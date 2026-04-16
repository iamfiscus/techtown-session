# Brainstorm: Prompting Methods for Non-Technical Founders

## Problem Statement
What prompting techniques should be taught to non-technical founders using AI coding tools like Lovable?

---

## Diverge: 68 Prompting Methods

### Visual Formatting (7)
1. Markdown headers (# ## ###) for structure
2. ALL CAPS for critical constraints (MUST, NEVER, IMPORTANT)
3. Bullet points for requirements lists
4. Numbered lists for sequential steps
5. Code blocks for technical specs
6. Bold for emphasis on key terms
7. Horizontal rules to separate sections

### Structural Templates (8)
8. Constraint sandwich: Context → Ask → Constraints
9. PREP framework: Purpose, Requirements, Examples, Preferences
10. CAF pattern: Context, Action, Format
11. User story format: "As a [user], I want [feature] so that [benefit]"
12. Acceptance criteria checklist format
13. Reference + Modify: "Like [example] but with [changes]"
14. Phased approach: Phase 1, Phase 2, Phase 3
15. Vertical slice: one complete feature at a time

### Conversation Patterns (6)
16. Interview method: back-and-forth vs. single mega-prompt
17. Start broad, then narrow
18. "Yes, and..." iterative refinement
19. Spot fix: "Keep X, but change Y"
20. Explain before fixing: "Why is this happening?"
21. Chunk requests: one feature per message

### Emphasis & Prioritization (5)
22. CRITICAL / IMPORTANT / NICE-TO-HAVE tiers
23. "DO NOT" for hard constraints
24. "ALWAYS" / "NEVER" for rules
25. Priority numbering (P0, P1, P2)
26. Must-have vs. nice-to-have sections

### Context-Setting (6)
27. State current tech stack upfront
28. Describe what already exists
29. Share file paths / component names
30. Explain the "why" behind requests
31. Reference previous conversation context
32. Describe the user/audience

### Describing Without Technical Knowledge (5)
33. Screenshot/mockup as prompt input
34. "Make it look like [famous site]"
35. Natural language UI descriptions
36. Behavior-first descriptions ("when user clicks...")
37. Analogy-based: "Like Uber but for dog walking"

### Error Handling Prompts (4)
38. Paste full error message + "explain and fix"
39. "What could cause this?" before "fix it"
40. "Show me 3 possible causes"
41. Include what you already tried

### Meta-Prompting (4)
42. Ask AI to ask you clarifying questions
43. "What information do you need from me?"
44. "Critique this prompt and improve it"
45. "Break this into smaller tasks"

### Reasoning & Analysis Frameworks (6)
46. **5 Whys** - drill to root cause ("Why? Why? Why? Why? Why?")
47. **Pros/Cons list** - force tradeoff analysis
48. **Comparison matrix table** - evaluate options side-by-side
49. **First principles** - "What's the simplest version of this?"
50. **Rubber duck** - explain the problem back to get unstuck
51. **Decision criteria** - "Evaluate against these factors: X, Y, Z"

### Self-Correction Frameworks (5)
52. **Critique yourself first** - "What's wrong with this approach before we proceed?"
53. **Devil's advocate** - "Argue against this solution"
54. **Pre-mortem** - "Imagine this failed. What went wrong?"
55. **Steelman** - "What's the strongest version of this idea?"
56. **Assumption surfacing** - "What assumptions are you making here?"

### Exploration Frameworks (5)
57. **Give me 3 options** - force alternatives instead of single answer
58. **Explore the solution space** - "What are ALL the ways to solve this?"
59. **Best case / worst case** - bracket the possible outcomes
60. **Edge cases** - "What happens if [unusual input]?"
61. **Boundary testing** - "What are the limits of this approach?"

### Structured Output Requests (4)
62. **Chain of thought** - "Think step by step"
63. **Show your work** - "Explain your reasoning"
64. **Confidence levels** - "How sure are you? What would change your answer?"
65. **Cite sources** - "Where does this pattern come from?"

### Personas & Perspectives (4)
66. **Role assignment** - "Act as a senior engineer reviewing this"
67. **Audience shift** - "Explain to a 5-year-old / to a CTO"
68. **Multiple experts** - "What would security expert vs. UX designer say?"
69. **User perspective** - "Walk through this as a first-time user"

### Iteration Frameworks (4)
70. **Zoom in / zoom out** - change abstraction level
71. **Version this** - "Give me v1, v2, v3 with increasing complexity"
72. **Incremental enhancement** - "Now add [one thing] to this"
73. **Simplify challenge** - "Now do this in half the code"

---

## Cluster: 8 Themes

| # | Cluster | Count | Methods |
|---|---------|-------|---------|
| 1 | **Visual Formatting** | 7 | Markdown headers, ALL CAPS, bullets, numbered lists, code blocks, bold, horizontal rules |
| 2 | **Structural Templates** | 8 | Constraint sandwich, PREP, CAF, user stories, acceptance criteria, reference+modify, phased approach, vertical slices |
| 3 | **Conversation Flow** | 6 | Interview method, start broad→narrow, "yes and", spot fix, explain before fix, chunking |
| 4 | **Emphasis Signals** | 5 | CRITICAL/IMPORTANT tiers, DO NOT, ALWAYS/NEVER, priority numbers, must-have sections |
| 5 | **Context Loading** | 11 | Tech stack, what exists, file paths, the "why", screenshots, analogies, behavior descriptions, audience, user perspective |
| 6 | **Debug & Error Handling** | 4 | Paste full error, ask causes, show 3 causes, include what tried |
| 7 | **Reasoning & Analysis** | 11 | 5 Whys, pros/cons, comparison matrix, first principles, rubber duck, decision criteria, assumption surfacing, edge cases, boundary testing, best/worst case, explore solution space |
| 8 | **Self-Correction & Critique** | 9 | Critique yourself, devil's advocate, pre-mortem, steelman, give 3 options, chain of thought, show work, confidence levels, meta-prompting |
| 9 | **Personas & Output Control** | 8 | Role assignment, audience shift, multiple experts, cite sources, version this, zoom in/out, incremental, simplify |

---

## Converge: Prioritized Methods

### Tier 1 - Must Teach (Core 5)
| Method | Why Essential |
|--------|---------------|
| 1. Markdown headers | Instant structure, AI parses it well |
| 2. ALL CAPS for constraints | Draws attention to critical requirements |
| 3. Constraint sandwich | Context → Ask → Constraints works every time |
| 4. Interview method | Conversation beats mega-prompts |
| 5. Reference + Modify | "Like X but Y" saves 1000 words |

### Tier 2 - High Value (Next 10)
| Method | Why Valuable |
|--------|--------------|
| 6. Numbered steps | Sequences need explicit order |
| 7. "Explain before fixing" | Learn while debugging |
| 8. Screenshot as input | Visual > verbal for UI |
| 9. Paste full error | Details matter for debugging |
| 10. Chunking | One feature at a time = fewer errors |
| 11. Give me 3 options | Forces alternatives, avoids tunnel vision |
| 12. Comparison matrix | Side-by-side evaluation |
| 13. Critique yourself first | Catches problems before building |
| 14. 5 Whys | Gets to root cause |
| 15. Pre-mortem | "How could this fail?" |

### Tier 3 - Advanced (Power Users)
| Method | When to Use |
|--------|-------------|
| 16. Ask AI to ask questions | Unclear requirements |
| 17. Phased approach | Large features |
| 18. Acceptance criteria | Definition of done |
| 19. Role assignment | "Act as senior engineer" |
| 20. Chain of thought | Complex logic |
| 21. Steelman | Strengthen weak ideas |
| 22. Version this (v1, v2, v3) | Incremental complexity |
| 23. First principles | Simplify over-engineered solutions |
| 24. Confidence levels | Gauge certainty |

---

## Deep Dive: All Methods Explained

---

# TIER 1: FOUNDATIONAL METHODS

---

## 1. Markdown Headers (# ## ###)

**What it is**: Using hashtags to create visual hierarchy in your prompts.

**Why it works**: AI models are trained on millions of markdown documents. Headers signal "this is a new section" and "this is important." It forces YOU to organize your thinking.

**Bad example**:
```
I need a landing page with a hero section and it should have a headline
and subheadline and a CTA button and also a features section with 3
features and each feature should have an icon and title and description
and also a pricing section with 3 tiers
```

**Good example**:
```
# Landing Page

## Hero Section
- Headline: "Ship faster with AI"
- Subheadline: "Build apps in hours, not months"
- CTA button: "Start Free Trial"

## Features Section
3 features, each with:
- Icon
- Title
- Short description

## Pricing Section
3 tiers: Free, Pro, Enterprise
```

**Key principle**: One concept per header. If you're cramming multiple ideas under one header, split them.

---

## 2. ALL CAPS for Critical Constraints

**What it is**: Using capital letters to signal non-negotiable requirements.

**Why it works**: Draws attention. In a sea of lowercase text, ALL CAPS stands out. AI models weight emphasized text more heavily.

**When to use**:
- Hard technical requirements
- Things that MUST happen
- Things that must NEVER happen
- Constraints the AI might otherwise ignore

**Bad example**:
```
Build a contact form. Make sure it validates email addresses
and please don't let users submit without filling required fields.
```

**Good example**:
```
Build a contact form.

REQUIRED:
- Email field MUST validate format before submit
- NEVER allow empty required fields to submit
- ALWAYS show inline error messages

IMPORTANT: Form must work on mobile
```

**Warning**: Don't overuse. If everything is ALL CAPS, nothing is. Reserve for 2-4 critical items max.

---

## 3. Constraint Sandwich (Context → Ask → Constraints)

**What it is**: A three-part structure that front-loads context, makes a clear ask, then adds boundaries.

**Why it works**: AI needs context to make good decisions. The "sandwich" ensures it knows the situation before acting, then respects your limits.

**The pattern**:
```
## Context
[What exists, what you're building, who it's for]

## Request
[The specific thing you want built]

## Constraints
[Limits, requirements, things to avoid]
```

**Bad example**:
```
Add a search bar
```

**Good example**:
```
## Context
I have an e-commerce site built with React. The product catalog
has 500+ items stored in Supabase.

## Request
Add a search bar to the header that filters products by name.

## Constraints
- MUST debounce input (300ms delay)
- Search should be case-insensitive
- Show "No results" state when empty
- DO NOT make a new API call on every keystroke
```

---

## 4. Interview Method (Conversation vs. Mega-Prompt)

**What it is**: Building features through back-and-forth dialogue instead of one massive prompt.

**Why it works**:
- You can course-correct early
- AI can ask clarifying questions
- Less overwhelming for complex features
- Catches misunderstandings before they compound

**Mega-prompt approach** (risky):
```
Build me a complete user authentication system with email/password
login, Google OAuth, password reset via email, remember me checkbox,
rate limiting on failed attempts, session management, and a profile
page where users can update their info and change their password.
```

**Interview approach** (safer):
```
Turn 1: "I need user authentication. Let's start with basic
        email/password login. What do you need to know?"

Turn 2: AI asks questions, you answer

Turn 3: "Good, now let's add Google OAuth"

Turn 4: "Now add password reset via email"

Turn 5: "Finally, add a profile page for updating info"
```

**When to use mega-prompts**: Simple, well-defined tasks with no ambiguity.

**When to use interview method**: Anything with multiple components, unclear requirements, or room for interpretation.

---

## 5. Reference + Modify ("Like X but with Y")

**What it is**: Pointing to something that exists and describing how yours should differ.

**Why it works**: A picture (or reference) is worth 1000 words. Instead of describing from scratch, you leverage shared understanding.

**Bad example**:
```
Build a pricing page with modern design, good typography,
a professional look, three columns for different tiers,
toggle for monthly/annual billing...
```

**Good example**:
```
Build a pricing page like Stripe's pricing page, but with:
- Only 2 tiers instead of 3
- Our brand colors: primary #2563EB, secondary #7C3AED
- No enterprise "Contact us" tier
- Add a FAQ section below the pricing cards
```

**What you can reference**:
- Famous websites ("like Linear's homepage")
- Competitors ("similar to Notion's sidebar")
- Design systems ("use shadcn/ui style")
- Your own screenshots ("match the attached mockup")

---

# TIER 2: HIGH VALUE METHODS

---

## 6. Numbered Steps for Sequences

**What it is**: Using explicit 1, 2, 3 ordering for multi-step processes.

**Why it works**: Removes ambiguity about order. AI knows exactly what happens first, second, third.

**Bad example**:
```
The checkout flow should collect shipping info, show order summary,
process payment, and send confirmation email.
```

**Good example**:
```
Checkout flow - steps in exact order:

1. Shipping info form (name, address, phone)
2. Order summary with item list and totals
3. Payment form (Stripe integration)
4. Processing spinner while payment confirms
5. Success page with order number
6. Trigger confirmation email (background)
```

**Bonus**: Numbered steps make it easy to reference later: "Step 3 isn't working" is clearer than "the payment part is broken."

---

## 7. "Explain Before Fixing" for Debugging

**What it is**: Asking AI to diagnose before it prescribes.

**Why it works**:
- Forces AI to reason through the problem
- You learn what went wrong (not just get a fix)
- Catches cases where AI might apply wrong fix
- Builds your debugging intuition over time

**Bad approach**:
```
[paste error]
Fix this
```

**Good approach**:
```
[paste error]

Before you fix this:
1. Explain what's causing this error
2. Why might this be happening in my code?
3. Then show me the fix
```

**Even better**:
```
[paste error]

What are the 3 most likely causes of this error?
Then tell me which one applies to my situation.
```

---

## 8. Screenshot/Mockup as Input

**What it is**: Attaching images to your prompts instead of (or alongside) text descriptions.

**Why it works**: Visual information is dense. A screenshot communicates layout, spacing, colors, and relationships that would take paragraphs to describe.

**What to screenshot**:
- Figma/design mockups
- Competitor sites you want to emulate
- Current state of your app (to show what exists)
- Error screens
- Mobile vs. desktop views

**How to use**:
```
[Attached: screenshot of Airbnb's search results page]

Build a search results layout like this screenshot:
- Card grid with images
- Price in bottom right of each card
- Heart icon for favoriting
- Pagination at bottom

Changes from screenshot:
- 3 columns instead of 4
- No map sidebar
```

---

## 9. Paste Full Error Message

**What it is**: Copying the complete error, not just summarizing it.

**Why it works**: Error messages contain critical details—file names, line numbers, stack traces. Summarizing loses information AI needs.

**Bad approach**:
```
I'm getting a type error in my code
```

**Good approach**:
```
Getting this error:

TypeError: Cannot read properties of undefined (reading 'map')
    at ProductList (src/components/ProductList.tsx:23:15)
    at renderWithHooks (react-dom.development.js:14985:18)
    at mountIndeterminateComponent (react-dom.development.js:17811:13)

What's causing this and how do I fix it?
```

**Pro tip**: Include what you were doing when the error occurred:
```
This error appears when I click the "Load More" button
after the initial page load works fine.
```

---

## 10. Chunking (One Feature Per Message)

**What it is**: Requesting one thing at a time instead of bundling multiple features.

**Why it works**:
- Each feature gets full attention
- Easier to catch problems early
- Simpler to undo if something breaks
- AI context stays focused

**Bad approach**:
```
Add user authentication, a dashboard with charts,
notification system, and dark mode toggle.
```

**Good approach**:
```
Message 1: "Add user authentication with email/password"
[verify it works]

Message 2: "Add a dashboard page with a welcome message"
[verify it works]

Message 3: "Add a line chart showing user activity to the dashboard"
[verify it works]

Message 4: "Add dark mode toggle to the header"
[verify it works]
```

**Rule of thumb**: If you're using "and" more than twice, you're probably bundling too much.

---

## 11. Give Me 3 Options

**What it is**: Forcing AI to present multiple alternatives instead of a single answer.

**Why it works**:
- Avoids tunnel vision on first idea
- Reveals tradeoffs you didn't know existed
- You make the choice, AI provides options
- Often surfaces a better approach

**Bad approach**:
```
How should I structure my database for a todo app?
```

**Good approach**:
```
Give me 3 different ways to structure the database for a todo app.

For each option:
- Show the schema
- Pros and cons
- When you'd choose this approach
```

**Variations**:
- "Give me a simple version, medium version, and complex version"
- "Show me the quick-and-dirty way vs. the production-ready way"
- "What would a beginner do vs. what would an expert do?"

---

## 12. Comparison Matrix Table

**What it is**: Asking AI to evaluate options in a structured table format.

**Why it works**:
- Forces systematic comparison
- Easy to scan and compare
- Reveals which option wins on which criteria
- Makes decision rationale transparent

**Example**:
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

**Output you'll get**:
| Criteria | Supabase | Firebase | PlanetScale |
|----------|----------|----------|-------------|
| Ease of setup | Good | Good | Medium |
| Pricing (small) | Good | Medium | Good |
| Real-time | Good | Good | Poor |
| ... | ... | ... | ... |

---

## 13. Critique Yourself First

**What it is**: Asking AI to find problems with its own suggestion before you implement it.

**Why it works**:
- Catches issues before you build
- AI knows weaknesses but won't mention them unless asked
- Builds your critical thinking about solutions
- Cheaper to fix problems in planning than in code

**How to use**:
```
Before we implement this, critique your own solution:
- What are the weaknesses?
- What edge cases might break this?
- What would a senior engineer push back on?
- What's the biggest risk?
```

**Or after getting a solution**:
```
You just suggested [X approach].

Now argue against it. What's wrong with this approach?
What would you do differently if you had more time?
```

---

## 14. 5 Whys

**What it is**: Asking "why" repeatedly to drill down to root cause.

**Why it works**:
- Surfaces the real problem, not symptoms
- Prevents fixing the wrong thing
- Simple but powerful debugging technique
- Works for technical AND product problems

**Example - Technical**:
```
The page is slow.
Why? → The API call takes 3 seconds.
Why? → We're fetching all 10,000 products.
Why? → There's no pagination.
Why? → We didn't think the catalog would grow this big.
Why? → No one defined scale requirements upfront.

Root cause: Missing pagination. Fix that, not "make it faster."
```

**Example - Product**:
```
Users aren't completing onboarding.
Why? → They drop off at step 3.
Why? → Step 3 asks for credit card.
Why? → We require payment upfront.
Why? → We assumed it would reduce tire-kickers.
Why? → We never tested free trial vs. paid upfront.

Root cause: Test free trial model, not "improve step 3 UI."
```

**Prompt format**:
```
Apply the 5 Whys technique to this problem:
[describe problem]

Keep asking "why" until we reach the root cause.
```

---

## 15. Pre-Mortem ("How Could This Fail?")

**What it is**: Imagining the project has already failed, then working backward to identify causes.

**Why it works**:
- Easier to spot risks when you assume failure happened
- Overcomes optimism bias
- Surfaces concerns people are hesitant to voice
- Creates actionable prevention list

**How to use**:
```
Imagine it's 3 months from now and this feature completely failed.
Users hate it, it's full of bugs, we had to roll it back.

What went wrong? List the 5 most likely causes of failure.
```

**Then follow up**:
```
For each failure cause, what could we do NOW to prevent it?
```

**Example output**:
```
Potential failures:
1. Performance - didn't handle scale
   Prevention: Load test with 10x expected users

2. Edge cases - broke for certain user types
   Prevention: Define and test edge cases upfront

3. Scope creep - took 3x longer than planned
   Prevention: Lock scope, cut features aggressively
```

---

# TIER 3: ADVANCED METHODS

---

## 16. Ask AI to Ask Clarifying Questions

**What it is**: Explicitly inviting AI to interview YOU before it builds.

**Why it works**: AI often makes assumptions to fill gaps. This technique surfaces those gaps upfront.

**How to use**:
```
I want to build a booking system for my salon.

Before you start building, ask me 5-10 clarifying questions
about requirements, constraints, and preferences.
```

**Or more targeted**:
```
I want to add payments to my app.

What do you need to know about:
- Payment provider preference?
- Subscription vs. one-time?
- Currency and regions?
- Refund handling?

Ask me these questions before building.
```

---

## 17. Phased Approach for Complex Features

**What it is**: Breaking large features into explicit phases, building one phase at a time.

**Why it works**:
- Each phase is a working checkpoint
- Easier to test incrementally
- Can adjust direction between phases
- Less risk of compounding errors

**Example**:
```
# User Dashboard - Phased Build

## Phase 1: Foundation (this message)
- Dashboard route and basic layout
- Navigation sidebar
- Header with user name

## Phase 2: (next message)
- Activity feed component
- Recent items list

## Phase 3: (later)
- Analytics charts
- Settings panel

Let's start with Phase 1 only.
```

---

## 18. Acceptance Criteria Format

**What it is**: Using checkbox-style criteria that define "done."

**Why it works**: Creates unambiguous success conditions. Both you and AI know exactly what "finished" looks like.

**Example**:
```
## Feature: Password Reset

### Acceptance Criteria
- [ ] User can click "Forgot Password" from login page
- [ ] Email input form appears
- [ ] Valid email sends reset link (check for existing user)
- [ ] Invalid email shows error message
- [ ] Reset link expires after 1 hour
- [ ] Clicking link opens "Set New Password" form
- [ ] New password requires 8+ characters
- [ ] Success message redirects to login
```

---

## 19. Role Assignment ("Act as...")

**What it is**: Assigning AI a specific persona or expertise level.

**Why it works**:
- Changes the lens through which AI evaluates
- Surfaces concerns a generalist might miss
- Gets domain-specific advice

**Examples**:
```
Act as a senior security engineer. Review this authentication
code and tell me what vulnerabilities you see.
```

```
Act as a UX designer. Critique this user flow and suggest
improvements for clarity and ease of use.
```

```
Act as a skeptical investor. Poke holes in this business model.
```

**Combine perspectives**:
```
Review this feature from 3 perspectives:
1. As a first-time user
2. As a power user
3. As the developer who has to maintain this
```

---

## 20. Chain of Thought ("Think Step by Step")

**What it is**: Asking AI to show its reasoning process, not just the answer.

**Why it works**:
- Improves accuracy on complex problems
- You can spot where reasoning goes wrong
- Learn the thought process, not just the solution

**How to use**:
```
Think step by step through this problem:
[describe problem]

Show your reasoning at each step before giving the final answer.
```

**For code**:
```
Walk me through how you would approach building this feature:
1. What's the first thing you'd think about?
2. What decisions need to be made?
3. What order would you build things in?
4. Then show me the code.
```

---

## 21. Steelman (Strengthen the Weak Idea)

**What it is**: Asking AI to make the strongest possible case for an idea, even a weak one.

**Why it works**:
- Discovers hidden value in ideas you might dismiss
- Reveals conditions under which an idea would work
- Counteracts knee-jerk rejection

**How to use**:
```
I'm tempted to dismiss this idea: [describe idea]

Steelman it. What's the strongest argument FOR this approach?
Under what conditions would this be the right choice?
```

**Example**:
```
My co-founder wants to build the MVP with no-code tools.
I think we should use real code from day one.

Steelman the no-code approach. When would that be the right call?
```

---

## 22. Version This (v1, v2, v3)

**What it is**: Requesting multiple versions of increasing complexity or quality.

**Why it works**:
- Shows the spectrum of possibilities
- You choose your complexity budget
- Learn what "better" looks like incrementally

**Examples**:
```
Build a user authentication system in 3 versions:

v1: Simplest possible (MVP, ship today)
v2: Production-ready (good enough for real users)
v3: Enterprise-grade (security-hardened, scalable)

Start with v1.
```

```
Write this email in 3 versions:
v1: Casual and friendly
v2: Professional but warm
v3: Formal and corporate
```

---

## 23. First Principles ("Simplest Version")

**What it is**: Stripping away assumptions to find the core of what you need.

**Why it works**:
- Fights feature creep
- Reveals what's actually essential
- Often produces better solutions through constraints

**How to use**:
```
I want to build [complex thing].

First principles question: What's the absolute simplest version
that would still solve the core problem?

Strip away everything non-essential.
```

**Example**:
```
I want to build a project management tool.

First principles: What's the minimum viable version?
- No: Gantt charts, time tracking, integrations, permissions
- Yes: [what's actually essential?]
```

---

## 24. Confidence Levels

**What it is**: Asking AI to rate its certainty and explain what would change its answer.

**Why it works**:
- AI often sounds confident when it shouldn't be
- Reveals areas of uncertainty you should verify
- Helps you know when to trust vs. double-check

**How to use**:
```
[After getting an answer]

How confident are you in this answer? (Low / Medium / High)

What would change your confidence?
What information would make you revise this?
```

**Example response**:
```
Confidence: Medium

I'm confident about the general approach, but:
- I'm not 100% sure about the Supabase pricing tier limits
- The rate limiting numbers are estimates, test to verify
- This assumes your traffic pattern is fairly even (not spiky)
```

---

# Quick Reference Card

| Method | When to Use | Example Phrase |
|--------|-------------|----------------|
| Markdown headers | Always for structure | `# Section` `## Subsection` |
| ALL CAPS | Critical constraints | `MUST`, `NEVER`, `REQUIRED` |
| Constraint sandwich | Every non-trivial request | Context → Ask → Constraints |
| Interview method | Complex features | "Let's start with..." |
| Reference + Modify | UI/design work | "Like Stripe but with..." |
| Numbered steps | Sequential processes | `1. First... 2. Then...` |
| Explain before fixing | Debugging | "Why is this happening?" |
| Screenshots | UI work | [attach image] |
| Full error paste | Any error | Copy entire stack trace |
| Chunking | Multiple features | One feature per message |
| Give 3 options | Decision points | "Show me 3 ways to..." |
| Comparison matrix | Evaluating choices | "Create a table comparing..." |
| Critique yourself | Before implementing | "What's wrong with this?" |
| 5 Whys | Root cause analysis | "Why? Why? Why?..." |
| Pre-mortem | Risk planning | "How could this fail?" |
| Ask for questions | Unclear requirements | "Ask me clarifying questions" |
| Phased approach | Large features | "Phase 1... Phase 2..." |
| Acceptance criteria | Definition of done | `- [ ] checkbox format` |
| Role assignment | Specialized review | "Act as a security engineer" |
| Chain of thought | Complex reasoning | "Think step by step" |
| Steelman | Evaluating weak ideas | "Make the strongest case for..." |
| Version this | Complexity options | "Give me v1, v2, v3" |
| First principles | Fighting bloat | "What's the simplest version?" |
| Confidence levels | Gauging certainty | "How sure are you?" |
