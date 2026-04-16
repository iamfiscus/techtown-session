# TechTown Start Studio: Session Comparison & Gap Analysis
## Prompt Engineering Workshop Series | JD Fiscus

---

# SESSION 1: "Intro to Prompt Engineering — Stop Praying, Start Planning"
### January 21, 2026 | 2 hours (55 min lecture + 55 min live demo + 10 min wrap-up)

---

## Hour 1: How to Think About Prompting

### Slide 1 — Title
**Intro to Prompt Engineering: Stop Praying, Start Planning**

### Slide 2 — The Hook: A Prompt Disaster Story (5 min)
- Personal story: "Build me a patient intake form" gone wrong
- $47 burned, 3 hours wasted, 17 broken versions
- The AI suggested adding a shopping cart to a medical form
- **Key concept introduced:** Outcome-driven prompting is the problem

### Slide 3 — What You'll Learn Today
1. Understand why your prompts work (or don't)
2. Know a framework that works every time
3. Have a prompt that changes everything
4. See it work live on a real product

### Slide 4 — The Mindset Shift: Outcome vs. Process Prompting (10 min)
| Outcome Prompting | Process Prompting |
|---|---|
| "Build me an e-commerce site" | "Help me plan the steps to build product pages" |
| "Make my app secure" | "Interview me about security requirements" |
| "Add user authentication" | "What questions should I answer before adding auth?" |

**Takeaway:** Outcome = Pray. Process = Plan.

### Slide 5 — Outcome Prompting Example
- Prompt: "Build me a booking system for my salon"
- Result: Generic UI, no business context, missing cancellation policy/staff schedules/service types
- The "That's not what I wanted!" / "You didn't tell me!" dynamic

### Slide 6 — Process Prompting Example
- Prompt: "I'm building a booking system for my salon. Before we build anything, interview me about my requirements. Ask one question at a time."
- Result: AI asks about services, staff, hours, policies. Spec emerges naturally.

### Slide 7 — Why This Works
- You know things AI doesn't: your business model, customers, constraints, preferences, existing systems
- Process prompting extracts this knowledge from YOUR head

### Slide 8 — Token Economics: Your Prompt Wallet (10 min)
- Every word costs money (~$0.01-0.015 per 1K tokens)
- 1 token = ~4 characters = ~0.75 words
- Demonstrated the cost spiral of confused prompting vs. efficient prompting

### Slide 9 — The Context Window
- GPT-4: ~128K tokens, Claude: ~200K tokens
- When the bucket overflows: AI forgets, contradicts itself, you start over

### Slide 10 — Efficiency Principle
- **Expensive:** Prompt > wrong > re-prompt > wrong > re-prompt...
- **Cheap:** Plan > interview > spec > prompt once > get right thing

### Slide 11 — The Tool Ladder (10 min)
```
Level 1: ChatGPT / Gemini    → Conversation, planning, interviews
Level 2: Lovable / Bolt      → Visual building, quick prototypes
Level 3: Cursor / Replit     → More control, real code access
Level 4: Claude Code         → Full development environment
```
Goal: Use Level 1 to be better at Level 2. Graduate up over time.

### Slide 12 — When to Use What
| Tool | Best For | Limitations |
|---|---|---|
| ChatGPT/Gemini | Planning, interviews, specs | No building |
| Lovable | Quick MVPs, visual prototypes | Limited customization |
| Cursor | Real development, version control | Steeper learning curve |
| Claude Code | Full autonomy, complex features | Most technical |

**Pro tip:** Plan in ChatGPT (free), build in Lovable (paid).

### Slide 13 — The Workflow: Plan > Interview > Spec > Build (15 min)
```
PLAN (Free) → INTERVIEW (Free) → SPEC (Free/Cheap) → BUILD (Paid)
```

### Slide 14 — Step 1: PLAN
- What feature am I building? Who is it for? What's the core function?
- Not a detailed spec — just a direction.

### Slide 15 — Step 2: INTERVIEW
**The Golden Prompt:**
> "I want you to interview me one question at a time. Give me an example of a response to make me think and explain the technical terms in a non-technical way."

### Slide 16 — Why The Golden Prompt Works
1. "One question at a time" → Prevents overwhelm
2. "Example response" → Shows what good looks like
3. "Explain technical terms" → You learn as you go
4. "Non-technical way" → No jargon intimidation

### Slide 17 — Step 3: SPEC
> "Based on our conversation, create a specification document I can use to build this feature. Include requirements, user flows, and technical considerations."

### Slide 18 — Step 4: BUILD
> "I'm adding a [feature] to my existing app. Here's the specification: [paste spec]. Please implement this feature, focusing on [specific component first]."

### Slide 19 — Preview of Hour 2
- Meet Tyranny and Digital Doula app
- Watch interview process live
- Build spec together
- Start implementing in Lovable

### Slide 20 — Hour 1 Recap
1. Mindset: Process > Outcome
2. Economics: Words cost money, plan for free
3. Tools: Know the ladder, use the right rung
4. Workflow: Plan → Interview → Spec → Build
5. The Prompt: Interview me one question at a time...

---

## Hour 2: Build a Feature with Tyranny (Live Demo)

### Slide 21 — Meet Tyranny: Digital Doula
- Natural language pregnancy/postpartum companion
- Built in Lovable
- **Today's feature:** Partner Invite System

### Slide 22 — The Feature
- User invites their partner
- Partner gets limited access
- Both see relevant information

### Slide 23 — Step 1: The Plan
- Feature: Partner invite
- Who: Expecting mothers inviting partners
- Core function: Shared access to pregnancy journey

### Slides 24-25 — Step 2: The Interview (LIVE)
- Used the Golden Prompt live with Tyranny
- AI asked about: invite method, partner permissions, multiple partners, breakup scenario, email vs phone, account requirements

### Slides 26-27 — Step 3: The Spec (LIVE)
- Generated spec with: requirements, user flow, permissions model, edge cases

### Slides 28-29 — Step 4: The Build (LIVE)
- Moved to Lovable, pasted spec, started building invite UI component
- Watched for: spec alignment, AI clarifying questions, course corrections

### Slide 30 — What Just Happened
- 2 min defining feature, 15 min interview, 5 min spec, 20 min building
- No guessing. No "prompt and pray."

---

## Wrap-Up

### Slides 31-32 — Takeaway Prompt
The Golden Prompt displayed prominently for screenshots.

### Slide 33 — Cheat Sheet
One-page handout: workflow, prompt, tool comparison, key terminology.

### Slides 34-37 — Homework, Office Hours, Q&A, Thank You
- Homework: Use the interview prompt on YOUR feature, generate YOUR spec, bring to Lovable

---

## Appendix (Backup Slides)
- Token calculation deep-dive example
- Common prompting mistakes (too vague, too much at once, no context, outcome-focused, not iterating)
- XML/Markdown structure for complex prompts
- Temperature explained (Low = predictable, High = creative)

---
---

# SESSION 2: "From Interview to Interface — Turn Your Spec Into a Real App"
### February 2026 | 45 min talk + 15 min Q&A

---

## Recap & Problem Statement

### Slide 1 — Title
**From Interview to Interface: Turn Your Spec Into a Real App**

### Slide 2 — Welcome Back (2 min)
- Recap Session 1: Plan → Interview → Spec → Build
- Reminder of the Golden Prompt
- **Today:** We go deep on BUILD.

### Slide 3 — The Problem: The Spec-to-Screen Gap (3 min)
- You have a great spec... then you dump it all into Lovable
- What happens: Lovable chokes, generic-looking app, half-built features
- **Key insight:** The spec is NOT the prompt. You need a translation step.

### Slide 4 — What You'll Learn
1. How to translate interview output into Lovable-ready prompts
2. A reusable template for every feature you build
3. Why one-prompt-at-a-time beats mega-prompts
4. See it work live — spec to polished UI

### Slide 5 — The Updated Workflow (3 min)
```
PLAN → INTERVIEW → SPEC → TRANSLATE (NEW!) → BUILD
```
The TRANSLATE step separates messy builds from polished ones.

---

## Part 1: The Lovable Prompting Playbook (15 min)

### Slide 6 — Rule #1: One Feature Per Prompt
- Don't build the whole house at once
- Bad: "Build me a pregnancy app with accounts, invites, tracking, journal, notifications, and chatbot"
- Good: "Create a clean login/signup page with email auth" → then "Add a dashboard with timeline and appointments"
- **Layer by layer. Like painting.**

### Slide 7 — Rule #2: Structure Your Prompts
Every prompt should follow:
```
PURPOSE:   What am I building?
FEATURES:  What does it do? (2-3 max)
USER FLOW: What happens step by step?
UI STYLE:  What should it look like?
```

### Slide 8 — Rule #3: Reference Real Designs
- Vague: "Make it look modern and clean"
- Specific: "Use a design similar to Stripe's dashboard — white background, subtle shadows, blue accent, left sidebar"
- Even better: "Layout like Notion's clean minimal style..."
- **You don't need to be a designer. Point at something you like.**

### Slide 9 — Rule #4: Name Your Styles
| Say This | Get This |
|---|---|
| "card-based layout" | Organized content in clean boxes |
| "generous whitespace" | Breathing room, not cramped |
| "subtle shadows" | Depth without heaviness |
| "rounded corners" | Friendly, modern feel |
| "sticky navigation" | Header stays while scrolling |
| "gradient hero section" | Eye-catching top banner |
| "mobile-responsive" | Works on phones too |
| "glassmorphism" | Frosted glass effect |
| "skeleton loading" | Smooth loading states |

### Slide 10 — Rule #5: Iterate, Don't Restart (The Fix-Forward Method)
- Don't: "Start over. Build a completely new version."
- Do: "The appointment card looks good but needs: (1) date larger and bold, (2) colored left border for urgency, (3) reduce padding between cards."
- **Be specific about what to change. Keep what works.**

---

## Part 2: The Starter Template (10 min)

### Slide 11 — Introducing the Template
Session 1's Golden Prompt gets you a spec. Today's template turns that spec into Lovable prompts.

### Slide 12 — Step 1: App Foundation Prompt
```
I'm building [APP NAME], a [ONE-SENTENCE DESCRIPTION].
Tech stack: React with TypeScript and Tailwind CSS.

Create the app foundation with:
- A clean, modern layout with [STYLE REFERENCE]
- Navigation: [DESCRIBE NAV STRUCTURE]
- Color scheme: [PRIMARY COLOR] with [ACCENT COLOR]
- Typography: Clean sans-serif, generous spacing

Start with just the layout shell and navigation.
Don't add any features yet.
```
**Always your FIRST prompt. Get the foundation right.**

### Slide 13 — Step 2: Feature Prompts (One at a Time)
```
Add [FEATURE NAME] to the app.

PURPOSE: [What this feature does]
USER FLOW:
1. User [first action]
2. System [response]
3. User [next action]
4. System [result]

UI DETAILS:
- [Layout description]
- [Key visual elements]
- [Interactive elements]

Keep the existing design style consistent.
```

### Slide 14 — Step 3: Refinement Prompts
```
Improve the [COMPONENT] with these changes:

VISUAL:
- [Specific visual change]
- [Specific visual change]

BEHAVIOR:
- [Specific interaction change]
- [Specific interaction change]

Don't change anything else.
```

### Slide 15 — Putting It Together
- Interview gave: feature name, user stories, requirements, edge cases
- Template turns this into: 6 focused prompts (foundation + 5 features) instead of 1 mega-prompt

---

## Part 3: Live Demo (12 min)

### Slides 16-19 — Building Digital Doula's "My Village" Feature
1. Foundation prompt: app shell, sage green + cream, Calm-like design, bottom nav
2. Feature prompt: invite flow with email/link modal, pending cards, status badges
3. Refinement: larger illustrations, permission tier selector, manage panel
4. Result: 4-5 focused prompts produced a polished feature

### Slide 20 — What Just Happened
- 1 prompt for foundation, 1 for feature, 2-3 for refinement
- Each prompt was specific, clear about user flow, descriptive about UI, referenced real patterns

---

## Part 4: Pro Tips & Common Mistakes (5 min)

### Slide 21 — The 5 Lovable Mistakes Everyone Makes
| Mistake | Fix |
|---|---|
| Dump whole spec in one prompt | Break into foundation + features + polish |
| Say "make it look good" | Reference a real app or design style |
| Fix by starting over | Fix forward — be specific about what to change |
| Ignore the preview | Check every prompt's result before moving on |
| Skip mobile | Say "mobile-first" in your first prompt |

### Slide 22 — The Meta-Prompting Trick
> "I want to add a notification settings page. Before building it, describe what this page should contain and how it should be laid out. Then I'll tell you what to change before you build it."

Asking AI to help write the prompt before executing.

### Slide 23 — The Complete Process
```
SESSION 1                    SESSION 2
────────                    ────────
PLAN                        TRANSLATE
  ↓                           ↓
INTERVIEW (Golden Prompt)   Foundation Prompt
  ↓                           ↓
SPEC                        Feature Prompts (one at a time)
                              ↓
                            Refinement Prompts
                              ↓
                            SHIP IT
```

---

## Wrap-Up

### Slides 24-25 — Takeaways & Complete Toolkit
- Template: Foundation → Features → Refinement
- Format: Purpose, User Flow, UI Details
- Rules: One feature per prompt, reference real designs, fix forward

### Slides 26-28 — What's Next, Q&A, Thank You
- Homework: fill in template with YOUR spec, build one feature in Lovable
- Graduate path: Lovable → Cursor → Claude Code

---

## Appendix (Backup Slides)
- Lovable vs Cursor vs Claude Code comparison table
- The Four Prompting Levels (Training Wheels → No Training Wheels → Meta Prompting → Reverse Meta)
- Full template reference (handout)

---
---

# GAP ANALYSIS: What's Missing Between Sessions 1 & 2

## Covered Well Across Both Sessions

| Topic | Session 1 | Session 2 |
|---|---|---|
| Mindset shift (outcome vs. process) | Deep coverage | Brief recap |
| The Golden Prompt (interview method) | Core teaching | Referenced as foundation |
| Token economics / context windows | Taught | Assumed knowledge |
| Tool ladder (Lovable → Cursor → Claude Code) | Introduced | Referenced in "what's next" |
| Workflow: Plan → Interview → Spec → Build | Full framework | Extended with TRANSLATE step |
| Live demo with Digital Doula | Interview + spec | Building + refinement |
| One feature at a time principle | Mentioned briefly | Central rule (#1) |
| Lovable-specific prompting techniques | Not covered | Full playbook (5 rules) |
| Prompt templates | Golden Prompt only | Foundation + Feature + Refinement |
| Meta-prompting | Not covered | Introduced |

---

## GAP 1: Debugging & Troubleshooting Prompts
**What's missing:** Neither session teaches what to do when things go wrong *mid-build*. Session 1's cheat sheet has a brief debugging prompt template, but it's never taught in the slides. When Lovable produces broken output, attendees need:
- How to describe bugs to AI effectively
- When to use "Try to fix it" vs. writing your own fix prompt
- How to share error messages / screenshots with AI
- When to roll back vs. fix forward (decision framework)

**Why it matters:** This is where founders actually get stuck and burn tokens.

---

## GAP 2: Managing Long Conversations / Context Degradation
**What's missing:** Session 1 teaches that context windows exist and overflow. But neither session teaches practical strategies for managing this:
- When to start a new chat vs. continue the current one
- How to "reset" context by summarizing the conversation
- Signs that AI is losing the thread (contradictions, forgetting requirements)
- How to carry context between tools (ChatGPT interview → Lovable build)

**Why it matters:** Founders hit this wall after 10-15 prompts in Lovable. They don't know why quality degrades.

---

## GAP 3: Version Control / Saving Progress
**What's missing:** No coverage of how to protect your work:
- Lovable's version history and how to use it
- When to "checkpoint" by saving/exporting
- How to recover from a prompt that breaks everything
- Git basics for those graduating to Cursor

**Why it matters:** The #1 fear is "I'll break what's working." This is what causes the restart-from-scratch behavior.

---

## GAP 4: Evaluating AI Output
**What's missing:** Neither session teaches how to *judge* whether AI output is good:
- How to test a feature (click through the user flow you specified)
- What "done" looks like for a prompt
- How to spot common AI code problems (hardcoded data, missing edge cases, no error states)
- When output is "good enough" vs. needs refinement

**Why it matters:** Founders either accept everything or reject everything. They need a rubric.

---

## GAP 5: Working with Existing Code / Adding to an App
**What's missing:** Both sessions build from a relatively clean starting point. Real attendees have messy existing Lovable projects. Missing:
- How to describe your existing app to AI when adding features
- How to prevent new prompts from breaking existing features
- "Don't change anything else" as a defensive prompt pattern (mentioned briefly but not taught as strategy)
- How to scope prompts that modify vs. add

**Why it matters:** Most attendees aren't starting fresh — they have apps with accumulated AI decisions they don't fully understand.

---

## GAP 6: When AI Is Wrong (Hallucination & Bad Advice)
**What's missing:** Session 1's disaster stories show AI failures, but neither session teaches:
- How to verify AI's technical suggestions
- When to push back on AI recommendations
- How to spot hallucinated features or APIs
- The difference between AI being creative vs. AI being wrong

**Why it matters:** Non-technical founders can't independently verify technical claims. They need heuristics.

---

## GAP 7: Data & Backend Basics
**What's missing:** Both sessions focus entirely on UI/frontend. But attendees building real products need:
- What happens to user data (where does it go?)
- Supabase / database basics for Lovable users
- Authentication beyond "add login" (what's actually happening)
- API connections (how your app talks to other services)

**Why it matters:** Every attendee will hit this wall within 2-3 features. It's the #1 reason Lovable apps stall.

---

## GAP 8: Prompt Patterns Beyond Lovable
**What's missing:** Session 2 is heavily Lovable-specific. For attendees graduating up the ladder:
- How prompting changes for Cursor (more technical, code-aware)
- How prompting changes for Claude Code (system prompts, file references)
- How to reuse interview/spec skills in other tools
- When Lovable hits its limits and it's time to move up

**Why it matters:** Session 1 introduced the tool ladder. Neither session teaches how to actually climb it.

---

## GAP 9: Collaboration & Handoff
**What's missing:** Attendees often work with co-founders, mentors, or hired developers:
- How to share specs with collaborators
- How to hand off a Lovable project to a developer
- How to describe what AI built to someone who wasn't in the conversation
- Exporting/deploying from Lovable

**Why it matters:** The Start Studio cohort has mentors and eventually hires. The spec document is only useful if others can read and act on it.

---

## GAP 10: Prompt Hygiene & Organization
**What's missing:** Practical file/document management:
- Where to save your specs (not just in the chat)
- How to organize prompts you want to reuse
- Naming conventions for features/versions
- Keeping a prompt journal or log of what worked

**Why it matters:** Founders who don't save their specs end up re-interviewing from scratch.

---

## Summary: Priority Gaps for a Potential Session 3

| Priority | Gap | Why |
|---|---|---|
| **HIGH** | Debugging & troubleshooting prompts | Where founders burn the most tokens |
| **HIGH** | Managing context degradation | Invisible problem that derails builds |
| **HIGH** | Data & backend basics | Wall every Lovable user hits |
| **MEDIUM** | Evaluating AI output | Need a rubric for "is this right?" |
| **MEDIUM** | Working with existing messy code | Real-world reality for every attendee |
| **MEDIUM** | Version control / saving progress | Fear of breaking things causes restarts |
| **LOW** | Prompt patterns beyond Lovable | Relevant for graduates, not current cohort |
| **LOW** | Collaboration & handoff | Important later in their journey |
| **LOW** | When AI is wrong | Covered partially by process prompting |
| **LOW** | Prompt hygiene & organization | Good practice, not urgent |

---

*Compiled February 2026 for TechTown Start Studio*
