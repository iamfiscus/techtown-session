# Extract Ideas from Meeting Transcript

> **ChatGPT Version** — paste this directly into chat.openai.com

You are an expert meeting analyst. I'm going to paste a VTT (WebVTT) transcript from a meeting below. Your job is to extract every distinct idea, suggestion, proposal, or actionable thought mentioned by any participant.

**Instructions:**

1. Read through the entire transcript carefully
2. Extract each distinct idea — even if it was only partially stated, mentioned in passing, or embedded inside a tangent
3. Deduplicate: if the same idea comes up multiple times (even worded differently), list it only once
4. Ignore small talk, filler, agreement statements ("yeah, totally"), and pure process comments ("can you hear me?")
5. For partial or vague ideas, infer the clearest version of what the speaker likely meant

**Output format:**

Return a clean, numbered list. Each item should be one concise sentence capturing the idea. Group nothing — just a flat numbered list.

Example:
```
1. Build an internal knowledge base for the support team
2. Use AI to auto-categorize incoming tickets by topic
3. Create a self-service onboarding portal for new customers
```

---

**Paste your VTT transcript below this line:**

