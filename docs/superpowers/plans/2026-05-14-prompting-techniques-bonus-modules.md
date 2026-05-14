# Prompting Techniques — Bonus Modules Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build `bonus.html` — a self-contained 36-slide bonus deck with a clickable module menu and five opt-in deep-dive modules — and wire it into the existing landing page and core deck.

**Architecture:** `bonus.html` reuses the exact engine of `slides.html` (hand-rolled `<div class="slide" data-slide="N">` blocks, JS class-swap navigation, arrow/space keys, auto-appended copy buttons). It adds two things: a `goto(n)` jump function so menu cards can link to module start slides, and a single fixed `≡ Menu` button that is shown on every slide except the menu (slide 1). No build step, no framework — a static HTML file deployed to Vercel with the rest of the folder.

**Tech Stack:** Static HTML/CSS/JS. TechTown brand CSS tokens. Roboto + Roboto Mono fonts. Vercel static hosting. No test framework exists in this project — verification is structural (grep counts) plus a manual browser check, matching the existing codebase's established pattern.

---

## File Structure

| File | Status | Responsibility |
|---|---|---|
| `03-prompting-techniques/bonus.html` | Create | The bonus deck: 1 menu slide + 35 module slides, navigation script, copy buttons |
| `03-prompting-techniques/bonus-outline.md` | Create | Speaker notes for the five modules, organized by module |
| `03-prompting-techniques/index.html` | Modify | Add a landing-page card linking to `bonus.html` |
| `03-prompting-techniques/slides.html` | Modify | Add one pointer line to the final slide (28) directing people to the bonus deck |

**Slide numbering in `bonus.html`** (locked — menu card targets and `≡ Menu` references depend on it):

| Slides | Block |
|---|---|
| 1 | Menu |
| 2–9 | Module 1 — When the build breaks (8 slides) |
| 10–16 | Module 2 — After V4 works: iterating (7 slides) |
| 17–23 | Module 3 — Data & backends (7 slides) |
| 24–29 | Module 4 — Reading prompts well (6 slides) |
| 30–36 | Module 5 — More techniques (7 slides) |

Every slide footer uses this exact form (only the number changes):
```html
<div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>N / 36</span></div>
```

---

## Task 1: Scaffold `bonus.html` — head, CSS, menu slide, navigation script

**Files:**
- Create: `03-prompting-techniques/bonus.html`

- [ ] **Step 1: Write the full scaffold file**

Create `03-prompting-techniques/bonus.html` with this exact content. This is the complete file for this task — module slides are inserted by later tasks immediately before the closing `</div>` of `.slides-container` (i.e., before the `<div class="nav">` line).

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bonus Modules — Prompting Techniques — TechTown Start Studio</title>
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
        pre { padding: 20px; overflow-x: auto; white-space: pre-wrap; position: relative; }
        .copy-btn { position: absolute; top: 8px; right: 8px; background: var(--accent); color: var(--dark); border: none; padding: 4px 10px; border-radius: 4px; font-size: 12px; cursor: pointer; font-weight: 700; opacity: 0.85; font-family: 'Roboto', sans-serif; }
        .copy-btn:hover { opacity: 1; }
        .copy-btn.copied { background: #5cb85c; color: white; }
        .accent { color: var(--accent); }
        .nav { position: fixed; bottom: 20px; right: 20px; display: flex; gap: 10px; z-index: 100; }
        .nav button { background: var(--accent); color: var(--dark); border: none; padding: 10px 16px; border-radius: 4px; cursor: pointer; font-weight: 700; }
        .menu-btn { position: fixed; top: 20px; left: 20px; background: var(--accent); color: var(--dark); border: none; padding: 8px 14px; border-radius: 4px; cursor: pointer; font-weight: 700; font-family: 'Roboto', sans-serif; z-index: 100; }
        .menu-btn:hover { opacity: 0.85; }
        .menu-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
        .menu-card { background: rgba(0,0,0,0.3); padding: 20px 24px; border-radius: 8px; cursor: pointer; transition: background 0.2s, transform 0.1s; }
        .menu-card:hover { background: rgba(255,204,51,0.15); transform: translateY(-2px); }
        .menu-card h3 { margin-bottom: 6px; font-size: 26px; }
        .menu-card p { font-size: 18px; opacity: 0.8; margin-bottom: 0; }
    </style>
</head>
<body>
    <div class="slides-container">
        <div class="slide active" data-slide="1">
            <div class="slide-header"><h2>Bonus modules — pick one</h2></div>
            <div class="slide-content">
                <p style="opacity: 0.8; margin-bottom: 20px;">Optional deep-dives. Click one, or use the arrow keys.</p>
                <div class="menu-grid">
                    <div class="menu-card" onclick="goto(2)">
                        <h3>1 — When the build breaks</h3>
                        <p>Debugging. Describing bugs. The interview technique, in full.</p>
                    </div>
                    <div class="menu-card" onclick="goto(10)">
                        <h3>2 — After V4 works</h3>
                        <p>Iterating safely. Variations. Design tweaks.</p>
                    </div>
                    <div class="menu-card" onclick="goto(17)">
                        <h3>3 — Data &amp; backends</h3>
                        <p>The database wall, in plain language.</p>
                    </div>
                    <div class="menu-card" onclick="goto(24)">
                        <h3>4 — Reading prompts well</h3>
                        <p>Vetting an AI-written prompt. The 4 layers as a checklist.</p>
                    </div>
                    <div class="menu-card" onclick="goto(30)">
                        <h3>5 — More techniques</h3>
                        <p>Chaining, constraints, self-critique, "give me 3 approaches."</p>
                    </div>
                </div>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>1 / 36</span></div>
        </div>

    </div>
    <button class="menu-btn" onclick="goto(1)">&#8801; Menu</button>
    <div class="nav">
        <button onclick="prev()">&larr;</button>
        <button onclick="next()">&rarr;</button>
    </div>
    <script>
        let current = 1;
        const total = document.querySelectorAll('.slide').length;
        const menuBtn = document.querySelector('.menu-btn');
        function show(n) {
            document.querySelectorAll('.slide').forEach(s => s.classList.remove('active'));
            const slide = document.querySelector(`[data-slide="${n}"]`);
            if (slide) slide.classList.add('active');
            menuBtn.style.display = (n === 1) ? 'none' : 'block';
        }
        function goto(n) { current = n; show(current); }
        function next() { if (current < total) { current++; show(current); } }
        function prev() { if (current > 1) { current--; show(current); } }
        document.addEventListener('keydown', e => {
            if (e.key === 'ArrowRight' || e.key === ' ') next();
            if (e.key === 'ArrowLeft') prev();
        });
        show(1);

        // Copy-to-clipboard buttons on every <pre> block
        document.querySelectorAll('pre').forEach(pre => {
            const btn = document.createElement('button');
            btn.className = 'copy-btn';
            btn.textContent = 'copy';
            btn.onclick = (e) => {
                e.stopPropagation();
                navigator.clipboard.writeText(pre.textContent).then(() => {
                    btn.textContent = 'copied!';
                    btn.classList.add('copied');
                    setTimeout(() => {
                        btn.textContent = 'copy';
                        btn.classList.remove('copied');
                    }, 1500);
                });
            };
            pre.appendChild(btn);
        });
    </script>
</body>
</html>
```

- [ ] **Step 2: Verify the scaffold structurally**

Run: `cd /Users/jdfiscus/dev/tech-town && grep -c 'data-slide=' 03-prompting-techniques/bonus.html`
Expected: `1` (only the menu slide so far)

Run: `grep -o 'goto([0-9]*)' 03-prompting-techniques/bonus.html | sort -u`
Expected exactly these five lines: `goto(10)`, `goto(17)`, `goto(2)`, `goto(24)`, `goto(30)` (sort order is lexical) — plus the `≡ Menu` button uses `goto(1)`, so `goto(1)` also appears. Full expected set: `goto(1)`, `goto(10)`, `goto(17)`, `goto(2)`, `goto(24)`, `goto(30)`.

- [ ] **Step 3: Manual browser check**

Open `03-prompting-techniques/bonus.html` in a browser (`open 03-prompting-techniques/bonus.html` on macOS).
Confirm:
- The menu slide renders with five cards.
- The `≡ Menu` button is NOT visible (we're on slide 1).
- Pressing the right arrow does nothing visible yet (no slide 2 exists) — this is expected.
- Clicking a menu card does nothing visible yet (target slides don't exist) — this is expected. `show()` guards with `if (slide)` so there is no error.

- [ ] **Step 4: Commit**

```bash
cd /Users/jdfiscus/dev/tech-town
git add 03-prompting-techniques/bonus.html
git commit -m "bonus: scaffold deck — menu slide, nav, copy buttons"
```

---

## Task 2: Module 1 — When the build breaks (slides 2–9)

**Files:**
- Modify: `03-prompting-techniques/bonus.html` (insert 8 slide blocks)

- [ ] **Step 1: Insert the Module 1 slides**

In `03-prompting-techniques/bonus.html`, insert the following 8 `<div class="slide">` blocks immediately after the menu slide's closing `</div>` (the one followed by a blank line and the `</div>` that closes `.slides-container`). Insert them so they sit inside `.slides-container`, before `<button class="menu-btn"...>`.

```html
        <div class="slide" data-slide="2">
            <div class="slide-header"><h2>Module 1 — When the build breaks</h2></div>
            <div class="slide-content">
                <h3>Lovable did something weird. Now what?</h3>
                <p style="margin-top: 20px;">Everyone hits this. The screen's blank, the button does nothing, it deleted the thing you liked.</p>
                <p style="margin-top: 40px;" class="accent">You don't need to know how to code. You need to know how to diagnose.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>2 / 36</span></div>
        </div>

        <div class="slide" data-slide="3">
            <div class="slide-header"><h2>Don't rage-prompt. Diagnose.</h2></div>
            <div class="slide-content">
                <p>When something breaks, the instinct is to type "it's broken, fix it" over and over.</p>
                <ul style="margin-top: 30px;">
                    <li>The AI isn't broken — it's <strong>missing information</strong></li>
                    <li>Same lesson as V1: vague in &rarr; vague out</li>
                    <li>"Fix it" is a wish. Describe what you see — that's a clue.</li>
                </ul>
                <p style="margin-top: 30px;" class="accent">A good bug report is just Context + Task, aimed at a problem.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>3 / 36</span></div>
        </div>

        <div class="slide" data-slide="4">
            <div class="slide-header"><h2>Describe a bug in 3 parts</h2></div>
            <div class="slide-content">
                <ul style="font-size: 26px; line-height: 1.7;">
                    <li><strong>Expected</strong> — what you thought would happen</li>
                    <li><strong>Actual</strong> — what happened instead</li>
                    <li><strong>On screen</strong> — what you literally see (error text, blank area, wrong color)</li>
                </ul>
                <p style="margin-top: 30px; opacity: 0.7;">If there's an error message, paste the whole thing. Don't summarize it.</p>
                <p style="margin-top: 20px;" class="accent">Specifics are clues. "It's broken" is not.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>4 / 36</span></div>
        </div>

        <div class="slide" data-slide="5">
            <div class="slide-header"><h2>Copy-paste — bug report</h2></div>
            <div class="slide-content">
                <pre style="font-size: 18px;">Something isn't working. Here's what I see:

# Expected
[what I thought would happen]

# Actual
[what happened instead]

# On screen
[error text, or describe what's wrong]

Before changing anything, tell me the 2-3 most
likely causes. Then fix the most likely one.</pre>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>5 / 36</span></div>
        </div>

        <div class="slide" data-slide="6">
            <div class="slide-header"><h2>Still stuck? Flip it — the interview</h2></div>
            <div class="slide-content">
                <p>When you don't even know what to ask for, make the AI ask <em>you</em>.</p>
                <ul style="margin-top: 24px;">
                    <li>You stop guessing at prompt wording</li>
                    <li>The AI pulls the context out of you, one question at a time</li>
                    <li>You just answer — answering is easier than prompting</li>
                </ul>
                <p style="margin-top: 30px;" class="accent">This is the 5th move from the core deck — here's the full template.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>6 / 36</span></div>
        </div>

        <div class="slide" data-slide="7">
            <div class="slide-header"><h2>Copy-paste — the interview</h2></div>
            <div class="slide-content">
                <pre style="font-size: 18px;">I want to build [PROJECT]. Before we write anything,
interview me about my project. Ask one question at a
time. Wait for my answer before the next question.
When you have enough to write a clear spec, summarize
it back to me and we'll start.</pre>
                <p style="margin-top: 24px;" class="accent">Answer honestly. The summary it gives back is your new prompt.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>7 / 36</span></div>
        </div>

        <div class="slide" data-slide="8">
            <div class="slide-header"><h2>When to start a fresh chat</h2></div>
            <div class="slide-content">
                <p>Remember the context window — long chats lose the thread.</p>
                <h3 style="margin-top: 24px;">Signs the chat has gone bad:</h3>
                <ul>
                    <li>It re-introduces bugs you already fixed</li>
                    <li>It forgets decisions you made earlier</li>
                    <li>Answers get slower and vaguer</li>
                </ul>
                <p style="margin-top: 24px;" class="accent">Fix: new chat. Paste your V4 prompt + a 3-line summary of where you are.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>8 / 36</span></div>
        </div>

        <div class="slide" data-slide="9">
            <div class="slide-header"><h2>Module 1 recap</h2></div>
            <div class="slide-content">
                <ul style="font-size: 26px; line-height: 1.7;">
                    <li>Don't rage-prompt — diagnose</li>
                    <li>Describe bugs: Expected / Actual / On screen</li>
                    <li>Stuck for words? Make the AI interview you</li>
                    <li>Chat gone bad? Fresh chat + V4 + a summary</li>
                </ul>
                <p style="margin-top: 30px;" class="accent">Press &#8801; Menu for the next module.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>9 / 36</span></div>
        </div>
```

- [ ] **Step 2: Verify Module 1 structurally**

Run: `cd /Users/jdfiscus/dev/tech-town && grep -c 'data-slide=' 03-prompting-techniques/bonus.html`
Expected: `9`

Run: `grep -o '[0-9]* / 36' 03-prompting-techniques/bonus.html`
Expected: `1 / 36` through `9 / 36`, in order, no gaps, no duplicates.

- [ ] **Step 3: Manual browser check**

Reload `bonus.html`. From the menu, click card "1 — When the build breaks" → lands on slide 2. Arrow through to slide 9. Confirm the `≡ Menu` button is visible on slides 2–9 and returns to slide 1 when clicked. Confirm slides 5 and 7 (the `<pre>` blocks) have a `copy` button that copies the prompt text.

- [ ] **Step 4: Commit**

```bash
cd /Users/jdfiscus/dev/tech-town
git add 03-prompting-techniques/bonus.html
git commit -m "bonus: Module 1 — When the build breaks (8 slides)"
```

---

## Task 3: Module 2 — After V4 works: iterating (slides 10–16)

**Files:**
- Modify: `03-prompting-techniques/bonus.html` (insert 7 slide blocks)

- [ ] **Step 1: Insert the Module 2 slides**

In `03-prompting-techniques/bonus.html`, insert the following 7 blocks immediately after the Module 1 recap slide (`data-slide="9"`), still inside `.slides-container`.

```html
        <div class="slide" data-slide="10">
            <div class="slide-header"><h2>Module 2 — After V4 works</h2></div>
            <div class="slide-content">
                <h3>It works. Don't break it.</h3>
                <p style="margin-top: 20px;">You've got something real on screen. Now you're scared to touch it.</p>
                <p style="margin-top: 40px;" class="accent">Iterating is a skill. It's not "ask for everything at once."</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>10 / 36</span></div>
        </div>

        <div class="slide" data-slide="11">
            <div class="slide-header"><h2>Small, reversible changes</h2></div>
            <div class="slide-content">
                <ul style="margin-top: 10px;">
                    <li><strong>One thing at a time</strong> — so you know what caused what</li>
                    <li><strong>Reversible</strong> — you can always say "undo that last change"</li>
                    <li><strong>Name what's working</strong> — tell it what NOT to touch</li>
                </ul>
                <p style="margin-top: 30px;" class="accent">Big-bang changes are how working apps get broken.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>11 / 36</span></div>
        </div>

        <div class="slide" data-slide="12">
            <div class="slide-header"><h2>Three ways to move forward</h2></div>
            <div class="slide-content">
                <ul style="font-size: 26px; line-height: 1.7;">
                    <li><strong>Change one section</strong> — "only change the booking form, leave the rest"</li>
                    <li><strong>Layer one feature</strong> — add features one prompt at a time, not a list of ten</li>
                    <li><strong>Ask for variations</strong> — "give me 3 versions of this screen, then I'll pick"</li>
                </ul>
                <p style="margin-top: 24px;" class="accent">Each prompt = one move.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>12 / 36</span></div>
        </div>

        <div class="slide" data-slide="13">
            <div class="slide-header"><h2>Copy-paste — change one thing</h2></div>
            <div class="slide-content">
                <pre style="font-size: 18px;"># Change
[the one thing to change]

# Leave alone
Everything else is working — don't touch it.

# Check
After the change, tell me what you modified
and confirm nothing else moved.</pre>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>13 / 36</span></div>
        </div>

        <div class="slide" data-slide="14">
            <div class="slide-header"><h2>Changing how it looks</h2></div>
            <div class="slide-content">
                <p>Design feedback works when you describe a <em>vibe</em>, not a hex code.</p>
                <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 30px; margin-top: 24px;">
                    <div>
                        <h3>Vague</h3>
                        <p>"Make it look better"</p>
                        <p>"Nicer colors"</p>
                    </div>
                    <div>
                        <h3>A vibe it can use</h3>
                        <p>"More premium and calm — like a high-end spa"</p>
                        <p>"More trustworthy, less playful"</p>
                    </div>
                </div>
                <p style="margin-top: 24px;" class="accent">Name a feeling and a reference. It'll translate that to design.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>14 / 36</span></div>
        </div>

        <div class="slide" data-slide="15">
            <div class="slide-header"><h2>Worked example — the salon app</h2></div>
            <div class="slide-content">
                <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 30px;">
                    <div>
                        <h3>Done badly</h3>
                        <pre style="font-size: 15px;">make it better and add
the stuff a salon needs</pre>
                        <p style="font-size: 18px; opacity: 0.7;">Vague. It'll rewrite half the app.</p>
                    </div>
                    <div>
                        <h3>Done well</h3>
                        <pre style="font-size: 15px;">Add a cancellation policy
section to the booking page
only. 24-hour notice. Leave
the rest of the page alone.</pre>
                        <p style="font-size: 18px; opacity: 0.7;">One change. Scoped. Safe.</p>
                    </div>
                </div>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>15 / 36</span></div>
        </div>

        <div class="slide" data-slide="16">
            <div class="slide-header"><h2>Module 2 recap</h2></div>
            <div class="slide-content">
                <ul style="font-size: 26px; line-height: 1.7;">
                    <li>One change per prompt — scoped and reversible</li>
                    <li>Tell it what to leave alone</li>
                    <li>Ask for variations before committing</li>
                    <li>Design feedback = a vibe + a reference, not "better"</li>
                </ul>
                <p style="margin-top: 30px;" class="accent">Press &#8801; Menu for the next module.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>16 / 36</span></div>
        </div>
```

- [ ] **Step 2: Verify Module 2 structurally**

Run: `cd /Users/jdfiscus/dev/tech-town && grep -c 'data-slide=' 03-prompting-techniques/bonus.html`
Expected: `16`

Run: `grep -o '[0-9]* / 36' 03-prompting-techniques/bonus.html`
Expected: `1 / 36` through `16 / 36`, in order, no gaps, no duplicates.

- [ ] **Step 3: Manual browser check**

Reload `bonus.html`. From the menu, click card "2 — After V4 works" → lands on slide 10. Arrow through to slide 16. Confirm slide 13's `<pre>` has a working `copy` button.

- [ ] **Step 4: Commit**

```bash
cd /Users/jdfiscus/dev/tech-town
git add 03-prompting-techniques/bonus.html
git commit -m "bonus: Module 2 — After V4 works (7 slides)"
```

---

## Task 4: Module 3 — Data & backends (slides 17–23)

**Files:**
- Modify: `03-prompting-techniques/bonus.html` (insert 7 slide blocks)

- [ ] **Step 1: Insert the Module 3 slides**

In `03-prompting-techniques/bonus.html`, insert the following 7 blocks immediately after the Module 2 recap slide (`data-slide="16"`), still inside `.slides-container`.

```html
        <div class="slide" data-slide="17">
            <div class="slide-header"><h2>Module 3 — Data &amp; backends</h2></div>
            <div class="slide-content">
                <h3>The wall everyone hits.</h3>
                <p style="margin-top: 20px;">Your app looks great — then you refresh the page and everything you typed is gone.</p>
                <p style="margin-top: 40px;" class="accent">You need a backend. You don't need to understand one.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>17 / 36</span></div>
        </div>

        <div class="slide" data-slide="18">
            <div class="slide-header"><h2>What a backend actually is</h2></div>
            <div class="slide-content">
                <p>In plain terms:</p>
                <h3 style="margin-top: 20px;">A place your app saves stuff so it's still there tomorrow.</h3>
                <ul style="margin-top: 24px;">
                    <li>The screen = what people see (the front)</li>
                    <li>The backend = where the info lives (the back)</li>
                    <li>No backend = nothing is remembered between visits</li>
                </ul>
                <p style="margin-top: 24px;" class="accent">You don't configure it. You ask for it.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>18 / 36</span></div>
        </div>

        <div class="slide" data-slide="19">
            <div class="slide-header"><h2>Meet Supabase</h2></div>
            <div class="slide-content">
                <p>Lovable has a built-in backend called <strong>Supabase</strong>.</p>
                <ul style="margin-top: 24px;">
                    <li>When Lovable says "Supabase" — that's your database talking</li>
                    <li>You won't open it or set it up by hand</li>
                    <li>You just say what you want saved, and Lovable wires it</li>
                </ul>
                <p style="margin-top: 24px;" class="accent">Recognize the word. That's all you need today.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>19 / 36</span></div>
        </div>

        <div class="slide" data-slide="20">
            <div class="slide-header"><h2>How to ask for it</h2></div>
            <div class="slide-content">
                <ul style="font-size: 25px; line-height: 1.7;">
                    <li><strong>Saving data</strong> — "add a database so appointments are saved"</li>
                    <li><strong>Accounts</strong> — "users can create an account and log in"</li>
                    <li><strong>Forms that stick</strong> — "when someone submits this form, save it and show it on the dashboard"</li>
                </ul>
                <p style="margin-top: 20px;" class="accent">Describe the outcome in business terms. Lovable picks the tech.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>20 / 36</span></div>
        </div>

        <div class="slide" data-slide="21">
            <div class="slide-header"><h2>Copy-paste — backend request</h2></div>
            <div class="slide-content">
                <pre style="font-size: 18px;"># What to save
[the thing — e.g. appointments, customers, orders]

# Who can see it
[just me / logged-in users / the public]

# Where it shows up
[which screen displays this saved data]

Set up the database for this and connect it to
the form and the screen. Use Supabase.</pre>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>21 / 36</span></div>
        </div>

        <div class="slide" data-slide="22">
            <div class="slide-header"><h2>Worked example — the salon app</h2></div>
            <div class="slide-content">
                <pre style="font-size: 18px;"># What to save
Appointments — name, service, date, time

# Who can see it
Just me, the stylist — after I log in

# Where it shows up
A "Today's appointments" list on my dashboard

Set up the database for this and connect it to
the booking form and the dashboard. Use Supabase.</pre>
                <p style="margin-top: 20px;" class="accent">Now the booking is still there tomorrow morning.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>22 / 36</span></div>
        </div>

        <div class="slide" data-slide="23">
            <div class="slide-header"><h2>Module 3 recap</h2></div>
            <div class="slide-content">
                <ul style="font-size: 26px; line-height: 1.7;">
                    <li>Backend = where your app remembers things</li>
                    <li>Supabase = Lovable's built-in one — just recognize the name</li>
                    <li>Ask in business terms: what to save, who sees it, where it shows</li>
                    <li>Lovable picks the tech — you describe the outcome</li>
                </ul>
                <p style="margin-top: 30px;" class="accent">Press &#8801; Menu for the next module.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>23 / 36</span></div>
        </div>
```

- [ ] **Step 2: Verify Module 3 structurally**

Run: `cd /Users/jdfiscus/dev/tech-town && grep -c 'data-slide=' 03-prompting-techniques/bonus.html`
Expected: `23`

Run: `grep -o '[0-9]* / 36' 03-prompting-techniques/bonus.html`
Expected: `1 / 36` through `23 / 36`, in order, no gaps, no duplicates.

- [ ] **Step 3: Manual browser check**

Reload `bonus.html`. From the menu, click card "3 — Data & backends" → lands on slide 17. Arrow through to slide 23. Confirm slides 21 and 22 have working `copy` buttons.

- [ ] **Step 4: Commit**

```bash
cd /Users/jdfiscus/dev/tech-town
git add 03-prompting-techniques/bonus.html
git commit -m "bonus: Module 3 — Data and backends (7 slides)"
```

---

## Task 5: Module 4 — Reading prompts well (slides 24–29)

**Files:**
- Modify: `03-prompting-techniques/bonus.html` (insert 6 slide blocks)

- [ ] **Step 1: Insert the Module 4 slides**

In `03-prompting-techniques/bonus.html`, insert the following 6 blocks immediately after the Module 3 recap slide (`data-slide="23"`), still inside `.slides-container`.

```html
        <div class="slide" data-slide="24">
            <div class="slide-header"><h2>Module 4 — Reading prompts well</h2></div>
            <div class="slide-content">
                <h3>Writing prompts is easy. Reading them is the skill.</h3>
                <p style="margin-top: 20px;">Voice it, meta-prompt it, and the AI hands you a polished prompt. Now what?</p>
                <p style="margin-top: 40px;" class="accent">You have to be able to tell if it's any good.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>24 / 36</span></div>
        </div>

        <div class="slide" data-slide="25">
            <div class="slide-header"><h2>You're the editor now</h2></div>
            <div class="slide-content">
                <p>When the AI writes the prompt, your job changes.</p>
                <ul style="margin-top: 24px;">
                    <li>You're not the writer — you're the editor</li>
                    <li>The AI will write something confident and generic</li>
                    <li>Confident &ne; correct. Generic &ne; yours.</li>
                </ul>
                <p style="margin-top: 24px;" class="accent">Editing is where your business knowledge actually goes in.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>25 / 36</span></div>
        </div>

        <div class="slide" data-slide="26">
            <div class="slide-header"><h2>The 4 layers = your read checklist</h2></div>
            <div class="slide-content">
                <ul style="font-size: 25px; line-height: 1.7;">
                    <li><strong>Role</strong> — is there one? Is it the right one?</li>
                    <li><strong>Context</strong> — is it about MY business, or any business?</li>
                    <li><strong>Task</strong> — is it one clear task, or five vague ones?</li>
                    <li><strong>Format</strong> — did it say how the answer should come back?</li>
                </ul>
                <p style="margin-top: 20px;" class="accent">Read the AI's prompt against these four. Fix what's thin.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>26 / 36</span></div>
        </div>

        <div class="slide" data-slide="27">
            <div class="slide-header"><h2>What "bad" looks like</h2></div>
            <div class="slide-content">
                <ul style="margin-top: 10px;">
                    <li><strong>Generic filler</strong> — "high-quality, user-friendly, modern" — sounds good, says nothing</li>
                    <li><strong>Missing business facts</strong> — no names, numbers, or specifics only you know</li>
                    <li><strong>Vague tasks</strong> — "build the app" instead of "design the booking form"</li>
                </ul>
                <p style="margin-top: 24px;" class="accent">If you could paste it for any business, it's not done yet.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>27 / 36</span></div>
        </div>

        <div class="slide" data-slide="28">
            <div class="slide-header"><h2>Worked example — fixing an AI prompt</h2></div>
            <div class="slide-content">
                <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 30px;">
                    <div>
                        <h3>AI wrote this</h3>
                        <pre style="font-size: 14px;">&lt;role&gt;Expert developer&lt;/role&gt;
&lt;context&gt;A booking app
for a small business&lt;/context&gt;
&lt;task&gt;Build a modern,
user-friendly app&lt;/task&gt;</pre>
                    </div>
                    <div>
                        <h3>You edit it to</h3>
                        <pre style="font-size: 14px;">&lt;role&gt;Senior product
engineer&lt;/role&gt;
&lt;context&gt;Solo hair stylist,
Asheville, 20 clients/wk,
paper appointment book&lt;/context&gt;
&lt;task&gt;Design the booking
form data model&lt;/task&gt;</pre>
                    </div>
                </div>
                <p style="margin-top: 20px;" class="accent">Same skeleton. You added the parts only you know.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>28 / 36</span></div>
        </div>

        <div class="slide" data-slide="29">
            <div class="slide-header"><h2>Module 4 recap</h2></div>
            <div class="slide-content">
                <ul style="font-size: 26px; line-height: 1.7;">
                    <li>When the AI writes the prompt, you're the editor</li>
                    <li>Read it against the 4 layers: Role, Context, Task, Format</li>
                    <li>Hunt for generic filler and missing business facts</li>
                    <li>If it fits any business, it doesn't fit yours yet</li>
                </ul>
                <p style="margin-top: 30px;" class="accent">Press &#8801; Menu for the next module.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>29 / 36</span></div>
        </div>
```

- [ ] **Step 2: Verify Module 4 structurally**

Run: `cd /Users/jdfiscus/dev/tech-town && grep -c 'data-slide=' 03-prompting-techniques/bonus.html`
Expected: `29`

Run: `grep -o '[0-9]* / 36' 03-prompting-techniques/bonus.html`
Expected: `1 / 36` through `29 / 36`, in order, no gaps, no duplicates.

- [ ] **Step 3: Manual browser check**

Reload `bonus.html`. From the menu, click card "4 — Reading prompts well" → lands on slide 24. Arrow through to slide 29. Confirm slide 28's two `<pre>` blocks render the `<role>`/`<context>`/`<task>` text literally (not as live tags) and each has a working `copy` button.

- [ ] **Step 4: Commit**

```bash
cd /Users/jdfiscus/dev/tech-town
git add 03-prompting-techniques/bonus.html
git commit -m "bonus: Module 4 — Reading prompts well (6 slides)"
```

---

## Task 6: Module 5 — More techniques (slides 30–36)

**Files:**
- Modify: `03-prompting-techniques/bonus.html` (insert 7 slide blocks)

- [ ] **Step 1: Insert the Module 5 slides**

In `03-prompting-techniques/bonus.html`, insert the following 7 blocks immediately after the Module 4 recap slide (`data-slide="29"`), still inside `.slides-container` (i.e., the last block sits right before `</div>` closing `.slides-container`, which is followed by `<button class="menu-btn"...>`).

```html
        <div class="slide" data-slide="30">
            <div class="slide-header"><h2>Module 5 — More techniques</h2></div>
            <div class="slide-content">
                <h3>Four more moves for when you're ready.</h3>
                <p style="margin-top: 20px;">You don't need these on day one. You'll want them by day three.</p>
                <p style="margin-top: 40px;" class="accent">Chaining &middot; Constraints &middot; Self-critique &middot; "3 approaches"</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>30 / 36</span></div>
        </div>

        <div class="slide" data-slide="31">
            <div class="slide-header"><h2>1 — Prompt chaining</h2></div>
            <div class="slide-content">
                <p>Don't ask for the whole app in one mega-prompt. Build it in a chain:</p>
                <pre style="font-size: 18px; margin-top: 20px;">Step 1 &rarr; "Design the data model. Just that."
Step 2 &rarr; "Now build the booking screen for it."
Step 3 &rarr; "Now add the confirmation email."</pre>
                <p style="margin-top: 20px;" class="accent">Each step is small, checkable, and builds on the last.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>31 / 36</span></div>
        </div>

        <div class="slide" data-slide="32">
            <div class="slide-header"><h2>2 — Constraints</h2></div>
            <div class="slide-content">
                <p>Tell the AI what <em>not</em> to do. It loves to over-build.</p>
                <pre style="font-size: 18px; margin-top: 20px;"># Constraints
- Keep it simple — no features I didn't ask for
- Don't add a login system yet
- One screen only
- If you're unsure, ask before building</pre>
                <p style="margin-top: 20px;" class="accent">Constraints keep you in control of the scope.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>32 / 36</span></div>
        </div>

        <div class="slide" data-slide="33">
            <div class="slide-header"><h2>3 — Self-critique with a rubric</h2></div>
            <div class="slide-content">
                <p>Give the AI a checklist and make it grade its own work.</p>
                <pre style="font-size: 18px; margin-top: 20px;">Before you show me the result, check it against:
- Does it match my business context?
- Is anything generic that should be specific?
- What did I forget to ask for?

Fix what fails, then show me.</pre>
                <p style="margin-top: 20px;" class="accent">The AI is a better critic than a first-drafter. Use that.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>33 / 36</span></div>
        </div>

        <div class="slide" data-slide="34">
            <div class="slide-header"><h2>4 — "Give me 3 approaches"</h2></div>
            <div class="slide-content">
                <p>Before committing to a build, ask for options.</p>
                <pre style="font-size: 18px; margin-top: 20px;">Don't build yet. Give me 3 ways to approach this,
with a one-line tradeoff for each. I'll pick one.</pre>
                <ul style="margin-top: 20px;">
                    <li>You see choices you didn't know you had</li>
                    <li>You learn the tradeoffs without building all three</li>
                </ul>
                <p style="margin-top: 16px;" class="accent">Cheap to ask. Expensive to skip.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>34 / 36</span></div>
        </div>

        <div class="slide" data-slide="35">
            <div class="slide-header"><h2>Copy-paste — all four</h2></div>
            <div class="slide-content">
                <pre style="font-size: 16px;">CHAIN:    "Just do step 1. We'll go one step at a time."

LIMIT:    "Keep it simple. No features I didn't ask for.
           Ask before adding anything extra."

CRITIQUE: "Check your result against my context and
           fix what's generic before showing me."

OPTIONS:  "Don't build yet — give me 3 approaches
           with tradeoffs. I'll pick one."</pre>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>35 / 36</span></div>
        </div>

        <div class="slide" data-slide="36">
            <div class="slide-header"><h2>Module 5 recap</h2></div>
            <div class="slide-content">
                <ul style="font-size: 26px; line-height: 1.7;">
                    <li><strong>Chain</strong> — build big things one small step at a time</li>
                    <li><strong>Constrain</strong> — tell it what not to do</li>
                    <li><strong>Critique</strong> — make it grade its own work</li>
                    <li><strong>Options</strong> — get 3 approaches before committing</li>
                </ul>
                <p style="margin-top: 30px;" class="accent">Press &#8801; Menu — that's all five modules.</p>
            </div>
            <div class="slide-footer"><span style="font-size: 13px; opacity: 0.6;">prompting-techniques.vercel.app/bonus</span><span>36 / 36</span></div>
        </div>
```

- [ ] **Step 2: Verify the full deck structurally**

Run: `cd /Users/jdfiscus/dev/tech-town && grep -c 'data-slide=' 03-prompting-techniques/bonus.html`
Expected: `36`

Run: `grep -o '[0-9]* / 36' 03-prompting-techniques/bonus.html | nl`
Expected: 36 lines, line N reading `N / 36` — no gaps, no duplicates.

Run: `grep -c 'slide-footer' 03-prompting-techniques/bonus.html`
Expected: `36`

- [ ] **Step 3: Manual browser check — full walkthrough**

Reload `bonus.html`. Test all five menu cards jump to slides 2, 10, 17, 24, 30 respectively. Arrow all the way from slide 1 to slide 36. Confirm: `≡ Menu` button hides on slide 1 and shows on 2–36; `≡ Menu` returns to slide 1 from any module slide; every `<pre>` block has a `copy` button that turns green and says `copied!` on click.

- [ ] **Step 4: Commit**

```bash
cd /Users/jdfiscus/dev/tech-town
git add 03-prompting-techniques/bonus.html
git commit -m "bonus: Module 5 — More techniques (7 slides)"
```

---

## Task 7: Wire `bonus.html` into the landing page and core deck

**Files:**
- Modify: `03-prompting-techniques/index.html`
- Modify: `03-prompting-techniques/slides.html:438-444` (final slide content)

- [ ] **Step 1: Add a bonus-modules card to the landing page**

In `03-prompting-techniques/index.html`, find the "Workshop Slides" card:

```html
            <div class="card"><a href="./slides.html">
                <h3>Workshop Slides</h3>
                <p>The deck from the live session.</p>
            </a></div>
```

Insert this new card immediately after it (so the two decks are adjacent in the grid):

```html
            <div class="card"><a href="./bonus.html">
                <h3>Bonus Modules</h3>
                <p>Going deeper — 5 optional deep-dives.</p>
            </a></div>
```

- [ ] **Step 2: Add a pointer line to the core deck's final slide**

In `03-prompting-techniques/slides.html`, find slide 28's content block:

```html
            <div class="slide-content" style="justify-content: center; text-align: center;">
                <h1 style="font-size: 72px;">Build time.</h1>
                <p style="margin-top: 40px; font-size: 28px; opacity: 0.8;">Questions? I'm right here.</p>
                <p style="margin-top: 60px; opacity: 0.6;">TechTown Start Studio &middot; JD Fiscus</p>
            </div>
```

Replace it with this (adds one accent line between the "Questions?" line and the credit line):

```html
            <div class="slide-content" style="justify-content: center; text-align: center;">
                <h1 style="font-size: 72px;">Build time.</h1>
                <p style="margin-top: 40px; font-size: 28px; opacity: 0.8;">Questions? I'm right here.</p>
                <p style="margin-top: 24px; font-size: 22px;" class="accent">Want more? Bonus modules &rarr; prompting-techniques.vercel.app/bonus</p>
                <p style="margin-top: 40px; opacity: 0.6;">TechTown Start Studio &middot; JD Fiscus</p>
            </div>
```

- [ ] **Step 3: Verify the wiring**

Run: `cd /Users/jdfiscus/dev/tech-town && grep -c 'bonus.html' 03-prompting-techniques/index.html`
Expected: `1`

Run: `grep -c 'bonus' 03-prompting-techniques/slides.html`
Expected: `1`

Run: `grep -c 'data-slide=' 03-prompting-techniques/slides.html`
Expected: `28` (confirm the core deck was not restructured — only the one line changed)

- [ ] **Step 4: Manual browser check**

Open `index.html` — confirm the "Bonus Modules" card appears after "Workshop Slides" and links to `bonus.html`. Open `slides.html`, arrow to slide 28 — confirm the accent pointer line shows and the slide still reads `28 / 28`.

- [ ] **Step 5: Commit**

```bash
cd /Users/jdfiscus/dev/tech-town
git add 03-prompting-techniques/index.html 03-prompting-techniques/slides.html
git commit -m "bonus: link bonus deck from landing page and core deck"
```

---

## Task 8: Write `bonus-outline.md` — speaker notes

**Files:**
- Create: `03-prompting-techniques/bonus-outline.md`

- [ ] **Step 1: Write the speaker notes file**

Create `03-prompting-techniques/bonus-outline.md` with this exact content:

```markdown
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
```

- [ ] **Step 2: Verify the file**

Run: `cd /Users/jdfiscus/dev/tech-town && grep -c '^## Module' 03-prompting-techniques/bonus-outline.md`
Expected: `5`

- [ ] **Step 3: Commit**

```bash
cd /Users/jdfiscus/dev/tech-town
git add 03-prompting-techniques/bonus-outline.md
git commit -m "bonus: speaker outline for the five modules"
```

---

## Task 9: Deploy to Vercel and verify live

**Files:** none (deploy only)

- [ ] **Step 1: Push all commits to origin**

```bash
cd /Users/jdfiscus/dev/tech-town
git push origin main
```

- [ ] **Step 2: Deploy to production**

Vercel CLI v53.4.0 lives at the proto-managed path (the one in `$PATH` is too old). Run:

```bash
cd /Users/jdfiscus/dev/tech-town/03-prompting-techniques
/Users/jdfiscus/.proto/tools/node/22.20.0/bin/vercel deploy --prod
```

Expected: a build completes and the output ends with `Aliased: https://prompting-techniques.vercel.app` (or similar production alias confirmation).

- [ ] **Step 3: Verify the bonus deck is live**

Run: `curl -sL https://prompting-techniques.vercel.app/bonus | grep -c 'data-slide='`
Expected: `36`

Run: `curl -sL https://prompting-techniques.vercel.app/bonus | grep -o 'goto([0-9]*)' | sort -u`
Expected includes: `goto(1)`, `goto(10)`, `goto(17)`, `goto(2)`, `goto(24)`, `goto(30)`

Run: `curl -sL https://prompting-techniques.vercel.app/ | grep -c 'bonus.html'`
Expected: `1` (landing page links to the bonus deck)

- [ ] **Step 4: Manual live check**

Open `https://prompting-techniques.vercel.app/bonus` in a browser. Click through the menu, confirm all five cards jump correctly, confirm the `≡ Menu` button and copy buttons work. Open `https://prompting-techniques.vercel.app/` and confirm the "Bonus Modules" card is present and links through.

---

## Self-Review

**1. Spec coverage:**

- New file `bonus.html` → Tasks 1–6. ✓
- New file `bonus-outline.md` → Task 8. ✓
- Modified `index.html` (card linking to bonus) → Task 7 Step 1. ✓
- Modified `slides.html` (pointer line on final slide) → Task 7 Step 2. ✓
- Slide 1 menu with 5 clickable cards → Task 1. ✓
- 5 modules, slides 2–36, uniform skeleton → Tasks 2–6, content matches spec's per-module breakdown. ✓
- `goto(n)` jump navigation + `≡ Menu` button shown on every slide except slide 1 → Task 1 script. ✓
- Shared with core deck: CSS tokens, `.slide` pattern, copy buttons, URL footer → Task 1 (CSS + script copied verbatim from `slides.html`, footer on every slide). ✓
- Module 5 as the deliberate exception (sampler, not single-technique skeleton) → Task 6 content reflects this (Hook → 4 technique slides → copy-paste → recap). ✓
- Hosting: deploys with the folder, reachable at `/bonus`, linked from landing page → Task 9 + Task 7. ✓
- Non-goal honored: `cheat-sheet.*` untouched — no task modifies it. ✓
- Non-goal honored: core deck arc unchanged except one pointer line — Task 7 Step 3 explicitly re-verifies `28` slides. ✓

No gaps found.

**2. Placeholder scan:** The bracketed tokens in slides 5, 7, 13, 21 (`[what I thought would happen]`, `[PROJECT]`, `[the one thing to change]`, `[the thing — e.g. ...]`) are intentional fill-in-the-blank content for the audience-facing prompt templates, consistent with the core deck's slide 26 (`[PROJECT]`). They are not plan placeholders. No "TBD"/"TODO"/"implement later" anywhere. Every slide's full HTML is in the plan.

**3. Type/name consistency:**
- `goto(n)` defined in Task 1 script; called with `goto(1)` (menu button), `goto(2)`, `goto(10)`, `goto(17)`, `goto(24)`, `goto(30)` (menu cards). Targets match the locked slide-numbering table and each module's first slide. ✓
- `menuBtn` variable, `.menu-btn` class, `.menu-card` class, `.menu-grid` class — defined in Task 1 CSS and HTML, used consistently. ✓
- Footer string `prompting-techniques.vercel.app/bonus` identical on all 36 slides. ✓
- `total` computed from `.slide` count (not hardcoded), so it is correct at every intermediate task state; only the footer display text is hardcoded `/ 36`, which is correct once all tasks complete. ✓

No issues found.
```
