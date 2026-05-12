# V4 Prompt Template

This is the structure you build to by minute 45. Fill in the bracketed sections with YOUR project details. The structure is what makes it work — don't skip sections.

---

## Copy-paste template

````
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
````

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
