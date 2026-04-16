---
aliases: [email test, email example, the email example]
tags: [example, context-engineering, foundational]
---

# The Email Test

> The foundational example that demonstrates why context engineering matters.

## The Scenario

You get an email from a client asking to reschedule a meeting. To reply well, you need **5 types of context**:

| # | Context | Why | Type |
|---|---------|-----|------|
| 1 | Original meeting details | What was it about? | [[static-context]] |
| 2 | Your calendar | When are you free? | [[dynamic-context]] |
| 3 | Their priority level | VIP or cold lead? | [[dynamic-context]] |
| 4 | Relationship history | 3rd email or 3-year partner? | [[episodic-context]] |
| 5 | Your current workload | Slammed or open? | [[dynamic-context]] |

Without ANY of them, your reply is worse. AI works the same way.

## The Demo

### Same prompt. Different context.

**Zero context (generic garbage):**
> "Thank you for reaching out. We'd be happy to help. Please let us know your availability."

**Rich context (nails it):**
> "Hi Sarah — since you've been on our Pro plan for 2 years, I've applied the loyalty discount and rescheduled your onboarding to Thursday 2pm."

The **prompt was identical**. The **context** made the difference.

## The Key Line

> "You wouldn't ask a new hire to reply to that email on their first day. Stop doing that to AI."

See: [[new-hire-analogy]]

## What It Teaches

1. **Context matters more than prompts** — Same prompt, different results
2. **Multiple types of context combine** — Static + Dynamic + Episodic
3. **Missing context = worse output** — Each gap degrades quality
4. **AI needs the same briefing humans do** — It's not magic, it's information

## Connection to the Framework

The email test naturally introduces all 4 context types:
- Meeting details = [[static-context]]
- Calendar/workload = [[dynamic-context]]
- Relationship history = [[episodic-context]]
- The act of checking these = [[tool-context]]

And it motivates the operations:
- How to save context? → [[write-operation]]
- How to pull in the right context? → [[select-operation]]
- How to summarize long histories? → [[compress-operation]]
- How to keep this email separate from other work? → [[isolate-operation]]

---

**See also:** [[context-engineering]], [[new-hire-analogy]], [[common-context-mistakes]]

#example #foundational
