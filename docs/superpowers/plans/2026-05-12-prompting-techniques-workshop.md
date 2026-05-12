# Prompting Techniques Workshop Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build all assets for the 45-min "Stop Praying, Start Stacking" workshop — slide deck, cheat sheet (HTML + PDF), prompt templates, fallback projects, speaker notes, QR code, and Vercel deployment.

**Architecture:** Static-site workshop folder mirroring the pattern of `01-prompting/`. Content artifacts (markdown templates, cheat sheet) are authored first; speaker outline and slides reference them; print/PDF artifacts derive from cheat sheet; QR points at deployed URL; Vercel hosts the folder as a static site.

**Tech Stack:** Plain HTML/CSS/JS (self-contained slide deck, no build framework), TechTown brand tokens reused from `01-prompting/slides.html`, headless Chrome for PDF export, `qrcode` CLI for QR generation, Vercel for hosting.

**Source spec:** `docs/superpowers/specs/2026-05-12-prompting-techniques-workshop-design.md` — read this before starting; it has the full beat sheet, content details per layer, and success criteria.

---

## File Structure

All paths relative to `/Users/jdfiscus/dev/tech-town/03-prompting-techniques/`:

```
03-prompting-techniques/
├── README.md                       # Folder index + shareable link, audience-facing
├── .gitignore                      # node_modules, .vercel, .DS_Store
├── vercel.json                     # Vercel static config + clean URLs
├── index.html                      # Landing page with links to slides + cheat sheet
├── slides.html                     # Self-contained reveal-style HTML deck (authored directly, no intermediate .md — matches 01-prompting/ precedent)
├── outline.md                      # Speaker notes + timing + volunteer choreography (JD-private)
├── cheat-sheet.md                  # One-page reference, markdown master
├── cheat-sheet-printable.html      # Print-styled one-page HTML
├── cheat-sheet.pdf                 # Exported PDF for QR/email distribution
├── prompt-template.md              # V4 prompt structure, copy-paste-ready
├── interview-template.md           # Interview-technique template + usage notes
├── fallback-projects.md            # 6 starter project prompts for stuck attendees
├── qr.png                          # QR code pointing to deployed URL
└── assets/
    └── styles.css                  # Optional: extracted brand tokens (currently inline)
```

**Brand reference:** `/Users/jdfiscus/dev/tech-town/01-prompting/slides.html:10-80` for CSS tokens (`--primary: #0c5449`, `--accent: #ffcc33`, etc.). Match the visual language.

---

## Task 1: Scaffold folder, README, and .gitignore

**Files:**
- Create: `03-prompting-techniques/README.md`
- Create: `03-prompting-techniques/.gitignore`

- [ ] **Step 1: Create the folder**

Run:
```bash
mkdir -p /Users/jdfiscus/dev/tech-town/03-prompting-techniques/assets
```

- [ ] **Step 2: Write `README.md`**

```markdown
# Prompting Techniques — TechTown Workshop

**Format:** 45 min interactive + 1–2 hr build time
**Audience:** Lovable builders, fresh TechTown crowd

## Files

- [`slides.html`](./slides.html) — the workshop deck
- [`cheat-sheet.pdf`](./cheat-sheet.pdf) — one-page printable reference
- [`prompt-template.md`](./prompt-template.md) — copy-paste V4 prompt
- [`interview-template.md`](./interview-template.md) — build-time rescue prompt
- [`fallback-projects.md`](./fallback-projects.md) — starter project ideas

## How to use

1. Open `slides.html` in a browser, full-screen, advance with arrow keys
2. Print `cheat-sheet-printable.html` for in-person handouts (or distribute via QR)
3. Audience pastes the V4 prompt-template into Lovable during build time

## Run / deploy

This folder deploys to Vercel as a static site. Push to main and Vercel auto-deploys.
```

- [ ] **Step 3: Write `.gitignore`**

```
.DS_Store
.vercel/
node_modules/
*.log
```

- [ ] **Step 4: Commit**

```bash
git add 03-prompting-techniques/README.md 03-prompting-techniques/.gitignore
git commit -m "scaffold: 03-prompting-techniques folder + README"
```

---

## Task 2: Write `fallback-projects.md`

**Files:**
- Create: `03-prompting-techniques/fallback-projects.md`

- [ ] **Step 1: Write the file**

```markdown
# Starter Project Ideas

For attendees who don't have a project idea in mind. Pick one and use it as your "thing I'd build if Lovable just worked" throughout the 4 layers.

---

## 1. Yoga Studio Booking
You run a small yoga studio with 3 instructors and 20 weekly classes. Right now bookings are managed in a spreadsheet and texts. You want a public site where clients book a class, pay, and get an email confirmation.

## 2. Real Estate Agent CRM
You're a solo real estate agent juggling 30 active leads. Right now everything lives in your head and a Google Sheet. You want a private dashboard where you can see every lead, their status, last contact date, and next action.

## 3. Tutoring Marketplace
You run a small tutoring business with 8 tutors covering math, reading, and SAT prep. Parents currently text you to schedule. You want a parent-facing booking site and a tutor-facing schedule view.

## 4. Homemade Hot Sauce Ordering
You make and sell small-batch hot sauce out of your kitchen. You take orders via Instagram DMs. You want a simple ordering site that shows the current week's bottles, lets people order, and emails you the list every Friday.

## 5. Freelancer Portfolio + Invoicing
You're a freelance designer with 5 active clients. You want a public portfolio site AND a private invoicing tool — issue an invoice, mark paid, see what's outstanding.

## 6. Local Pet-Sitter Directory
You want to build a directory of pet sitters in your town. Sitters create a profile. Pet owners browse, filter by service type, and message sitters directly. Like a mini Rover for one zip code.

---

**Pick one. Use it as YOUR project for the whole 45 min. You'll walk out with a V4 prompt for that specific idea.**
```

- [ ] **Step 2: Commit**

```bash
git add 03-prompting-techniques/fallback-projects.md
git commit -m "content: fallback project ideas for attendees without a project"
```

---

## Task 3: Write `prompt-template.md` (the V4 reference)

**Files:**
- Create: `03-prompting-techniques/prompt-template.md`

- [ ] **Step 1: Write the file**

```markdown
# V4 Prompt Template

This is the structure you build to by minute 45. Fill in the bracketed sections with YOUR project details. The structure is what makes it work — don't skip sections.

---

## Copy-paste template

```
<role>
You are a senior product engineer who builds small business apps.
You ask clarifying questions when context is missing.
You explain decisions in plain English before writing code.
</role>

<context>
- Business: [WHAT THE BUSINESS IS]
- Owner: [WHO YOU ARE — solo? team?]
- Current state: [HOW IT WORKS TODAY]
- Constraints: [BUDGET / TIME / TECH LIMITS]
- Success looks like: [WHAT "DONE" MEANS FOR YOU]
</context>

<task>
[THE SPECIFIC THING YOU WANT — not the whole app, the next step]
</task>

<format>
- [HOW THE OUTPUT SHOULD COME BACK]
- [LIST? CODE? PLAIN ENGLISH? DIAGRAM?]
- [SHORT OR LONG?]
</format>

<examples>
- [ONE EXAMPLE OF SOMETHING SIMILAR — e.g., "the booking flow on Acuity"]
- [ANOTHER EXAMPLE — "the messaging UI in Slack"]
</examples>

<process>
Before you write anything, think step-by-step about what could go wrong
with this approach. Then write the result.
</process>
```

---

## How to use it in Lovable

1. Paste the whole template into Lovable's chat
2. Lovable will likely ignore the XML tags visually but parse them as structure
3. If output is still too generic, run the **meta-prompt step**:
   - Paste your filled template back in
   - Ask: "What's missing from this prompt? Rewrite it to get a better result."
   - Run THAT version

## When it's working

You'll get back: clarifying questions OR a structured plan that mirrors your context. That's the signal.

## When it's not working

Your context section is probably too thin. Add more business specifics. AI can't guess what makes your business different.
```

- [ ] **Step 2: Commit**

```bash
git add 03-prompting-techniques/prompt-template.md
git commit -m "content: V4 prompt template with role/context/task/format/examples"
```

---

## Task 4: Write `interview-template.md`

**Files:**
- Create: `03-prompting-techniques/interview-template.md`

- [ ] **Step 1: Write the file**

```markdown
# Interview Technique

The rescue move. Use this when you don't know what to ask for next, when Lovable is stuck, or when your idea is too vague to specify.

---

## The prompt

```
I want to build [PROJECT, 1-2 SENTENCES].

Before we write anything, interview me about my project.
Ask one question at a time. Wait for my answer before
the next question. Don't ask multiple questions at once.

When you have enough to write a clear spec for the next
step, summarize what you heard back to me, and we'll
start there.
```

---

## How it works

You're flipping the dynamic. Instead of you trying to write the perfect prompt, the AI extracts the context out of your head — one question at a time.

This works because **YOU know things the AI can't guess**:
- Your business model
- Your customers' quirks
- Your constraints
- Your existing systems
- What you've already tried

## Example interview (abridged)

> **You:** I want to build a booking system for my salon. Interview me first.
>
> **AI:** Got it. First question: are you the only person taking bookings, or do you have other staff who need to manage their own schedules?
>
> **You:** Just me. Solo stylist.
>
> **AI:** OK. Do clients book a specific service (like "haircut" vs "color") or a generic time slot?
>
> **You:** Specific service. Different services take different time.
>
> **AI:** How do you currently handle cancellations? Is there a fee?
>
> **You:** No fee yet, but I want to add one for under-24-hour cancels.
>
> [... 5-10 more questions ...]
>
> **AI:** Here's what I heard: solo stylist, services with variable duration, public booking, you want a 24-hour cancel policy with a fee, email confirmations, no payment up front. Want to start with the booking flow first or the cancel policy?

## When to use it

- **Stuck during build:** Lovable produced something dumb and you don't know how to redirect
- **Vague idea:** You know you want something but can't describe it precisely
- **Starting fresh:** Better starting point than a one-shot V4 prompt
- **After V4 fails:** When your detailed prompt still gives mediocre output, the interview surfaces what you forgot to include

## Tip

If the AI asks two questions at once, interrupt: "One at a time, please." It'll comply.
```

- [ ] **Step 2: Commit**

```bash
git add 03-prompting-techniques/interview-template.md
git commit -m "content: interview-technique rescue template + usage notes"
```

---

## Task 5: Write `cheat-sheet.md`

**Files:**
- Create: `03-prompting-techniques/cheat-sheet.md`

- [ ] **Step 1: Write the file**

```markdown
# Prompting Cheat Sheet

**One page. Five techniques. Built for build time.**

---

## THE 4 LAYERS

### Layer 1 — V1: Just ask
Whatever you'd normally type. Almost always too vague.

### Layer 2 — V2: Role + Context + Task + Format

```
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
```

### Layer 3 — V3: Add Examples + Reasoning

Stack on top of V2:

```
# Examples
- Something similar that works (e.g., "booking flow on Acuity")
- Another reference

# Process
Before you write anything, think step-by-step about what
could break with this approach.
```

### Layer 4 — V4: XML Tags + Meta-Prompt

Wrap each section in tags:
```
<role>...</role>
<context>...</context>
<task>...</task>
<format>...</format>
<examples>...</examples>
```

Then **meta-prompt**:
```
Here's my prompt. What's missing? Rewrite it to get a
better result.
```
Run the AI's rewritten version.

---

## RESCUE MOVE — INTERVIEW TECHNIQUE

When you're stuck or vague:

```
I want to build [PROJECT]. Before we write anything,
interview me about my project. Ask one question at a
time. Wait for my answer. When you have enough,
summarize back and we'll start.
```

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
```

- [ ] **Step 2: Commit**

```bash
git add 03-prompting-techniques/cheat-sheet.md
git commit -m "content: one-page cheat sheet with 4 layers + interview rescue"
```

---

## Task 6: Write `outline.md` (speaker notes)

**Files:**
- Create: `03-prompting-techniques/outline.md`

- [ ] **Step 1: Write the file**

Copy the full beat sheet from the spec (`docs/superpowers/specs/2026-05-12-prompting-techniques-workshop-design.md` section "The 45-Minute Beat Sheet" and "Content Detail Per Layer"). Then add speaker cues per beat. Structure:

```markdown
# Speaker Outline — Prompting Techniques Workshop

**Total time:** 45 min + 1–2 hr build time after
**Audience:** ~250, fresh TechTown crowd, building with Lovable

---

## 0:00 — Title Slide

**Say:** "Welcome. By the end of the next 45 minutes you'll have a prompt that's 4 layers better than the one you'd write today. And then you'll have time to actually use it in Lovable."

**Cue:** Advance after ~30 sec.

---

## 0:01 — Logistics

**Say:** "Open ChatGPT or Claude.ai. Free is fine. Think of ONE project — the thing you'd build if Lovable just worked. No idea? Look for a red-shirt volunteer; they have starter cards. Or scan this QR."

**Cue:** Point to QR. Wait 30 sec for laptops to open.

**Say:** "If you fall behind at any point, just watch my screen. You'll still walk out with the prompt."

**Cue:** Advance.

---

## 0:03 — Mindset Shift

**Say:** "Most people pray when they prompt. 'Build me Uber.' That's a wish. Today we're stacking. Each layer is something the AI can't guess about your business."

**Cue:** Advance to Layer 1.

---

[CONTINUE FOR EVERY BEAT FROM 0:05 TO 0:45 — see spec beat sheet]

---

## Recovery Moves

**Running 5 min behind:**
- Cut V3 audience prompt time to 2 min instead of 3
- Skip the volunteer-surfaced example on V3 layer
- Compress takeaway to 2 min

**Running 5 min ahead:**
- Add live interview-technique demo at 0:40 (audience watches AI interview JD)
- Extend Q&A buffer

**Audience is lost / slow:**
- Skip V4 meta-prompt step, end at XML wrap
- Tell them: "The cheat sheet has V4. Get V3 solid for build time."

**Tech failure mid-demo:**
- Use pre-prepared screenshots saved in `assets/` (capture day-of)
- Keep moving; the layer concept lands even without live AI response

---

## Volunteer Briefing (give this 15 min before start)

1. Hand out fallback project cards to anyone looking lost in first 60 sec
2. During each 3-min audience prompt time, float and unblock individuals
3. Watch for good examples on attendee screens
4. During "pencils down" transition, snap a photo of one good example with your phone
5. Send to AV station via [mechanism — Slido/AirDrop/doc cam — confirm before show day]
6. DO NOT use mics to ask audience to speak — visual surface only
7. During build time, transition to floating tech support
```

- [ ] **Step 2: Fill in all beats from 0:05 to 0:45**

Open the spec at `docs/superpowers/specs/2026-05-12-prompting-techniques-workshop-design.md` and find the section "The 45-Minute Beat Sheet" (around line 54). Author one outline.md section per beat using the same format as the 0:00–0:03 examples above. Required per beat:

- Time stamp (e.g., `## 0:14 — Layer 2 R-C-T-F`)
- Which slide number is on screen (e.g., "Slide 9")
- **Say:** what JD says (1-3 sentences, conversational, first-person)
- **Cue:** stage direction (advance, wait, poll, demo)
- **Volunteer cue:** if applicable, what floor volunteers should be doing

Beats to author (15 total):
0:05 Layer 1 V1, 0:08 V1 diagnosis, 0:11 Markdown primer, 0:14 R-C-T-F framework, 0:16 V2 demo, 0:19 V2 audience, 0:22 V2 share-back, 0:23 Layer 3 intro, 0:26 V3 example, 0:28 V3 audience, 0:31 V3 share-back, 0:32 Layer 4 intro, 0:34 V4 demo, 0:37 V4 audience, 0:40 V4 share-back, 0:41 Cheat sheet QR, 0:42 Interview rescue, 0:43 Bridge to build, 0:44 Q&A, 0:45 End.

- [ ] **Step 3: Commit**

```bash
git add 03-prompting-techniques/outline.md
git commit -m "content: speaker outline with beat-by-beat cues + recovery moves"
```

---

## Task 7: Build `slides.html` skeleton + Act 0 (slides 1-4)

**Files:**
- Create: `03-prompting-techniques/slides.html`

- [ ] **Step 1: Create the HTML skeleton with CSS**

Reference: copy CSS tokens and slide structure pattern from `/Users/jdfiscus/dev/tech-town/01-prompting/slides.html:10-200`.

Write `slides.html` starting with:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prompting Techniques — TechTown Start Studio</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700;900&family=Roboto+Mono:wght@400;500&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #0c5449;
            --accent: #ffcc33;
            --secondary: #25524a;
            --light: #f5f5f5;
            --dark: #1a1a1a;
            --white: #ffffff;
            --gradient-primary: linear-gradient(135deg, #0c5449 0%, #25524a 100%);
            --gradient-accent: linear-gradient(135deg, #ffcc33 0%, #f0b000 100%);
            --gradient-dark: linear-gradient(135deg, #1a1a1a 0%, #25524a 100%);
            --radius: 10px;
            --shadow: 0 4px 20px rgba(0, 0, 0, 0.15);
        }
        * { margin: 0; padding: 0; box-sizing: border-box; }
        html, body { height: 100%; font-family: 'Roboto', sans-serif; background: var(--dark); overflow: hidden; }
        .slides-container { width: 100%; height: 100%; position: relative; }
        .slide { position: absolute; top: 0; left: 0; width: 100%; height: 100%; display: none; flex-direction: column; padding: 60px 80px; background: var(--gradient-primary); color: var(--white); opacity: 0; transition: opacity 0.4s ease; }
        .slide.active { display: flex; opacity: 1; }
        .slide-header { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 40px; }
        .slide-content { flex: 1; display: flex; flex-direction: column; justify-content: center; }
        .slide-footer { display: flex; justify-content: space-between; align-items: center; margin-top: 40px; font-size: 14px; opacity: 0.7; }
        h1 { font-size: 64px; font-weight: 900; margin-bottom: 24px; }
        h2 { font-size: 48px; font-weight: 700; margin-bottom: 20px; }
        h3 { font-size: 32px; font-weight: 500; margin-bottom: 16px; color: var(--accent); }
        p, li { font-size: 24px; line-height: 1.5; margin-bottom: 12px; }
        code, pre { font-family: 'Roboto Mono', monospace; background: rgba(0,0,0,0.3); padding: 4px 8px; border-radius: 4px; font-size: 20px; }
        pre { padding: 20px; overflow-x: auto; white-space: pre-wrap; }
        .accent { color: var(--accent); }
        .nav { position: fixed; bottom: 20px; right: 20px; display: flex; gap: 10px; z-index: 100; }
        .nav button { background: var(--accent); color: var(--dark); border: none; padding: 10px 16px; border-radius: 4px; cursor: pointer; font-weight: 700; }
    </style>
</head>
<body>
    <div class="slides-container">
        <!-- SLIDES GO HERE -->
    </div>
    <div class="nav">
        <button onclick="prev()">←</button>
        <button onclick="next()">→</button>
    </div>
    <script>
        let current = 1;
        const total = document.querySelectorAll('.slide').length;
        function show(n) {
            document.querySelectorAll('.slide').forEach(s => s.classList.remove('active'));
            const slide = document.querySelector(`[data-slide="${n}"]`);
            if (slide) slide.classList.add('active');
        }
        function next() { if (current < total) { current++; show(current); } }
        function prev() { if (current > 1) { current--; show(current); } }
        document.addEventListener('keydown', e => {
            if (e.key === 'ArrowRight' || e.key === ' ') next();
            if (e.key === 'ArrowLeft') prev();
        });
        show(1);
    </script>
</body>
</html>
```

- [ ] **Step 2: Insert slide 1 — Title**

Add inside `<div class="slides-container">`:

```html
<div class="slide active" data-slide="1">
    <div class="slide-content" style="justify-content: center; text-align: center;">
        <h1>Stop Praying,<br><span class="accent">Start Stacking</span></h1>
        <h3>4 Layers to a Lovable-Ready Prompt</h3>
        <p style="margin-top: 60px; opacity: 0.8;">JD Fiscus &middot; TechTown Start Studio</p>
    </div>
    <div class="slide-footer">
        <span>1 / 24</span>
    </div>
</div>
```

- [ ] **Step 3: Insert slide 2 — The Promise / Logistics**

```html
<div class="slide" data-slide="2">
    <div class="slide-header"><h2>Before we start</h2></div>
    <div class="slide-content">
        <ul>
            <li>Open <strong>ChatGPT</strong> or <strong>Claude.ai</strong> (free is fine)</li>
            <li>Think of <strong>ONE project</strong> — "what I'd build if Lovable worked"</li>
            <li>No idea? Red-shirt volunteer has cards (or scan QR)</li>
            <li>Fall behind? <strong>Watch my screen.</strong> You'll still get everything.</li>
        </ul>
        <p style="margin-top: 40px;"><span class="accent">After this 45 min → 1-2 hr build time.</span> This session is your prep.</p>
    </div>
    <div class="slide-footer"><span>2 / 24</span></div>
</div>
```

- [ ] **Step 4: Insert slide 3 — Mindset Shift**

```html
<div class="slide" data-slide="3">
    <div class="slide-header"><h2>Outcome prompts = praying</h2></div>
    <div class="slide-content">
        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 40px;">
            <div>
                <h3>Outcome</h3>
                <p>"Build me Uber"</p>
                <p>"Make my app secure"</p>
                <p>"Add user auth"</p>
            </div>
            <div>
                <h3>Layered</h3>
                <p>Stack 4 things AI can't guess</p>
                <p>Role + Context + Task + Format</p>
                <p>Then examples, reasoning, structure</p>
            </div>
        </div>
        <p style="margin-top: 40px;" class="accent">Today we stack 4 layers.</p>
    </div>
    <div class="slide-footer"><span>3 / 24</span></div>
</div>
```

- [ ] **Step 5: Insert slide 4 — V1 prompt-along instruction**

```html
<div class="slide" data-slide="4">
    <div class="slide-header"><h2>Layer 1 — Write your V1</h2></div>
    <div class="slide-content">
        <h3>Whatever you'd normally type.</h3>
        <p>About your project. 60–90 seconds.</p>
        <p style="margin-top: 40px; opacity: 0.7;">Be honest. Don't try to be clever. We're establishing baseline.</p>
        <p style="margin-top: 60px;" class="accent">Type it. Run it. Watch what comes back.</p>
    </div>
    <div class="slide-footer"><span>4 / 24</span></div>
</div>
```

- [ ] **Step 6: Open `slides.html` in browser and verify**

Run:
```bash
open /Users/jdfiscus/dev/tech-town/03-prompting-techniques/slides.html
```

Expected: title slide displays, arrow keys advance through slides 1–4 cleanly. Fonts load. No layout breaks.

- [ ] **Step 7: Commit**

```bash
git add 03-prompting-techniques/slides.html
git commit -m "slides: skeleton + Act 0 (title, logistics, mindset, V1 prompt)"
```

---

## Task 8: Add slides 5-12 — V1 diagnosis, markdown primer, V2 R-C-T-F

**Files:**
- Modify: `03-prompting-techniques/slides.html`

- [ ] **Step 1: Add slide 5 — V1 diagnosis (JD's example)**

Insert before the closing `</div>` of `slides-container`:

```html
<div class="slide" data-slide="5">
    <div class="slide-header"><h2>My V1: "build me a booking app for my salon"</h2></div>
    <div class="slide-content">
        <pre style="background: rgba(0,0,0,0.4);">→ 800 lines of generic React
→ No business logic
→ Generic booking UI
→ Missing: cancellation policy, services, staff
→ I say: "that's not what I wanted"
→ AI says: "you didn't tell me"</pre>
        <p style="margin-top: 40px;" class="accent">Vague in → vague out.</p>
    </div>
    <div class="slide-footer"><span>5 / 24</span></div>
</div>
```

- [ ] **Step 2: Add slide 6 — The diagnosis / setup**

```html
<div class="slide" data-slide="6">
    <div class="slide-header"><h2>Your prompt is missing 4 things</h2></div>
    <div class="slide-content">
        <p>The AI can't guess:</p>
        <ul style="margin-top: 30px;">
            <li><strong>Role</strong> — who it should act as</li>
            <li><strong>Context</strong> — what your business actually is</li>
            <li><strong>Task</strong> — the specific next step</li>
            <li><strong>Format</strong> — how the answer comes back</li>
        </ul>
        <p style="margin-top: 40px;" class="accent">We're about to add all four. But first — one quick thing.</p>
    </div>
    <div class="slide-footer"><span>6 / 24</span></div>
</div>
```

- [ ] **Step 3: Add slide 7 — Markdown primer**

```html
<div class="slide" data-slide="7">
    <div class="slide-header"><h2>Markdown in 90 seconds</h2></div>
    <div class="slide-content">
        <p>4 moves AI reads as structure:</p>
        <pre style="margin-top: 30px;"># Header           — major section
- bullet           — list of things
**bold**           — emphasis on a key word
```code```          — exact text or code</pre>
        <p style="margin-top: 30px;" class="accent">That's it. Don't overthink it.</p>
    </div>
    <div class="slide-footer"><span>7 / 24</span></div>
</div>
```

- [ ] **Step 4: Add slide 8 — Markdown before/after**

```html
<div class="slide" data-slide="8">
    <div class="slide-header"><h2>Why it matters</h2></div>
    <div class="slide-content">
        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 30px;">
            <div>
                <h3>Without structure</h3>
                <pre style="font-size: 14px;">build a booking app for my salon
the salon is solo i do hair
i want online booking with a cancel policy</pre>
            </div>
            <div>
                <h3>With markdown</h3>
                <pre style="font-size: 14px;"># Project
Booking app for a solo salon

# Business
- One stylist, hair only
- Want public online booking
- Need cancel policy</pre>
            </div>
        </div>
        <p style="margin-top: 30px;" class="accent">Same content. Different output quality.</p>
    </div>
    <div class="slide-footer"><span>8 / 24</span></div>
</div>
```

- [ ] **Step 5: Add slide 9 — Layer 2 R-C-T-F framework**

```html
<div class="slide" data-slide="9">
    <div class="slide-header"><h2>Layer 2 — R-C-T-F</h2></div>
    <div class="slide-content">
        <pre style="font-size: 18px;"># Role
You are a senior product engineer...

# Context
- Salon in Asheville, solo stylist
- 20 clients/week, paper appointment book

# Task
Design the booking flow data model.

# Format
Bullet list. Plain English. No code yet.</pre>
    </div>
    <div class="slide-footer"><span>9 / 24</span></div>
</div>
```

- [ ] **Step 6: Add slide 10 — V2 demo (JD live)**

```html
<div class="slide" data-slide="10">
    <div class="slide-header"><h2>Watch this</h2></div>
    <div class="slide-content" style="text-align: center;">
        <h3 style="font-size: 48px;">Live demo</h3>
        <p style="margin-top: 30px;">I rewrite my V1 as R-C-T-F.</p>
        <p style="margin-top: 60px;" class="accent">Compare to V1 side-by-side.</p>
    </div>
    <div class="slide-footer"><span>10 / 24</span></div>
</div>
```

- [ ] **Step 7: Add slide 11 — Audience V2 upgrade**

```html
<div class="slide" data-slide="11">
    <div class="slide-header"><h2>Your turn — V2</h2></div>
    <div class="slide-content">
        <h3>Rewrite your V1 with R-C-T-F.</h3>
        <p>Use markdown headers (#) for each section. 3 minutes.</p>
        <p style="margin-top: 30px;">Stuck on Context? Ask yourself: <em>"What would a new employee need to know on day one?"</em></p>
        <p style="margin-top: 60px;" class="accent">Type. Run. Compare to your V1.</p>
    </div>
    <div class="slide-footer"><span>11 / 24</span></div>
</div>
```

- [ ] **Step 8: Add slide 12 — V2 share-back**

```html
<div class="slide" data-slide="12">
    <div class="slide-header"><h2>Pencils down</h2></div>
    <div class="slide-content" style="text-align: center;">
        <h3 style="font-size: 56px;">Better than V1?</h3>
        <p style="margin-top: 40px; opacity: 0.7;">Volunteers — surface one good example to the screen.</p>
    </div>
    <div class="slide-footer"><span>12 / 24</span></div>
</div>
```

- [ ] **Step 9: Verify in browser**

Run:
```bash
open /Users/jdfiscus/dev/tech-town/03-prompting-techniques/slides.html
```

Click through slides 1-12. Check: layout doesn't break on long content, code blocks are readable.

- [ ] **Step 10: Commit**

```bash
git add 03-prompting-techniques/slides.html
git commit -m "slides: V1 diagnosis, markdown primer, Layer 2 R-C-T-F (slides 5-12)"
```

---

## Task 9: Add slides 13-19 — Layer 3 and Layer 4

**Files:**
- Modify: `03-prompting-techniques/slides.html`

- [ ] **Step 1: Add slide 13 — Layer 3 intro (Few-Shot + CoT)**

```html
<div class="slide" data-slide="13">
    <div class="slide-header"><h2>Layer 3 — Examples + Reasoning</h2></div>
    <div class="slide-content">
        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 40px;">
            <div>
                <h3>Few-Shot</h3>
                <p>2-3 examples of "what good looks like"</p>
                <p style="opacity: 0.7; font-size: 18px;">Research: 15-40% accuracy boost</p>
            </div>
            <div>
                <h3>Chain-of-Thought</h3>
                <p>"Think step-by-step first"</p>
                <p style="opacity: 0.7; font-size: 18px;">Forces structured reasoning</p>
            </div>
        </div>
        <p style="margin-top: 40px;" class="accent">Examples teach SHAPE. Step-by-step teaches PROCESS. Stack them.</p>
    </div>
    <div class="slide-footer"><span>13 / 24</span></div>
</div>
```

- [ ] **Step 2: Add slide 14 — V3 demo prompt**

```html
<div class="slide" data-slide="14">
    <div class="slide-header"><h2>Layer 3 stacked on Layer 2</h2></div>
    <div class="slide-content">
        <pre style="font-size: 18px;"># Examples
- Acuity booking flow
- Square Appointments

# Process
Before you write anything, think step-by-step about
what could break in this booking flow.</pre>
        <p style="margin-top: 30px;" class="accent">Add these to your V2. Don't replace anything.</p>
    </div>
    <div class="slide-footer"><span>14 / 24</span></div>
</div>
```

- [ ] **Step 3: Add slide 15 — Audience V3 upgrade**

```html
<div class="slide" data-slide="15">
    <div class="slide-header"><h2>Your turn — V3</h2></div>
    <div class="slide-content">
        <h3>Add Examples + Process to your V2.</h3>
        <p>3 minutes.</p>
        <p style="margin-top: 30px; opacity: 0.7;">Your examples don't have to be perfect. "Something like Acuity booking" is enough.</p>
        <p style="margin-top: 60px;" class="accent">Type. Run. Compare to V2.</p>
    </div>
    <div class="slide-footer"><span>15 / 24</span></div>
</div>
```

- [ ] **Step 4: Add slide 16 — V3 share-back**

```html
<div class="slide" data-slide="16">
    <div class="slide-header"><h2>Pencils down</h2></div>
    <div class="slide-content" style="text-align: center;">
        <h3 style="font-size: 56px;">Even better?</h3>
        <p style="margin-top: 40px; opacity: 0.7;">One volunteer-surfaced example.</p>
    </div>
    <div class="slide-footer"><span>16 / 24</span></div>
</div>
```

- [ ] **Step 5: Add slide 17 — Layer 4 intro (XML + Meta)**

```html
<div class="slide" data-slide="17">
    <div class="slide-header"><h2>Layer 4 — Pro Moves</h2></div>
    <div class="slide-content">
        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 40px;">
            <div>
                <h3>XML Tags</h3>
                <p>Wrap markdown sections:</p>
                <pre style="font-size: 14px;">&lt;role&gt;...&lt;/role&gt;
&lt;context&gt;...&lt;/context&gt;
&lt;task&gt;...&lt;/task&gt;
&lt;examples&gt;...&lt;/examples&gt;</pre>
            </div>
            <div>
                <h3>Meta-Prompt</h3>
                <p>Then say:</p>
                <pre style="font-size: 14px;">"What's missing from
this prompt? Rewrite it
to get a better result."</pre>
                <p style="margin-top: 10px;">Run the AI's rewrite.</p>
            </div>
        </div>
    </div>
    <div class="slide-footer"><span>17 / 24</span></div>
</div>
```

- [ ] **Step 6: Add slide 18 — V4 demo (the whoa moment)**

```html
<div class="slide" data-slide="18">
    <div class="slide-header"><h2>Watch this</h2></div>
    <div class="slide-content" style="text-align: center;">
        <h3 style="font-size: 48px;">Live demo</h3>
        <p style="margin-top: 30px;">Wrap V3 in XML → meta-prompt it → run the rewritten version.</p>
        <p style="margin-top: 60px;" class="accent">Use the AI to be the best prompt writer in the room.</p>
    </div>
    <div class="slide-footer"><span>18 / 24</span></div>
</div>
```

- [ ] **Step 7: Add slide 19 — Audience V4 upgrade**

```html
<div class="slide" data-slide="19">
    <div class="slide-header"><h2>Your turn — V4</h2></div>
    <div class="slide-content">
        <h3>Wrap your V3 sections in XML tags. Then meta-prompt it.</h3>
        <p>3 minutes.</p>
        <p style="margin-top: 30px; opacity: 0.7;">Don't be precious. Let the AI rewrite your prompt.</p>
        <p style="margin-top: 60px;" class="accent">Wrap. Meta-prompt. Run the rewrite.</p>
    </div>
    <div class="slide-footer"><span>19 / 24</span></div>
</div>
```

- [ ] **Step 8: Verify in browser**

Run:
```bash
open /Users/jdfiscus/dev/tech-town/03-prompting-techniques/slides.html
```

Click through slides 13-19. Verify side-by-side grids render correctly and code blocks fit on screen.

- [ ] **Step 9: Commit**

```bash
git add 03-prompting-techniques/slides.html
git commit -m "slides: Layer 3 (Few-Shot+CoT) and Layer 4 (XML+meta) (slides 13-19)"
```

---

## Task 10: Add slides 20-24 — Takeaway, interview rescue, bridge to build

**Files:**
- Modify: `03-prompting-techniques/slides.html`

- [ ] **Step 1: Add slide 20 — Final share-back**

```html
<div class="slide" data-slide="20">
    <div class="slide-header"><h2>Pencils down</h2></div>
    <div class="slide-content" style="text-align: center;">
        <h3 style="font-size: 56px;">Final glow-up?</h3>
        <p style="margin-top: 40px; opacity: 0.7;">Best volunteer-surfaced example.</p>
    </div>
    <div class="slide-footer"><span>20 / 24</span></div>
</div>
```

- [ ] **Step 2: Add slide 21 — Cheat sheet QR**

```html
<div class="slide" data-slide="21">
    <div class="slide-header"><h2>You just stacked 4 layers</h2></div>
    <div class="slide-content" style="text-align: center;">
        <h3>Cheat sheet ↓</h3>
        <img src="qr.png" alt="QR code to cheat sheet" style="width: 320px; height: 320px; margin: 30px auto; background: white; padding: 20px; border-radius: 10px;">
        <p class="accent" style="font-size: 24px;">[Final deployed URL]</p>
    </div>
    <div class="slide-footer"><span>21 / 24</span></div>
</div>
```

- [ ] **Step 3: Add slide 22 — Interview rescue (5th technique)**

```html
<div class="slide" data-slide="22">
    <div class="slide-header"><h2>The 5th move — Interview Technique</h2></div>
    <div class="slide-content">
        <h3>Stuck during build? Flip it.</h3>
        <pre style="font-size: 18px;">I want to build [PROJECT]. Before we write anything,
interview me about my project. Ask one question at a
time. Wait for my answer. When you have enough,
summarize back and we'll start.</pre>
        <p style="margin-top: 30px;" class="accent">Full template on the cheat sheet.</p>
    </div>
    <div class="slide-footer"><span>22 / 24</span></div>
</div>
```

- [ ] **Step 4: Add slide 23 — Bridge to build**

```html
<div class="slide" data-slide="23">
    <div class="slide-header"><h2>Now go build</h2></div>
    <div class="slide-content" style="text-align: center;">
        <h3 style="font-size: 48px;">First move:</h3>
        <p style="margin-top: 30px; font-size: 36px;" class="accent">Paste your V4 into Lovable.</p>
        <p style="margin-top: 40px;">Then iterate. We're all here.</p>
    </div>
    <div class="slide-footer"><span>23 / 24</span></div>
</div>
```

- [ ] **Step 5: Add slide 24 — Closing**

```html
<div class="slide" data-slide="24">
    <div class="slide-content" style="justify-content: center; text-align: center;">
        <h1 style="font-size: 72px;">Build time.</h1>
        <p style="margin-top: 40px; font-size: 28px; opacity: 0.8;">Questions? I'm right here.</p>
        <p style="margin-top: 60px; opacity: 0.6;">TechTown Start Studio &middot; JD Fiscus</p>
    </div>
    <div class="slide-footer"><span>24 / 24</span></div>
</div>
```

- [ ] **Step 6: Verify in browser**

Run:
```bash
open /Users/jdfiscus/dev/tech-town/03-prompting-techniques/slides.html
```

Click through ALL 24 slides front-to-back. Check: no broken layouts, QR placeholder is positioned correctly (QR image will be added in Task 13), final slide renders cleanly.

- [ ] **Step 7: Commit**

```bash
git add 03-prompting-techniques/slides.html
git commit -m "slides: takeaway, interview rescue, bridge to build (slides 20-24)"
```

---

## Task 11: Build `cheat-sheet-printable.html`

**Files:**
- Create: `03-prompting-techniques/cheat-sheet-printable.html`

- [ ] **Step 1: Write the print-styled HTML**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Prompting Cheat Sheet — TechTown</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700;900&family=Roboto+Mono:wght@400&display=swap" rel="stylesheet">
    <style>
        @page { size: letter; margin: 0.4in; }
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Roboto', sans-serif; font-size: 10pt; line-height: 1.35; color: #1a1a1a; }
        h1 { font-size: 18pt; color: #0c5449; margin-bottom: 4pt; }
        h2 { font-size: 11pt; color: #0c5449; margin-top: 8pt; margin-bottom: 4pt; text-transform: uppercase; letter-spacing: 0.5pt; }
        h3 { font-size: 9pt; font-weight: 700; margin-bottom: 2pt; }
        pre, code { font-family: 'Roboto Mono', monospace; font-size: 8pt; background: #f5f5f5; padding: 4pt 6pt; border-radius: 3pt; }
        pre { white-space: pre-wrap; margin: 2pt 0 4pt 0; }
        ul { margin-left: 14pt; }
        li { margin-bottom: 2pt; }
        .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 8pt; }
        .accent { color: #ffcc33; background: #1a1a1a; padding: 2pt 4pt; border-radius: 2pt; font-weight: 700; }
        .header { border-bottom: 2pt solid #0c5449; padding-bottom: 4pt; margin-bottom: 8pt; display: flex; justify-content: space-between; align-items: flex-end; }
        .footer { margin-top: 8pt; padding-top: 4pt; border-top: 1pt solid #ccc; font-size: 8pt; color: #666; text-align: center; }
    </style>
</head>
<body>
    <div class="header">
        <div>
            <h1>Prompting Cheat Sheet</h1>
            <p style="font-size: 9pt; color: #666;">5 techniques. Built for build time.</p>
        </div>
        <div style="font-size: 8pt; color: #666; text-align: right;">
            TechTown Start Studio<br>JD Fiscus
        </div>
    </div>

    <h2>The 4 Layers</h2>

    <div class="grid">
        <div>
            <h3>Layer 1 — V1: Just ask</h3>
            <p style="font-size: 9pt;">Whatever you'd normally type. Almost always too vague.</p>

            <h3 style="margin-top: 6pt;">Layer 2 — Role + Context + Task + Format</h3>
            <pre># Role
You are a senior product engineer...

# Context
- Business specifics
- Constraints
- Current state

# Task
Specific next step (not whole app)

# Format
How the answer should come back</pre>
        </div>
        <div>
            <h3>Layer 3 — Add Examples + Reasoning</h3>
            <pre># Examples
- Acuity booking flow
- Slack messaging UI

# Process
Before you write anything, think
step-by-step about what could break.</pre>

            <h3 style="margin-top: 6pt;">Layer 4 — XML Tags + Meta-Prompt</h3>
            <pre>&lt;role&gt;...&lt;/role&gt;
&lt;context&gt;...&lt;/context&gt;
&lt;task&gt;...&lt;/task&gt;
&lt;format&gt;...&lt;/format&gt;
&lt;examples&gt;...&lt;/examples&gt;</pre>
            <p style="font-size: 9pt;">Then: <em>"What's missing? Rewrite this prompt to get a better result."</em> Run the rewrite.</p>
        </div>
    </div>

    <h2>Rescue Move — Interview Technique</h2>
    <pre>I want to build [PROJECT]. Before we write anything,
interview me about my project. Ask one question at a time.
Wait for my answer. When you have enough, summarize back.</pre>

    <h2>After V4 Works — 3 Next Moves</h2>
    <ul>
        <li><strong>Iterate one section</strong> — change only Context or Task, leave the rest</li>
        <li><strong>Ask for variations</strong> — "Give me 3 different approaches. Compare trade-offs."</li>
        <li><strong>Ask AI to critique itself</strong> — "What's wrong with what you just produced?"</li>
    </ul>

    <h2>Don't</h2>
    <ul>
        <li>Don't use "CRITICAL: YOU MUST..." — modern models get overcautious and refuse</li>
        <li>Don't change 3 things at once when iterating — change one, test, then the next</li>
        <li>Don't assume same prompt works in Claude and ChatGPT</li>
    </ul>

    <div class="footer">
        [Deployed URL] &middot; TechTown Start Studio &middot; 2026-05-12
    </div>
</body>
</html>
```

- [ ] **Step 2: Open in browser and verify print layout**

Run:
```bash
open /Users/jdfiscus/dev/tech-town/03-prompting-techniques/cheat-sheet-printable.html
```

Then File → Print → Preview. Verify: fits on ONE page (US Letter), all sections legible at 100% zoom, no content cut off.

If content overflows, reduce font sizes by 1pt or condense bullet items.

- [ ] **Step 3: Commit**

```bash
git add 03-prompting-techniques/cheat-sheet-printable.html
git commit -m "cheat-sheet: print-styled one-page HTML"
```

---

## Task 12: Generate `cheat-sheet.pdf` from printable HTML

**Files:**
- Create: `03-prompting-techniques/cheat-sheet.pdf`

- [ ] **Step 1: Generate PDF using headless Chrome**

Run:
```bash
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless \
  --disable-gpu \
  --no-pdf-header-footer \
  --print-to-pdf=/Users/jdfiscus/dev/tech-town/03-prompting-techniques/cheat-sheet.pdf \
  file:///Users/jdfiscus/dev/tech-town/03-prompting-techniques/cheat-sheet-printable.html
```

Expected: `cheat-sheet.pdf` created in the folder.

If Chrome isn't installed at that path, find it with `find /Applications -name "Google Chrome" -type d 2>/dev/null` or use `puppeteer` via npx:

```bash
npx -y puppeteer-cli print \
  --path /Users/jdfiscus/dev/tech-town/03-prompting-techniques/cheat-sheet.pdf \
  /Users/jdfiscus/dev/tech-town/03-prompting-techniques/cheat-sheet-printable.html
```

- [ ] **Step 2: Verify PDF**

Run:
```bash
open /Users/jdfiscus/dev/tech-town/03-prompting-techniques/cheat-sheet.pdf
```

Check: opens cleanly, exactly 1 page, all sections present.

- [ ] **Step 3: Commit**

```bash
git add 03-prompting-techniques/cheat-sheet.pdf
git commit -m "cheat-sheet: PDF export for QR/email distribution"
```

---

## Task 13: Generate QR code and embed in slides

**Files:**
- Create: `03-prompting-techniques/qr.png`
- Modify: `03-prompting-techniques/slides.html`
- Modify: `03-prompting-techniques/cheat-sheet-printable.html`

**Note:** This task requires JD to have decided the final deployed URL. Use a placeholder if not yet decided — regenerate after Task 15 deploy.

- [ ] **Step 1: Set the target URL variable**

Decide the URL. Default to the Vercel-assigned URL (e.g., `https://03-prompting-techniques.vercel.app`) if no custom domain yet. JD to confirm.

- [ ] **Step 2: Generate QR code PNG**

Run (replace URL):
```bash
npx -y qrcode "https://prompting.techtown.studio" \
  -o /Users/jdfiscus/dev/tech-town/03-prompting-techniques/qr.png \
  -w 800 \
  --margin 2
```

Expected: `qr.png` created at 800x800, scannable from across a 250-person room.

- [ ] **Step 3: Verify the QR works**

Open `qr.png`, scan with phone. Should resolve to the chosen URL.

- [ ] **Step 4: Update slide 21 with real URL**

In `slides.html`, find the line `<p class="accent" style="font-size: 24px;">[Final deployed URL]</p>` and replace `[Final deployed URL]` with the actual URL (e.g., `prompting.techtown.studio`).

- [ ] **Step 5: Update cheat-sheet-printable.html footer**

Find `<div class="footer">[Deployed URL]` and replace `[Deployed URL]` with the actual URL.

- [ ] **Step 6: Regenerate PDF**

Run again:
```bash
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless --disable-gpu --no-pdf-header-footer \
  --print-to-pdf=/Users/jdfiscus/dev/tech-town/03-prompting-techniques/cheat-sheet.pdf \
  file:///Users/jdfiscus/dev/tech-town/03-prompting-techniques/cheat-sheet-printable.html
```

- [ ] **Step 7: Commit**

```bash
git add 03-prompting-techniques/qr.png 03-prompting-techniques/slides.html 03-prompting-techniques/cheat-sheet-printable.html 03-prompting-techniques/cheat-sheet.pdf
git commit -m "qr: generate code, embed in slides and cheat sheet, regen PDF"
```

---

## Task 14: Add `index.html` landing page and `vercel.json`

**Files:**
- Create: `03-prompting-techniques/index.html`
- Create: `03-prompting-techniques/vercel.json`

- [ ] **Step 1: Write `index.html`**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prompting Techniques — TechTown Workshop</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #0c5449;
            --accent: #ffcc33;
            --dark: #1a1a1a;
            --white: #ffffff;
        }
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Roboto', sans-serif; background: linear-gradient(135deg, #0c5449, #25524a); color: white; min-height: 100vh; padding: 60px 20px; }
        .container { max-width: 720px; margin: 0 auto; }
        h1 { font-size: 48px; font-weight: 900; margin-bottom: 12px; }
        h1 .accent { color: var(--accent); }
        p.subtitle { font-size: 20px; opacity: 0.85; margin-bottom: 40px; }
        .grid { display: grid; gap: 16px; margin-top: 24px; }
        .card { background: rgba(0,0,0,0.25); padding: 20px 24px; border-radius: 10px; transition: background 0.2s; }
        .card:hover { background: rgba(0,0,0,0.4); }
        .card a { color: white; text-decoration: none; display: block; }
        .card h3 { font-size: 22px; color: var(--accent); margin-bottom: 4px; }
        .card p { font-size: 16px; opacity: 0.8; }
        footer { margin-top: 60px; opacity: 0.6; font-size: 14px; }
    </style>
</head>
<body>
    <div class="container">
        <h1>Prompting <span class="accent">Techniques</span></h1>
        <p class="subtitle">TechTown Start Studio workshop &middot; JD Fiscus</p>

        <div class="grid">
            <div class="card"><a href="./cheat-sheet.pdf">
                <h3>Cheat Sheet (PDF)</h3>
                <p>One-page reference. The 4 layers + interview rescue.</p>
            </a></div>
            <div class="card"><a href="./slides.html">
                <h3>Workshop Slides</h3>
                <p>The deck from the live session.</p>
            </a></div>
            <div class="card"><a href="./prompt-template.md">
                <h3>V4 Prompt Template</h3>
                <p>Copy-paste structure for your own projects.</p>
            </a></div>
            <div class="card"><a href="./interview-template.md">
                <h3>Interview Rescue Template</h3>
                <p>When you're stuck during build.</p>
            </a></div>
            <div class="card"><a href="./fallback-projects.md">
                <h3>Starter Project Ideas</h3>
                <p>Pick one if you don't have a project yet.</p>
            </a></div>
        </div>

        <footer>
            TechTown Start Studio &middot; 2026
        </footer>
    </div>
</body>
</html>
```

- [ ] **Step 2: Write `vercel.json`**

```json
{
  "cleanUrls": true,
  "trailingSlash": false,
  "headers": [
    {
      "source": "/(.*)",
      "headers": [
        { "key": "Cache-Control", "value": "public, max-age=3600, must-revalidate" }
      ]
    }
  ]
}
```

- [ ] **Step 3: Verify locally**

Run:
```bash
open /Users/jdfiscus/dev/tech-town/03-prompting-techniques/index.html
```

Check: landing page renders, all 5 cards visible, links resolve to existing files.

- [ ] **Step 4: Commit**

```bash
git add 03-prompting-techniques/index.html 03-prompting-techniques/vercel.json
git commit -m "deploy: landing index.html + Vercel static config"
```

---

## Task 15: Deploy to Vercel and verify

**Files:**
- None modified — this task is deployment only

**Note:** This task requires JD to have a Vercel account, the Vercel CLI installed (`npm i -g vercel`), and authentication done (`vercel login`). If not, JD should run those manually first.

- [ ] **Step 1: Push current main to GitHub remote**

Run from repo root:
```bash
git push origin main
```

Expected: all commits from Tasks 1-14 land on the remote.

- [ ] **Step 2: Deploy to Vercel from the folder**

Run:
```bash
cd /Users/jdfiscus/dev/tech-town/03-prompting-techniques
vercel --prod
```

Follow CLI prompts:
- Set up and deploy? **Y**
- Which scope? (JD's account)
- Link to existing project? **N**
- Project name? `prompting-techniques` (or as preferred)
- Directory? **./** (current dir, since we ran from inside the folder)

Expected: Vercel outputs a deployment URL like `https://prompting-techniques.vercel.app`.

- [ ] **Step 3: Visit the deployed URL and verify**

Run:
```bash
open https://prompting-techniques.vercel.app
```

(Substitute actual URL from Step 2 output.)

Verify in browser:
- Landing page loads
- Each of the 5 cards is clickable
- `slides.html` opens and arrow-key advance works
- `cheat-sheet.pdf` opens
- `prompt-template.md` renders (as raw text — that's expected for .md files on Vercel; if you want rendered markdown, add a static rendering step or convert to .html)

- [ ] **Step 4: Configure custom domain (if applicable)**

If JD owns `techtown.studio` and wants `prompting.techtown.studio`:
1. In Vercel dashboard → Project → Settings → Domains
2. Add `prompting.techtown.studio`
3. Update DNS at registrar with the CNAME Vercel provides
4. Wait for SSL cert provision (usually under 5 min)

If using just the Vercel-assigned URL: skip this step.

- [ ] **Step 5: Verify QR resolves to deployed URL**

Scan `qr.png` with phone. Should land on the deployed Vercel URL (or custom domain if configured). If URL has changed since Task 13, regenerate QR and slide 21:

```bash
npx -y qrcode "https://[actual-deployed-url]" \
  -o /Users/jdfiscus/dev/tech-town/03-prompting-techniques/qr.png \
  -w 800 --margin 2
```

Update slide 21 + cheat-sheet footer + regenerate PDF + commit + redeploy.

- [ ] **Step 6: Final commit**

```bash
git add 03-prompting-techniques/.vercel
git commit -m "deploy: link Vercel project for 03-prompting-techniques"
git push origin main
```

(Note: `.vercel/` is in `.gitignore`, so this commit will only include the project config if Vercel writes it elsewhere. Adjust if needed.)

---

## Final Verification Checklist

After all 15 tasks complete, run this end-to-end check:

- [ ] All 24 slides render correctly in browser (arrow keys advance, no broken layouts)
- [ ] Cheat sheet PDF opens, fits on ONE page, all sections readable
- [ ] QR code on slide 21 scans cleanly and resolves to the deployed URL
- [ ] Deployed URL serves the landing page; all 5 card links work
- [ ] `prompt-template.md` and `interview-template.md` are accessible from deployed site
- [ ] Slides match the spec beat sheet timing (mentally walk through 0:00 → 0:45)
- [ ] `outline.md` covers every beat with speaker cues (not just spec copy-paste)
- [ ] All commits pushed to `origin/main`

---

## What This Plan Does NOT Cover

- **Live show-day operations:** mic setup, volunteer briefing schedule, projector calibration — JD handles morning-of
- **Slido / Mentimeter integration:** if JD wants live audience polling beyond hand-raises, requires separate setup
- **Recording the session:** if recording for YouTube post-event, requires camera/screen-recording config not in this plan
- **Pre-event attendee emails:** drafting the "bring a laptop, here's the QR" email is a separate write
