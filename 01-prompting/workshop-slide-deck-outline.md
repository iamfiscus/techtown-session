# Intro to Prompt Engineering
## TechTown Start Studio Workshop
### January 21, 2026 | JD Fiscus

---

# HOUR 1: HOW TO THINK ABOUT PROMPTING (55 min)

---

## Slide 1: Title Slide
**Intro to Prompt Engineering**
*Stop Praying, Start Planning*

JD Fiscus | TechTown Start Studio
January 21, 2026

---

## Slide 2: The Hook - A Prompt Disaster Story (5 min)
### "Build me an app like Uber"

**What happened:**
- $47 in tokens burned
- 3 hours of confusion
- An app that sort of worked but couldn't be fixed
- Started over from scratch

**The problem:** Outcome-driven prompting

*[Tell personal story or use relatable example]*

---

## Slide 3: What You'll Learn Today

By the end of this workshop, you will:

1. **Understand** why your prompts work (or don't)
2. **Know** a framework that works every time
3. **Have** a prompt that changes everything
4. **See** it work live on a real product

---

## Slide 4: The Mindset Shift (10 min)
### Outcome vs. Process Prompting

| Outcome Prompting | Process Prompting |
|-------------------|-------------------|
| "Build me an e-commerce site" | "Help me plan the steps to build product pages" |
| "Make my app secure" | "Interview me about security requirements" |
| "Add user authentication" | "What questions should I answer before adding auth?" |

**Outcome = Pray | Process = Plan**

---

## Slide 5: Outcome Prompting Example

**Prompt:** "Build me a booking system for my salon"

**Result:**
- Generic booking UI
- No understanding of YOUR business
- Missing: cancellation policy, staff schedules, service types
- You: "That's not what I wanted!"
- AI: "You didn't tell me!"

*[Show actual screenshot of generic output]*

---

## Slide 6: Process Prompting Example

**Prompt:** "I'm building a booking system for my salon. Before we build anything, interview me about my requirements. Ask one question at a time."

**Result:**
- AI asks about services, staff, hours, policies
- YOU provide the context
- Spec document emerges naturally
- Build matches YOUR business

*[Show actual interview exchange]*

---

## Slide 7: Why This Works
### You Know Things AI Doesn't

- Your business model
- Your customers' quirks
- Your constraints
- Your preferences
- Your existing systems

**Process prompting extracts this from YOUR head.**

---

## Slide 8: Token Economics (10 min)
### Your Prompt Wallet

Every word costs money:
- ChatGPT-4: ~$0.01 per 1K tokens
- Claude: ~$0.015 per 1K tokens
- Lovable: Credits = tokens

**1 token ≈ 4 characters ≈ 0.75 words**

"Build me an e-commerce site" = 6 tokens
+ AI's response = 500+ tokens
+ Your follow-up = 100+ tokens
+ Confusion loop = 2000+ tokens

---

## Slide 9: The Context Window
### Your Bucket Has a Limit

```
[=========|          ]
   Used      Available
```

- GPT-4: ~128K tokens
- Claude: ~200K tokens
- Lovable: Varies by plan

**When the bucket overflows:**
- AI "forgets" earlier context
- Starts contradicting itself
- You start over (expensive!)

---

## Slide 10: Efficiency Principle

**Expensive:** Prompt → Get wrong thing → Re-prompt → Get wrong thing → Re-prompt...

**Cheap:** Plan → Interview → Spec → Prompt once → Get right thing

*The planning happens in cheaper tools (or free ones)*

---

## Slide 11: The Tool Ladder (10 min)
### Where Are You Now? Where Do You Want to Be?

```
Level 1: ChatGPT / Gemini    → Conversation, planning, interviews
Level 2: Lovable / Bolt      → Visual building, quick prototypes
Level 3: Cursor / Replit     → More control, real code access
Level 4: Claude Code         → Full development environment
```

**Today's goal:** Use Level 1 to be better at Level 2
**Long-term goal:** Graduate up the ladder

---

## Slide 12: When to Use What

| Tool | Best For | Limitations |
|------|----------|-------------|
| ChatGPT/Gemini | Planning, interviews, specs | No building |
| Lovable | Quick MVPs, visual prototypes | Limited customization |
| Cursor | Real development, version control | Steeper learning curve |
| Claude Code | Full autonomy, complex features | Most technical |

**Pro tip:** Plan in ChatGPT (free), build in Lovable (paid)

---

## Slide 13: The Workflow That Changes Everything (15 min)
### Plan → Interview → Spec → Build

```
┌─────────┐     ┌───────────┐     ┌─────────┐     ┌─────────┐
│  PLAN   │ ──► │ INTERVIEW │ ──► │  SPEC   │ ──► │  BUILD  │
│         │     │           │     │         │     │         │
│ What do │     │ AI asks   │     │ Document│     │ One     │
│ I want? │     │ YOU       │     │ emerges │     │ prompt  │
└─────────┘     └───────────┘     └─────────┘     └─────────┘
   Free            Free           Free/Cheap       Paid
```

---

## Slide 14: Step 1 - PLAN
### Know What You Want (Roughly)

Before you touch any tool:
- What feature am I building?
- Who is it for?
- What's the core function?

**Not a detailed spec—just a direction.**

Example: "I want to add a partner invite feature to my app"

---

## Slide 15: Step 2 - INTERVIEW
### Let AI Extract the Details

The prompt that changes everything:

> "I want you to interview me one question at a time. Give me an example of a response to make me think and explain the technical terms in a non-technical way."

**Then tell it what you're building.**

---

## Slide 16: Why This Prompt Works

1. **"One question at a time"** → Prevents overwhelm
2. **"Example response"** → Shows you what good looks like
3. **"Explain technical terms"** → You learn as you go
4. **"Non-technical way"** → No jargon intimidation

**You're not dumb. You just need the right guide.**

---

## Slide 17: Step 3 - SPEC
### Turn Interview Into Document

After the interview, ask:

> "Based on our conversation, create a specification document I can use to build this feature. Include requirements, user flows, and technical considerations."

**Now you have a blueprint.**

---

## Slide 18: Step 4 - BUILD
### One Focused Prompt

Take your spec to Lovable (or your tool):

> "I'm adding a [feature] to my existing app. Here's the specification: [paste spec]. Please implement this feature, focusing on [specific component first]."

**Focused. Specific. Efficient.**

---

## Slide 19: The Workflow in Action
### What We're About to Do

Hour 2:
1. Meet Tyranny and her Digital Doula app
2. Watch the interview process live
3. Build a spec document together
4. Start implementing in Lovable

**You'll see exactly how this works.**

---

## Slide 20: Quick Recap - Hour 1

1. **Mindset:** Process > Outcome
2. **Economics:** Words cost money, plan for free
3. **Tools:** Know the ladder, use the right rung
4. **Workflow:** Plan → Interview → Spec → Build
5. **The Prompt:** Interview me one question at a time...

---

# HOUR 2: BUILD A FEATURE WITH TYRANNY (55 min)

---

## Slide 21: Meet Tyranny
### Digital Doula - Pregnancy & Postpartum Companion

*[Photo of Tyranny / App screenshot]*

- Natural language digital doula
- Pregnancy and postpartum tracking
- Companion for vulnerable moments
- Built in Lovable

**Today's feature:** Partner Invite System

---

## Slide 22: The Feature We're Building

**Partner Invite System**
- User has their own account
- User can invite their partner
- Partner gets limited access
- Both see relevant information

**Tyranny's starting point:** Has the core app, needs this feature

---

## Slide 23: Step 1 - The Plan

Tyranny's plan:
- Feature: Partner invite
- Who: Expecting mothers inviting partners
- Core function: Shared access to pregnancy journey

**That's enough to start the interview.**

---

## Slide 24: Step 2 - The Interview (LIVE)

*[Switch to live demo - ChatGPT/Claude]*

**The prompt:**
> "I'm building a partner invite feature for my pregnancy tracking app called Digital Doula. I want you to interview me one question at a time about this feature. Give me an example of a response to make me think and explain any technical terms in a non-technical way."

*[Conduct interview with Tyranny, audience participates]*

---

## Slide 25: Interview Checkpoint

Questions AI might ask:
- How does a user send an invite?
- What can the partner see vs. not see?
- Can there be multiple partners?
- What happens if they break up?
- Email or phone invite?
- Does partner need an account?

*[Capture key decisions on screen]*

---

## Slide 26: Step 3 - The Spec (LIVE)

*[Continue live demo]*

**The prompt:**
> "Based on our conversation, create a specification document for the partner invite feature. Include: requirements, user flow, permissions model, and edge cases."

*[Show spec being generated]*

---

## Slide 27: Spec Review

Key sections:
- **Requirements:** What must it do?
- **User Flow:** Step by step journey
- **Permissions:** What can partner access?
- **Edge Cases:** What could go wrong?

*[Review spec with audience, make adjustments]*

---

## Slide 28: Step 4 - The Build (LIVE)

*[Switch to Lovable]*

**The prompt:**
> "I'm adding a partner invite feature to my Digital Doula app. Here's the specification: [paste]. Start by creating the invite UI component."

*[Begin building, narrate decisions]*

---

## Slide 29: Building Checkpoint

What we're watching for:
- Does it match the spec?
- Any clarifying questions from AI?
- Where do we need to course-correct?

*[Continue building as time allows]*

---

## Slide 30: What Just Happened

In ~45 minutes:
1. Defined the feature (2 min)
2. Got interviewed by AI (15 min)
3. Generated a spec (5 min)
4. Started building (20 min)

**No guessing. No "prompt and pray."**

---

# WRAP-UP (10 min)

---

## Slide 31: The Workflow - One More Time

```
PLAN → INTERVIEW → SPEC → BUILD
```

Use free tools for planning.
Use paid tools for building.
Let AI interview YOU.

---

## Slide 32: Your Takeaway Prompt

Screenshot this:

```
I want you to interview me one question at a time
about [WHAT YOU'RE BUILDING].

Give me an example of a response to make me think
and explain the technical terms in a non-technical way.
```

*[Display prominently for photos]*

---

## Slide 33: The Cheat Sheet

*[Show QR code or announce distribution]*

One-page reference:
- The workflow
- The prompt
- Tool comparison
- Key terminology

**Grab one on your way out.**

---

## Slide 34: What's Next?

**Your homework:**
1. Open ChatGPT or Claude (free)
2. Use the interview prompt on YOUR feature
3. Generate YOUR spec
4. Bring spec to Lovable

**Stuck?** TechTown has resources.

---

## Slide 35: Office Hours & Support

- Mentors available through Start Studio
- Follow-up sessions TBD
- Questions? Reach out to TechTown team

*[Contact info / signup sheet]*

---

## Slide 36: Q&A

Questions?

---

## Slide 37: Thank You

**JD Fiscus**
*[Contact info if sharing]*

TechTown Start Studio
January 21, 2026

*Don't pray. Plan.*

---

# APPENDIX: Backup Slides

---

## Backup: Token Calculation Example

"Build me a complete e-commerce website with user authentication, product catalog, shopping cart, checkout, and payment processing"

= ~25 tokens (your prompt)
+ ~2000 tokens (AI response)
+ ~500 tokens (your confusion)
+ ~2000 tokens (AI re-explanation)
+ ~1000 tokens (wrong output)
= 5,525 tokens ≈ $0.08-0.15

**vs.**

Interview + Spec + Focused Build = Higher quality, similar cost

---

## Backup: Common Prompting Mistakes

1. **Too vague:** "Make it better"
2. **Too much at once:** "Build everything"
3. **No context:** "Add a button"
4. **Outcome-focused:** "I want X" vs "Help me figure out X"
5. **Not iterating:** One prompt, expect perfection

---

## Backup: XML/Markdown Structure

When prompts get complex:

```xml
<context>
I'm building a pregnancy tracking app
</context>

<task>
Add a partner invite feature
</task>

<constraints>
- Must work on mobile
- Partners have limited access
- Email-based invites only
</constraints>
```

*Structure helps AI understand you.*

---

## Backup: Temperature Explained

**Temperature = Randomness**

- Low (0.0-0.3): Predictable, consistent, factual
- Medium (0.4-0.7): Balanced creativity
- High (0.8-1.0): Creative, varied, sometimes weird

**For building features:** Keep it low
**For brainstorming:** Turn it up
