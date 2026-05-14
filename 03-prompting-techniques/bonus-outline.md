# Speaker Outline — Bonus Modules

**Format:** Optional deep-dives, run after the ~47-min core workshop, for sessions that go ~2 hours.
**Deck:** `bonus.html` — 1 menu slide + 5 modules (36 slides total)
**How to run it:** Open `bonus.html`. The menu slide is home base. Pick a module by show of
interest or in response to a question. The `≡ Menu` button (top-left) jumps back to the menu.
Modules are independent — run one, three, or all five, in any order.

By bonus-module time, volunteers are already in floating build-support mode — no volunteer
choreography here.

---

## Module 1 — When the build breaks (slides 2–9, ~12 min)

**Run this when:** someone asks "Lovable did X weird thing, what do I do?" or the room is
clearly about to hit build problems.

- **Slide 2 (Hook):** "Everyone hits this. The fix isn't coding — it's diagnosing."
- **Slide 3 (Concept):** Don't rage-prompt. The AI isn't broken, it's missing info. Same
  lesson as V1.
- **Slide 4 (How-to):** Three parts of a bug report — Expected / Actual / On screen. Paste
  full error text, never summarize it.
- **Slide 5 (Copy-paste):** The bug-report prompt. Point out the "tell me likely causes
  before changing anything" line — that stops the AI from thrashing.
- **Slide 6 (Interview, setup):** When you can't even name the problem, make the AI
  interview you. Callback to the core deck's 5th move.
- **Slide 7 (Copy-paste):** The interview template. "The summary it gives back is your new
  prompt."
- **Slide 8 (Fresh chat):** Context-window callback. Name the three signs a chat has gone
  bad. Fix: new chat + V4 + a 3-line summary.
- **Slide 9 (Recap):** Four bullets. Send them to the menu.

## Module 2 — After V4 works: iterating (slides 10–16, ~11 min)

**Run this when:** people have working apps and ask "how do I change it without breaking it?"

- **Slide 10 (Hook):** "It works. Don't break it." Name the fear of touching a working app.
- **Slide 11 (Concept):** Small, reversible changes. One thing at a time. Tell it what NOT
  to touch.
- **Slide 12 (How-to):** Three moves — change one section, layer one feature, ask for
  variations. Each prompt = one move.
- **Slide 13 (Copy-paste):** The "change one thing" template. The "# Leave alone" section is
  the important part.
- **Slide 14 (Design):** Design feedback = a vibe + a reference, not "make it better." Walk
  the vague vs. usable columns.
- **Slide 15 (Worked example):** Salon app — "make it better" vs. the scoped cancellation-
  policy change.
- **Slide 16 (Recap):** Four bullets. Send them to the menu.

## Module 3 — Data & backends (slides 17–23, ~12 min)

**Run this when:** someone asks "why doesn't my app remember anything?" or mentions
databases, logins, or saving data.

- **Slide 17 (Hook):** "The wall everyone hits — refresh the page and it's all gone."
- **Slide 18 (Concept):** A backend is a place your app saves stuff so it's there tomorrow.
  Front vs. back, plain terms.
- **Slide 19 (Supabase):** Name-drop. They don't configure it — they recognize it and
  request it.
- **Slide 20 (How-to):** Ask in business terms — saving data, accounts, forms that stick.
- **Slide 21 (Copy-paste):** The backend-request template — what to save / who sees it /
  where it shows.
- **Slide 22 (Worked example):** The same template filled in for the salon app.
- **Slide 23 (Recap):** Four bullets. Send them to the menu.

## Module 4 — Reading prompts well (slides 24–29, ~10 min)

**Run this when:** someone used voice + meta-prompt and asks "how do I know if the prompt
the AI wrote is good?"

- **Slide 24 (Hook):** "Writing prompts is easy. Reading them is the skill." Callback to the
  core deck's voice + meta-prompt slide.
- **Slide 25 (Concept):** When the AI writes the prompt, you're the editor. Confident ≠
  correct.
- **Slide 26 (How-to):** The 4 layers as a review checklist — Role, Context, Task, Format.
- **Slide 27 (Spotting trouble):** Generic filler, missing business facts, vague tasks. "If
  it fits any business, it's not done."
- **Slide 28 (Worked example):** An AI-written prompt vs. the edited version — same skeleton,
  real business facts added.
- **Slide 29 (Recap):** Four bullets. Send them to the menu.

## Module 5 — More techniques (slides 30–36, ~12 min)

**Run this when:** the room is advanced or asks "what else is there?" Good closer module.

- **Slide 30 (Hook):** "Four more moves for when you're ready." Not day-one material.
- **Slide 31 (Chaining):** Build big things in steps, not one mega-prompt.
- **Slide 32 (Constraints):** Tell the AI what NOT to do — it loves to over-build.
- **Slide 33 (Self-critique):** Give it a rubric, make it grade its own work before showing
  you.
- **Slide 34 ("3 approaches"):** Ask for options + tradeoffs before committing to a build.
- **Slide 35 (Copy-paste):** All four moves in one cheat-block.
- **Slide 36 (Recap):** Four bullets. "That's all five modules."

---

## Recovery Moves

**Only have time for one module:** run Module 1 (When the build breaks) — it's the most
universally needed and feeds straight into build time.

**Room is fading:** stop at any recap slide and send people to build. Modules are
self-contained — there's no cliffhanger.

**A question doesn't fit any module:** answer it briefly, then point to the cheat sheet and
move on. Don't improvise a sixth module live.
