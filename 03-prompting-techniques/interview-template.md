# Interview Technique

The rescue move. Use this when you don't know what to ask for next, when Lovable is stuck, or when your idea is too vague to specify.

---

## The prompt

````
I want to build [PROJECT, 1-2 SENTENCES].

Before we write anything, interview me about my project.
Ask one question at a time. Wait for my answer before
the next question. Don't ask multiple questions at once.

When you have enough to write a clear spec for the next
step, summarize what you heard back to me, and we'll
start there.
````

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
