# Prompting Techniques — Bonus Modules Design Spec

**Working title:** Going Deeper — Optional Bonus Modules
**Date:** 2026-05-14
**Author:** JD Fiscus
**Folder:** `03-prompting-techniques/`
**Extends:** `2026-05-12-prompting-techniques-workshop-design.md`

---

## Overview

The core workshop is a ~47-minute V1→V4 prompt-building arc (28 slides, `slides.html`),
followed by build time. This spec adds **optional bonus content** for sessions that run
closer to 2 hours.

The structure: run the 47-minute core unchanged, then offer **five self-contained
deep-dive modules** (~10–15 min each). Attendees opt in — they can stay for a module or
peel off to start building. JD picks which module to run based on what the room asks for.

The modules double as Q&A preparation: when a question lands ("how do I connect a
database?"), JD jumps to the matching module instead of improvising.

## Audience

Same as the core workshop: ~250 fresh TechTown attendees, small-business owners and
non-technical builders using Lovable. The bonus modules assume the audience has just
completed the core arc — they know R-C-T-F, Few-Shot, Chain-of-Thought, XML, and
meta-prompting, and they have a personal V4 prompt.

## Goals

1. **Coverage for a 2-hour slot:** enough opt-in content to fill the time without
   padding the core.
2. **Question readiness:** the five modules cover the topics this audience predictably
   asks about, so JD has a prepared answer to jump to.
3. **Presenter predictability:** every module follows one fixed skeleton, so JD always
   knows where the copy-paste prompt is and can drop any module without it feeling
   incomplete.

## Non-goals

- Changing the core 28-slide deck's content or arc (one small pointer line added to the
  final slide — see Modified Files).
- Refreshing `cheat-sheet.pdf` / `cheat-sheet.md` — the one-page sheet stays as-is. It is
  show-day-ready and bonus content lives only in `bonus.html`. A cheat-sheet refresh, if
  wanted, is a separate pass.
- A separate written Q&A prep doc — the modules themselves are the preparation.
- Deep LLM theory or model comparisons.

## Approach

**Approach A — Uniform module template** (chosen). Every module follows the same 6–8
slide skeleton. Predictable under live conditions: the copy-paste prompt is always in the
same position, any module can be dropped cleanly, and the recap slide doubles as a
2-minute lightning version.

Rejected: per-module custom structure (less predictable when jumping around live in front
of 250 people), and uniform-plus-explicit-lightning-slide (the recap slide already serves
that purpose; extra slides not worth it).

## Deliverables

Folder: `/Users/jdfiscus/dev/tech-town/03-prompting-techniques/`

### New files

| File | Purpose | Audience |
|---|---|---|
| `bonus.html` | The bonus deck — menu slide + 5 modules, ~36 slides | JD presents, shared after |
| `bonus-outline.md` | Speaker notes for the modules | JD private |

### Modified files

| File | Change |
|---|---|
| `index.html` | Add a card linking to `bonus.html` ("Going deeper? Bonus modules.") |
| `slides.html` | Final core slide (28, Q&A) gets one line: "Want more? Bonus modules at the same URL." |

## `bonus.html` Architecture

A self-contained HTML deck, same engine as `slides.html`: hand-rolled
`<div class="slide" data-slide="N">` blocks with JS class-swap navigation, arrow keys +
space to advance.

### Slide 1 — Menu

Five clickable cards, one per module. Clicking a card jumps directly to that module's
first slide via the existing `show(n)` navigation function. This is the live-control
surface: the room asks about databases, JD clicks "Data & backends."

### Slides 2–36 — Modules

Five contiguous module blocks, each following the uniform skeleton. Linear arrow/space
navigation works within and across modules.

### Navigation additions over the core deck

- **"≡ Menu" button:** a persistent small button (top-left, styled like the existing
  `.copy-btn`) on every module slide. Clicking it returns to slide 1 (the menu).
- Everything else matches the core deck's navigation behavior.

### Shared with the core deck

- TechTown CSS tokens: `--primary: #0c5449`, `--accent: #ffcc33`, `--secondary: #25524a`,
  `--dark: #1a1a1a`, Roboto + Roboto Mono.
- The `.slide` structure and class-swap navigation pattern.
- Copy-to-clipboard buttons on every `<pre>` block (same JS pattern as `slides.html`).
- Persistent URL footer on every slide: `prompting-techniques.vercel.app`.

## Uniform Module Skeleton (Approach A)

Every module follows this fixed slide order:

1. **Hook** — the pain or the question this module answers.
2. **Concept** — the mental model, in plain language.
3. **How-to** — the actual moves, step by step.
4. **Copy-paste prompt** — the reusable template, with a copy button.
5. **Worked example** — before/after using the salon project, for continuity with the
   core deck.
6. **Recap** — the 2-minute version; doubles as the lightning summary.

Modules run 7–8 slides where the how-to or example needs room (e.g., Module 1 has two
copy-paste prompts and an extra slide). The skeleton *order* is fixed even when slide
*count* varies — the copy-paste prompt always follows the how-to.

**Module 5 is the deliberate exception.** It is a sampler of four techniques rather than
one technique deepened, so its body slides are four technique slides instead of a single
concept/how-to/worked-example run. It still opens with a Hook, still carries a copy-paste
slide in the back third, and still closes with a Recap — so it reads as part of the same
deck — but it does not pretend to fit the single-technique skeleton.

## Module Content

### Module 1 — When the build breaks (~8 slides)

Debugging workflow. Gets an extra slide because it carries two copy-paste prompts.

1. Hook — "Lovable did something weird. Now what?" Everyone hits this.
2. Concept — Don't rage-prompt. Diagnose. The AI isn't broken; it's missing info — the
   core lesson, applied to bugs.
3. How-to — Describe a bug well: what you expected / what happened / what's on screen.
   Specifics, not "it's broken."
4. Copy-paste — the bug-report prompt template.
5. The interview technique, done fully — paste the interview prompt, the AI interviews
   you, you answer. This is the full treatment of the core deck's 5th move.
6. Copy-paste — the interview template (matches `interview-template.md`).
7. When to start a fresh chat — context-window callback: signs the chat has gone bad,
   carry your V4 + a short summary into a new chat.
8. Recap.

### Module 2 — After V4 works: iterating (~7 slides)

1. Hook — "It works. Don't break it." The fear of touching a working app.
2. Concept — Small, reversible changes. One thing at a time. You can always ask it to
   undo.
3. How-to — Change one section at a time; layer features one at a time; ask for
   variations.
4. Copy-paste — the "change one thing" prompt template.
5. Prompting for design/styling — describing a vibe ("more premium," "more trustworthy"),
   colors, layout.
6. Worked example — salon app: "add a cancellation policy section" done well vs "make it
   better" done badly.
7. Recap.

### Module 3 — Data & backends (~7 slides)

1. Hook — "The wall everyone hits: making your app remember things."
2. Concept — What a backend is, in plain terms: a place your app saves stuff so it's
   still there tomorrow. You don't need to understand it — you need to ask for it.
3. Supabase — Lovable's built-in backend. Name-drop so attendees recognize it when
   Lovable mentions it; they request it, they don't configure it.
4. How-to — Prompt for it: "add a database so [X] is saved." Auth in plain terms: "users
   can create an account and log in." Forms that save.
5. Copy-paste — the backend-request prompt template.
6. Worked example — salon app: "appointments should be saved and visible to the stylist
   tomorrow."
7. Recap.

### Module 4 — Reading prompts well (~6 slides)

1. Hook — "Writing prompts is easy. Reading them is the skill." Callback to the core
   deck's voice + meta-prompt slide.
2. Concept — When the AI writes your prompt (voice → meta-prompt), you become the editor.
   You have to vet it.
3. How-to — The 4 layers as a review checklist: Role there? Context specific or generic?
   Task single and clear? Format stated?
4. Spotting trouble — Generic filler, missing business facts, vague tasks. What "bad"
   looks like.
5. Worked example — An AI-written prompt with gaps, marked up, then fixed (before/after).
6. Recap.

### Module 5 — More techniques (~7 slides)

Curated builder-focused set — the highest-value techniques not in the core arc.

1. Hook — "Four more moves for when you're ready."
2. Prompt chaining — Build big things in steps, not one mega-prompt (data model, then UI,
   then polish).
3. Constraints / negative prompting — "Don't over-build, keep it simple, no features I
   didn't ask for." Reining the AI in.
4. Self-critique with a rubric — "Grade your output against these criteria, then improve
   it." Give it a checklist.
5. "Give me 3 approaches" — Get options with tradeoffs before committing.
6. Copy-paste — a combined cheat-block with all four techniques.
7. Recap.

**Total:** 1 menu slide + 35 module slides = ~36 slides in `bonus.html`.

## Speaker Notes — `bonus-outline.md`

Mirrors the structure of the core `outline.md` but organized by module rather than by
clock time (modules are opt-in and order is not fixed). For each module:

- A one-line "when to run this" trigger (the kind of question that should send JD here).
- Per-slide Say / Cue notes.
- An approximate run time (10–15 min).

No volunteer choreography section — by bonus-module time, volunteers are already in
floating build-support mode (per the core spec).

## Live Operation

- After the core deck's final slide, JD opens `bonus.html`. The menu slide is the home
  base.
- JD picks a module based on the room — either by show of interest or in response to a
  question.
- The "≡ Menu" button lets JD bounce back to the menu between modules.
- Attendees who want to start building just leave; the modules are opt-in.
- Modules are independent — JD can run one, three, or all five, in any order, and skip
  freely.

## Hosting & Distribution

- `bonus.html` deploys with the rest of the folder to Vercel (same auto-deploy on push).
- Reachable at `prompting-techniques.vercel.app/bonus`.
- Linked from the landing page (`index.html`) so attendees can revisit during build time.
- No new QR code — the existing QR points at the landing page, which now links to
  `bonus.html`.

## Success Criteria

1. JD can run any module standalone, in any order, without setup or dependency on another
   module.
2. Every module has a copy-paste prompt in a fixed, predictable slide position.
3. `bonus.html` matches the core deck's look, navigation feel, and shared features (copy
   buttons, URL footer).
4. The menu slide lets JD jump to any module in one click.
5. The core `slides.html` arc is unchanged except for the single pointer line on slide 28.

## What This Spec Does Not Cover

Defers to writing-plans implementation:

- Exact slide markup and per-slide copy.
- Final wording of each copy-paste prompt template.
- The worked-example before/after content for Modules 2, 3, and 4.
- The "≡ Menu" button's exact styling and placement values.
- Whether modules need any intra-module sub-navigation beyond linear advance (default:
  no).
