# Interview-to-Lovable Starter Template
## TechTown Start Studio | Session 2 | February 2026

---

## How to Use This Template

You have a spec from your AI interview (Session 1's Golden Prompt).
This template turns that spec into Lovable-ready prompts.

**Three steps. Three types of prompts. That's it.**

---

## Step 1: Foundation Prompt
### Set up the shell before adding features

```
I'm building [APP NAME], a [ONE-SENTENCE DESCRIPTION].

Tech stack: Use React with TypeScript and Tailwind CSS.

Create the app foundation with:
- Design style: [REFERENCE A REAL APP — e.g., "warm and nurturing like Calm",
  "clean and minimal like Notion", "bold and modern like Stripe"]
- Navigation: [DESCRIBE — e.g., "bottom tab bar with Home, Dashboard,
  Settings" or "left sidebar with collapsible menu"]
- Color scheme: [PRIMARY] with [ACCENT] — e.g., "soft sage green with warm cream"
- Typography: Clean sans-serif, generous spacing
- Mobile-first layout

Start with just the layout shell and navigation.
Don't add any features yet.
```

### How to fill it in:

| Field | Where to find it | Example |
|-------|------------------|---------|
| APP NAME | Your project | Digital Doula |
| ONE-SENTENCE DESCRIPTION | First answer from your interview | "pregnancy and postpartum companion for expecting mothers" |
| DESIGN STYLE | Think of an app you love the look of | "warm and nurturing like Calm" |
| NAVIGATION | Your spec's feature list becomes tabs/pages | "Bottom tabs: Home, Timeline, My Village, Journal, Settings" |
| COLOR SCHEME | Your brand or pick from your design reference | "soft sage green (#7C9A8E) with warm cream (#FFF8F0)" |

---

## Step 2: Feature Prompts
### Add ONE feature at a time from your spec

```
Add [FEATURE NAME] to the app.

PURPOSE: [One sentence — what does this feature do?]

USER FLOW:
1. User [first action — e.g., "taps the Invite button"]
2. System [response — e.g., "shows a modal with email field"]
3. User [next action — e.g., "enters email and taps Send"]
4. System [result — e.g., "shows pending invite card with 7-day countdown"]

UI DETAILS:
- [Layout — e.g., "card-based list of village members"]
- [Key elements — e.g., "avatar circle, name, role badge"]
- [Interactive parts — e.g., "tap card to manage permissions"]
- [Empty state — e.g., "illustration with 'Invite your village' button"]

Keep the existing design style consistent.
```

### How to fill it in:

| Field | Where to find it | Example |
|-------|------------------|---------|
| FEATURE NAME | Your spec's feature list | "My Village invite system" |
| PURPOSE | Your spec's overview/user stories | "Let users invite up to 2 support people" |
| USER FLOW | Your spec's user flow section (steps 1-4 max) | See above |
| UI DETAILS | Think about what the screen looks like | Cards, buttons, modals, empty states |

### Pro tips:
- Pull user flow directly from your spec's "User Flow" section
- If your spec has 6 features, that's 6 separate prompts
- Check Lovable's output after EACH prompt before moving on
- Order matters: build the most important feature first

---

## Step 3: Refinement Prompts
### Polish what Lovable gives you

```
Improve the [COMPONENT NAME] with these specific changes:

VISUAL:
- [Change 1 — e.g., "make the header text larger and bold"]
- [Change 2 — e.g., "add a soft shadow to the cards"]

BEHAVIOR:
- [Change 1 — e.g., "the invite modal should close when clicking outside"]
- [Change 2 — e.g., "show a success toast after sending an invite"]

Don't change anything else.
```

### When to use refinement prompts:
- After every feature prompt, review what Lovable built
- Fix visual issues (spacing, colors, sizing)
- Fix behavior issues (buttons, modals, transitions)
- Always say "Don't change anything else" to prevent Lovable from breaking other things

---

## Quick Reference: Style Keywords That Work

Use these in your Foundation or Feature prompts:

| Keyword | What it does |
|---------|-------------|
| "card-based layout" | Organized content in clean boxes |
| "generous whitespace" | Breathing room, not cramped |
| "subtle shadows" | Depth without heaviness |
| "rounded corners" | Friendly, modern feel |
| "mobile-first" | Designed for phones first |
| "sticky navigation" | Header stays while scrolling |
| "empty state with illustration" | Nice placeholder when no data |
| "skeleton loading" | Smooth loading animation |
| "glassmorphism" | Frosted glass effect |
| "gradient hero section" | Eye-catching top banner |

---

## Quick Reference: Design References That Work

Instead of describing from scratch, reference apps people know:

| If you want... | Say... |
|----------------|--------|
| Clean and minimal | "like Notion's clean interface" |
| Warm and friendly | "like Calm or Headspace" |
| Bold and professional | "like Stripe's dashboard" |
| Social and engaging | "like Instagram's card layout" |
| Data-rich dashboard | "like Linear's project view" |
| Simple and focused | "like the Apple website" |

---

## Example: Digital Doula → My Village

Here's how we translated the Session 1 spec into Lovable prompts:

### From the spec:
- Feature: My Village (support invite system)
- Max 2 members, 3 permission tiers
- Email + link invites, 7-day expiration
- Silent removal for safety

### Prompt sequence:

**Prompt 1 (Foundation):**
> App shell with bottom nav, sage green + cream, Calm-like style

**Prompt 2 (My Village tab):**
> Empty state with illustration → Invite button → Email/link modal → Pending card

**Prompt 3 (Permission tiers):**
> Three-card selector: Full Access, Updates Only, Appointments Only

**Prompt 4 (Member dashboard):**
> Member cards with avatar, name, role badge, manage button

**Prompt 5 (Refinement):**
> Larger empty state illustration, status badges (amber/green/gray), slide-up manage panel

**5 focused prompts. Not 1 mega-prompt.**

---

## The Complete Pipeline

```
┌─────────────────────────────────────────────────────────────┐
│                     YOUR TOOLKIT                            │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  SESSION 1: The Golden Prompt                               │
│  ─────────────────────────────                              │
│  "Interview me one question at a time about [FEATURE]..."   │
│  → Gets you a SPEC                                          │
│                                                             │
│  SESSION 2: The Starter Template                            │
│  ───────────────────────────────                            │
│  1. Foundation Prompt  → App shell + style                  │
│  2. Feature Prompts    → One feature at a time              │
│  3. Refinement Prompts → Polish and iterate                 │
│  → Gets you a WORKING APP                                   │
│                                                             │
│  PIPELINE:                                                  │
│  Plan → Interview → Spec → [Template] → Lovable → Ship     │
│  FREE    FREE       FREE    FREE         PAID      DONE     │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Your Homework

1. Open your spec from Session 1 (or create one with the Golden Prompt)
2. Fill in the Foundation Prompt template
3. List your features — one Feature Prompt each
4. Open Lovable and go prompt by prompt
5. Refine after each step

**Stuck?** TechTown mentors are here. Office hours available.

---

*Don't pray. Plan. Then translate.*

*TechTown Start Studio | February 2026*
