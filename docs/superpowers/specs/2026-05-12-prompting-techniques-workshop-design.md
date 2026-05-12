# Prompting Techniques Workshop — Design Spec

**Working title:** Stop Praying, Start Stacking — 4 Layers to a Lovable-Ready Prompt
**Date:** 2026-05-12
**Author:** JD Fiscus
**Folder:** `03-prompting-techniques/`

---

## Overview

A 45-minute interactive workshop that takes a fresh TechTown audience from prompting novice to power-user-with-a-sampler. Audience writes ONE prompt for their own project and upgrades it through 4 layers. They walk out with a Lovable-ready V4 prompt and a cheat sheet covering 5 techniques (4 layers + the interview rescue).

The 45 min is followed by **1–2 hours of build time** where JD and floor volunteers float to help. The session is framed as build prep, not a standalone lecture — which lowers retention pressure and turns the cheat sheet into a live tool.

## Audience

- ~250 attendees, fresh TechTown crowd (not repeat from prior 2-hour workshop)
- Small-business owners / non-technical builders becoming AI builders with Lovable
- Markdown literacy assumed at zero — needs a 90-second primer
- May or may not have Lovable open during the session; ChatGPT or Claude.ai is the prompt-along surface
- Solo presenter (JD) with floor volunteers helping individuals

## Goals

1. **Confidence:** every attendee leaves able to write a structured prompt that beats their starting baseline.
2. **Sampler:** every attendee has seen and tried 4 specific techniques (R-C-T-F, Few-Shot, CoT, XML + Meta-prompt) plus a 5th rescue move (Interview).
3. **Build readiness:** every attendee has a personal V4 prompt to paste into Lovable as their first move in build time.

## Non-goals

- Deep theory of LLMs or prompt engineering history
- Comparing models (Claude vs GPT vs Gemini)
- Building inside Lovable during the 45 min — that happens in build time after
- Covering every advanced technique — Self-Consistency, Tree-of-Thoughts intentionally omitted (mention only on cheat sheet for the curious)

## Deliverables

Folder: `/Users/jdfiscus/dev/tech-town/03-prompting-techniques/`

| File | Purpose | Audience |
|---|---|---|
| `slides.md` | Source markdown for the deck | JD source |
| `slides.html` | Reveal.js-style self-contained HTML deck | JD presents, shared after |
| `cheat-sheet.md` | One-page reference, all 5 techniques + templates | Audience reference |
| `cheat-sheet-printable.html` | Print-styled HTML | Print-ready |
| `cheat-sheet.pdf` | PDF export of printable HTML | Email/QR distribution |
| `fallback-projects.md` | 5-6 starter project prompts for attendees without an idea | Distributed at start via volunteer cards / QR |
| `prompt-template.md` | The V4 prompt structure, copy-paste-ready | Audience takeaway |
| `interview-template.md` | Full interview-technique prompt + usage notes | Build-time rescue resource |
| `outline.md` | Speaker notes, timing, volunteer choreography | JD private |
| `README.md` | Folder index, how to use the assets, shareable link | JD + audience |

## The 45-Minute Beat Sheet

```
─────────────────────────────────────────────────────────────
ACT 0 — SETUP (0:00 → 0:05)  ⏱ 5 min
─────────────────────────────────────────────────────────────
0:00  Title + promise: "4 layers, one prompt, 45 min."
0:01  Logistics + build-time context:
      • ChatGPT or Claude.ai open (free is fine)
      • ONE project idea — "what I'd build if Lovable worked"
      • No idea? Red-shirt volunteer has starter cards
        (also QR → fallback-projects.md)
      • After this 45 min, you have build time (1-2 hrs).
        This session is your prep. By minute 45 you'll have
        a prompt to paste into Lovable, and then we have
        actual time to make it work, with me and volunteers
        here to help.
      • If you fall behind, watch my screen — you'll still
        get everything.
      • Floor volunteers will surface cool examples to the
        big screen between rounds.
0:03  60-sec mindset shift:
      Outcome prompts ("build me Uber") = praying
      Layered prompts = stacking context AI can't guess
      Today we stack 4 layers.

─────────────────────────────────────────────────────────────
LAYER 1 — V1: THE NAKED PROMPT (0:05 → 0:11)  ⏱ 6 min
─────────────────────────────────────────────────────────────
0:05  Slide: "Write your V1. Whatever you'd normally type."
0:06  ⌨️ AUDIENCE PROMPTS (90s)
0:08  Pencils down. JD shows his V1:
       "build me a booking app for my salon"
       → 800 lines of generic React, no business logic.
       Point: vague in → vague out.
0:10  Show-of-hands: "About that level? 🙋"
       Setup: "Your prompt is missing 4 things AI can't
       guess. We're about to add them."

─────────────────────────────────────────────────────────────
INTERLUDE — MARKDOWN IN 90 SECONDS (0:11 → 0:14)  ⏱ 3 min
─────────────────────────────────────────────────────────────
0:11  Slide: "4 markdown moves AI reads as structure."

       # Header        — major section
       - bullet         — list of things
       **bold**         — emphasis on a key word
       ```code```       — exact text or code

0:12  Why: AI parses markdown structure. Same content
       structured vs unstructured = different output quality.
       Show 5-sec before/after example.
0:13  "These 4 are all you need. Don't overthink it."

─────────────────────────────────────────────────────────────
LAYER 2 — V2: ROLE + CONTEXT + TASK + FORMAT (0:14 → 0:23)
                                                ⏱ 9 min
─────────────────────────────────────────────────────────────
0:14  Slide: R-C-T-F framework AS a markdown prompt
       # Role
       You are a senior product engineer...

       # Context
       - Salon business in Asheville
       - Solo stylist, 20 clients/week
       - Currently using paper appointment book

       # Task
       Design the booking flow data model.

       # Format
       Bullet list. Plain English. No code yet.

0:16  JD live demo: paste V1 salon prompt, rewrite as
       R-C-T-F. Run. Side-by-side with V1 output.
0:19  ⌨️ AUDIENCE UPGRADES TO V2 (3m)
0:22  Show-of-hands + floor-volunteer-surfaced example (1m)

─────────────────────────────────────────────────────────────
LAYER 3 — V3: EXAMPLES + REASONING (0:23 → 0:32)  ⏱ 9 min
─────────────────────────────────────────────────────────────
0:23  Slide: Two techniques, stacked
       • FEW-SHOT — 2-3 examples of "what good looks like"
         (15-40% accuracy boost per research)
       • CHAIN-OF-THOUGHT — "Think step-by-step first"

0:25  Why together: examples teach SHAPE, step-by-step
       teaches PROCESS. Add to V2:

       # Examples
       - Acuity booking: ...
       - Square Appointments: ...

       # Process
       Before you write anything, think step-by-step
       about what could break in the booking flow.

0:27  JD live demo (90s)
0:28  ⌨️ AUDIENCE UPGRADES TO V3 (3m)
0:31  Show-of-hands + volunteer-surfaced example (1m)

─────────────────────────────────────────────────────────────
LAYER 4 — V4: XML + META-PROMPTING (0:32 → 0:41)  ⏱ 9 min
─────────────────────────────────────────────────────────────
0:32  Slide: The pro moves
       • XML TAGS — wrap markdown sections in tags for
         models that parse them better (esp. Claude):
         <role>, <context>, <task>, <format>, <examples>
       • META-PROMPTING — paste your prompt into the AI
         and say: "What's missing? Rewrite this prompt to
         get a better result." Then run THAT.

0:34  JD live demo: wrap V3 in XML → meta-prompt it →
       watch AI improve YOUR prompt → run improved version.
       The "whoa" moment.
0:37  ⌨️ AUDIENCE UPGRADES TO V4 (3m)
0:40  Final show-of-hands + best volunteer-surfaced example (1m)

─────────────────────────────────────────────────────────────
ACT 5 — TAKEAWAY + BRIDGE TO BUILD (0:41 → 0:45)  ⏱ 4 min
─────────────────────────────────────────────────────────────
0:41  Slide: "You just stacked 4 layers.
              Cheat sheet → [QR code]"

0:42  60-sec mention: the 5th move — INTERVIEW TECHNIQUE
       (as build-time rescue, not self-teach footnote)
       "If you get stuck during build — Lovable doing
        something dumb, you don't know what to ask for
        next — flip to the interview technique on the
        cheat sheet. Ask the AI to interview YOU. That's
        how you unblock."

0:43  Bridge to build:
       "Your first move when build starts: paste your V4
        into Lovable. Then iterate. We're all here."

0:44  Q&A buffer / closing energy
0:45  End → build time begins.
─────────────────────────────────────────────────────────────
```

## Content Detail Per Layer

### V1 — Naked Prompt
- **What audience does:** write whatever they'd normally type
- **What JD shows:** his salon V1 + the generic-React garbage it produced
- **Teaching moment:** "vague in → vague out; AI can't read your mind"
- **No technique introduced** — this is the baseline pain

### Markdown Interlude
- Just 4 elements: `#`, `-`, `**`, ` ``` `
- One side-by-side example: unstructured paragraph vs structured markdown, same content
- Permission slip: "this is all you need today"

### V2 — R-C-T-F
- **Framework:** Role + Context + Task + Format
- **JD's demo prompt structure:** all 4 sections as markdown headers
- **Coaching cue during audience time:** "If you don't know what to put in Context, ask: what would a new employee need to know on day one?"
- **Volunteer help focus during this round:** unblocking people who freeze on Context

### V3 — Few-Shot + CoT
- **Few-Shot rationale:** 15-40% accuracy boost (cite the research)
- **CoT phrase:** "Think step-by-step before you write anything"
- **Stack on top of V2:** add `# Examples` and `# Process` sections
- **Coaching cue:** "Your examples don't have to be perfect. 'Something like Acuity booking' is enough."

### V4 — XML + Meta-prompting
- **XML wrapping rationale:** Claude and structured-parsing models read tags as semantic boundaries; reduces ambiguity
- **Meta-prompting demo:** the "AI improves AI" moment — paste V3 in, ask "What's missing? Rewrite this prompt to get a better result," run the result
- **Pedagogical hook:** "You don't have to be the best prompt writer in the room. You just have to use the AI to be one."

## Build-Time Bridge

The session ends at 0:45 and build time starts immediately. Continuity moves:

1. **Cheat sheet is already in their hands** (or scanned via QR)
2. **First action is pre-stated:** paste V4 into Lovable
3. **Rescue move is pre-named:** interview technique, location on cheat sheet known
4. **Floor volunteers transition role** from "collect examples" to "answer build questions"

The cheat sheet's "after V4 works, try these next" section gives 1–2 hour attendees a runway: iterate with the interview technique, try variations, ask follow-up questions in Lovable.

## Interview Technique Track

Lives in three places:

1. **Mentioned at 0:42** in the live session (60 sec, framed as build-time rescue)
2. **On the cheat sheet** as the 5th technique with a copy-paste template
3. **Full template in `interview-template.md`** with usage notes and example interview transcript

Template starter:
```
I want to build [PROJECT]. Before we write anything,
interview me about my project. Ask one question at a
time. Wait for my answer before the next question.
When you have enough to write a clear spec, summarize
back to me and we'll start.
```

## Cheat Sheet Structure (one page)

Optimized for: scan while building, find the right move fast.

1. **The 4 Layers** (top half) — each layer as a copy-paste markdown block
2. **The Interview Rescue** (bottom-left) — full template
3. **After V4 Works** (bottom-right) — 3 follow-up moves: iterate one section, ask for variations, ask AI to critique its own output
4. **Footer:** QR back to the deployed Vercel URL (`prompting.techtown.studio` or similar — see Hosting & Distribution)

## Logistics & Volunteer Choreography

### Pre-session
- Volunteers wear identifiable color (red shirts assumed; confirm)
- Each volunteer carries printed fallback project cards (1 per audience member who asks)
- QR code projected at entrance pointing to `03-prompting-techniques/README.md`

### During session
- Volunteers float during 3-min audience prompt-along moments to help individuals
- During each "pencils down" transition, **one** designated volunteer scouts for a good example and surfaces it to the AV station (mechanism: TBD — see open questions)
- Volunteers DO NOT try to share examples verbally with mics — visual surface only

### Build-time (1–2 hr after)
- Volunteers transition to floating tech support for Lovable issues
- JD floats and answers questions
- Cheat sheet is the durable reference; volunteers can point to it

## Slide Count Estimate

22–24 slides:
- Title + promise (1)
- Logistics + build context (1)
- Mindset shift (1)
- V1 prompt + diagnostic (2)
- Markdown primer (2)
- R-C-T-F intro + framework + live demo placeholder (3)
- V3 techniques + example + demo placeholder (3)
- V4 techniques + demo + the "whoa" beat (3)
- Takeaway + cheat sheet QR (1)
- Interview rescue mention (1)
- Bridge to build (1)
- Closing / Q&A (1)
- Buffer / transition slides (2-3)

## Open Questions for Show Day

These don't block spec sign-off but need answers before live execution:

1. **Volunteer-to-screen mechanism** — Slido/Mentimeter, AirPlay from volunteer phone, or doc cam? Recommend Slido for cleanest text submissions.
2. **Final URL / domain** — Vercel is the host (see Hosting & Distribution); the short, typeable URL still needs confirmation (e.g., `prompting.techtown.studio` requires owning techtown.studio).
3. **Volunteer count and briefing** — how many volunteers, when do they get briefed on the round-by-round choreography?
4. **AV verification** — markdown + XML in live demo will need readable font sizes on a big screen; verify projector resolution and font baseline.
5. **Backup project ideas in fallback-projects.md** — needs final list approved by JD. Suggested: yoga studio booking, real estate agent CRM, tutoring marketplace, small-batch food ordering, freelancer portfolio + invoicing, local pet-sitter directory.

## Success Criteria

By minute 45, the workshop succeeds if:

1. ≥80% of attendees raise their hand at the final "is yours noticeably better?" poll
2. Every attendee has a V4 prompt in their clipboard or notes
3. Cheat sheet has been distributed (digital or print) to anyone who wants one
4. Build time starts with a clear first action that doesn't require asking JD
5. The interview technique is known and locatable as a rescue move

## Hosting & Distribution

- **Deploy target:** Vercel, auto-deployed from the `03-prompting-techniques/` folder via GitHub push
- **What ships:** the reveal.js `slides.html`, `cheat-sheet-printable.html`, `cheat-sheet.pdf`, `prompt-template.md`, `interview-template.md`, `fallback-projects.md`, and `README.md` as a static landing page
- **Domain:** custom domain TBD (e.g., `prompting.techtown.studio` or `techtown.studio/prompting`) — confirm before generating QR
- **QR code:** generated post-deploy pointing at the final URL; embedded in the takeaway slide and printed on volunteer fallback cards
- **Iteration window:** you can push slide tweaks up until showtime since Vercel auto-deploys

## What This Spec Does Not Cover

Defers to writing-plans implementation:
- Specific markdown structure of `slides.md` (which slide engine, what theme)
- Visual design tokens for the deck (colors, fonts, layouts)
- PDF generation toolchain for the cheat sheet
- Vercel project configuration (`vercel.json`, build settings) — to be decided during implementation
- QR code generator choice
- Pre-session attendee email / setup instructions
