# Fermi Estimate Top Options

> **ChatGPT Version** — paste this directly into chat.openai.com

You are using the Fermi Estimation method. For each of the top 2-3 ideas I provide, follow this process exactly:

---

## Fermi Estimation Workflow

**Step 1 — Clarify the question and metric:**
State precisely what you are estimating (e.g., "Annual cost savings from deploying an onboarding FAQ bot").

**Step 2 — Decompose into estimable components:**
Break the estimate into 3-5 smaller quantities you can reason about independently. Show the decomposition tree.

**Step 3 — Estimate using anchors:**
Use the meeting metrics below as your anchors. For each component, state your estimate and one sentence of reasoning.

**Step 4 — Bound with upper and lower limits:**
For each component, provide an optimistic, realistic, and pessimistic value. Propagate these through to the final estimate.

**Step 5 — Calculate and sanity-check:**
Compute the final number. Then ask: "Does this pass the smell test?" Compare against a known benchmark or industry average.

**Step 6 — Triangulate with an alternate path:**
Re-estimate using a completely different decomposition. If the two paths differ by more than 3x, investigate why.

---

## Anchors from the Meeting

- 1,400 tickets per week
- 22 minutes average handle time per ticket
- 6 support agents at $65K/year each ($390K total labor)
- 30% of tickets are onboarding questions
- Current tools: Zendesk, Notion, Slack

## What to Estimate for Each Idea

1. **Cost to implement** — Break down into time (person-weeks) and money (tools, licenses, contractors)
2. **Potential ticket deflection** — What percentage of the 1,400 weekly tickets could this eliminate? Absolute number per week?
3. **Annual cost savings** — Based on reduced agent time, fewer tickets, or efficiency gains
4. **Time to first impact** — How many weeks until the first measurable improvement?

## Output Format

Present each idea as a Fermi card:

```
IDEA: [Name]
---------------------------------------------
Cost to implement:    $XX,XXX  (X person-weeks)
Ticket deflection:    XX% (~XXX tickets/week)
Annual savings:       $XXX,XXX
Time to first impact: X weeks
Confidence:           [Low / Medium / High]
Key assumption:       [The one thing that most affects this estimate]
```

Then show your work: the decomposition, ranges, and sanity checks for each estimate.

---

**Paste your top 2-3 converged ideas below this line:**

