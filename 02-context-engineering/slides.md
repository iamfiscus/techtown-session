# Context Engineering, Tooling & MCP for Founders
## Making AI Smarter Before It Talks

**JD Fiscus | TechTown Start Studio | February 2026**

---

## Slide 2: Light Callback

**Last time:** How to talk to AI.
**Today:** How to make AI smarter *before* it talks.

> "Prompting is what you say. Context engineering is everything AI sees."

---

## Slide 3: The Email Test — Kitchen Table

You get an email from a client asking to reschedule a meeting. To reply well you need:

| # | Context Needed | Why It Matters |
|---|---------------|----------------|
| 1 | Original meeting details | What was it about? |
| 2 | Your calendar | When are you free? |
| 3 | Their priority level | VIP client or cold lead? |
| 4 | Relationship history | 3rd email or 3-year partner? |
| 5 | Your current workload | Slammed or open? |

That's 5 types of context. Without any of them, your reply is worse. AI works the same way.

---

## Slide 4: The Email Test — Founder Desk

Same customer support email, same prompt. Two very different results:

**Zero Context:**
"Thank you for reaching out. We'd be happy to help. Please let us know your availability."
→ Generic garbage

**Rich Context (brand voice + customer history + product details + current policies):**
"Hi Sarah — since you've been on our Pro plan for 2 years, I've already applied the loyalty discount and rescheduled your onboarding call to Thursday at 2pm, which I see is open on your calendar."
→ Nails it

> "You wouldn't ask a new hire to reply to that email on their first day. Stop doing that to AI."

---

## Slide 5: Types of Context

4 types of context with simple analogies:

| Type | What It Is | Analogy | Founder Example |
|------|-----------|---------|-----------------|
| **Static** | Docs, brand guidelines, specs | Your company handbook | Product requirements, brand voice doc, pricing sheet |
| **Dynamic** | Live data that changes | Today's calendar | CRM data, current metrics, inventory levels |
| **Episodic** | History and past decisions | Your memory of past meetings | Conversation history, lessons learned, past mistakes |
| **Tool** | Outputs from connected systems | Calling someone to ask a question | Slack messages, database queries, API responses |

> "Most people only give AI static context. The magic happens when you add dynamic and tool context."

---

## Slide 6: The 4 Operations of Context Engineering

The framework founders can actually use:

| Operation | What It Means | Kitchen Table | Founder Example |
|-----------|--------------|---------------|-----------------|
| **Write** | Save context outside the window | Take notes so you don't forget | Save meeting notes to Obsidian, document decisions, create specs |
| **Select** | Pull the RIGHT context in | Grab only the relevant folder, not the whole filing cabinet | Search your notes, retrieve relevant docs, RAG |
| **Compress** | Keep only what matters | Summarize a 2-hour meeting into 5 bullet points | Summarize long threads, trim conversation history |
| **Isolate** | Split context for different tasks | Don't bring your grocery list to a board meeting | Separate chats for separate projects, fresh context for new tasks |

> "Context engineering is doing these 4 things deliberately instead of accidentally."

---

## Slide 7: Context Hydration & The Attention Budget

**Context hydration** = deliberately filling the context window with the right information before AI acts.

Kitchen table: Imagine reading a 500-page manual to fix a leaky faucet vs. reading the 2-page section on faucets. Both are "context" but one helps and one hurts.

**The attention budget:** AI has a limited budget for paying attention. Every token you add depletes it. After a certain point, adding MORE context makes AI WORSE.

[Chart: AI accuracy goes UP with relevant context, peaks, then goes DOWN as you add noise]

---

## Slide 8: The Attention Budget — Founder Desk

What happens when you paste your entire codebase into a chat vs. paste only the relevant file + error message?

**Entire codebase:** AI gets lost, gives generic advice, misses the actual problem.

**Relevant file + error:** AI focuses, identifies the bug, suggests the exact fix.

> "The goal isn't maximum context. It's optimal context."

---

## Slide 9: Context Rot

**Kitchen table:** You're on a 2-hour phone call. By minute 90, you've forgotten what was said in minute 10. AI has the same problem.

**What context rot looks like:**
- Long conversations get worse over time (founders experience this daily)
- Important instructions from early in the chat get "buried"
- AI starts contradicting its own earlier answers
- Stale information misleads decisions

---

## Slide 10: Context Rot — The Fixes

| Fix | Operation | What To Do |
|-----|-----------|------------|
| Start fresh conversations for new tasks | Isolate | Don't keep one giant chat forever |
| Summarize and carry forward key decisions | Compress | Distill, don't dump |
| Store context externally so you can re-inject | Write + Select | Build a second brain |
| Use tools that auto-refresh context | Dynamic | MCP, N8N |

> "If your AI is getting dumber the longer you talk, it's not broken. It's rotting. And now you know how to fix it."

Connects directly to Session 1 Slide 6: "Every bad prompt, every retry stays in context and pollutes future responses." Now you understand the mechanics.

---

# BLOCK 2: TOOLS AS CONTEXT SOLUTIONS

*Each tool is introduced as the solution to a specific context problem.*

---

## Slide 12: The Tool Map

One slide mapping context problems to tools:

| Context Problem | Operation | Tool |
|----------------|-----------|------|
| "I need to research across many docs" | Select | **NotebookLM** |
| "I need persistent memory across sessions" | Write | **Obsidian + Vector Brain** |
| "I need AI to access my live tools & data" | Dynamic context | **MCP** |
| "I need context to flow automatically" | Hydration | **N8N** |
| "I need to plan/structure before building" | Compress / Isolate | **SuperDesign** |

---

## Slide 13: NotebookLM — "The Research Brain"

*Solves: Select — pulling the right context from many sources*

**Kitchen table:** Imagine you could upload every book you've ever read and ask questions across all of them at once.

**Founder desk:** Upload your pitch deck, market research, competitor analysis, and 20 customer interview transcripts. Ask: "What's my biggest blind spot?" It connects dots across all of them.

---

## Slide 14: NotebookLM — Key Features

| Feature | What It Means |
|---------|--------------|
| 1M token context window | ~750K words — 8x previous limit |
| Saved conversation history | Episodic context persists across sessions |
| Custom goals/personas | Tell it your role so responses fit your needs |
| Audio overview | Turn research into a podcast for learning on the go |

**Context engineering connection:** NotebookLM is a **Select** engine. It takes massive amounts of static context and lets you pull out exactly what you need. It prevents context rot because it retrieves fresh from source docs every time.

---

## Slide 15: Obsidian + Vector Brain — "The Second Brain"

*Solves: Write — persistent context that survives across sessions*

**Kitchen table:** Your notes are scattered Post-its. A vector brain is a filing cabinet that also understands what the notes MEAN and how they connect.

**Founder desk:**
- Take your Obsidian vault (all markdown notes)
- Create vector embeddings (like GPS coordinates for ideas — similar ideas have nearby coordinates)
- Store in a GitHub repo or gist
- Now AI can search by MEANING, not just keywords
- Ask "What decisions have I made about pricing?" and get answers from notes 6 months ago

---

## Slide 16: Obsidian — How It Works

**Embeddings explained simply:**
"The word 'king' is near 'queen' and far from 'bicycle' in meaning-space."

**What to show:**
- Obsidian graph view — visual connections between notes
- GitHub gist/repo as persistent memory AI can read across sessions and tools

**Context engineering connection:** This is the **Write** operation at scale. You're building a permanent context store outside any single AI conversation. When context rots in one chat, your second brain doesn't.

---

## Slide 17: MCP — "The Universal Adapter"

*Solves: Dynamic context — connecting AI to live data and tools*

**Kitchen table:** Remember when every phone had a different charger? USB-C fixed that. MCP is USB-C for AI — one standard plug that connects AI to any tool.

**Founder desk:**
- MCP connects Claude/ChatGPT directly to your Slack, calendar, database, file system
- 97M monthly downloads. Adopted by ChatGPT, Claude, Gemini, Cursor, VS Code
- Donated to Linux Foundation — this is THE industry standard, not a fad
- MCP Apps (Jan 2026) — interactive dashboards and forms inside AI chats

---

## Slide 18: MCP — What It Enables

**Diagram:** AI ↔ MCP ↔ [Slack] [Calendar] [Database] [Files] [APIs]

"Instead of copy-pasting data INTO AI, MCP lets AI reach OUT and grab it."

**Context engineering connection:** MCP solves **dynamic context** — the live, changing data that static docs can't capture. It also enables the **Tool** context type. Your AI goes from "answering with what it knows" to "answering with what it can look up."

---

## Slide 19: N8N — "The Autopilot"

*Solves: Context hydration — automatically assembling the right context*

**Kitchen table:** You hire a virtual assistant who watches for triggers and takes action. "When X happens, gather Y, and do Z." That's a workflow.

**Founder desk examples:**
- Article link → spreadsheet → AI summary → social media posts → engagement tracking. All automated.
- New lead signs up → N8N grabs LinkedIn profile + company info + past interactions → hydrates AI agent → drafts personalized welcome email

Visual drag-and-drop, 400+ integrations, built-in AI agent builder.

**Context engineering connection:** N8N is the **hydration engine**. It automatically assembles context from multiple sources and delivers it to AI. Instead of you manually copy-pasting 5 things into a prompt, N8N does it for you every time.

---

## Slide 20: SuperDesign — "The Design Shortcut"

*Solves: Compress + Isolate — structuring intent before building*

**Kitchen table:** Instead of describing what you want a room to look like in 500 words, you show a photo and say "like this, but blue."

**Founder desk:**
- Describe a dashboard in plain language → get 10+ design variants → pick one → get production-ready code
- Open source, lives in VS Code/Cursor, runs offline
- Connects to session 1: "plan before you build" — SuperDesign is the planning tool

**Context engineering connection:** Design compresses your intent into a visual artifact. That visual becomes high-signal context for the build phase. You're isolating the "what should it look like" decision from the "how do I build it" decision.

---

# BLOCK 3: PUTTING IT ALL TOGETHER

---

## Slide 22: The Adoption App Case Study

Walk through the dog/cat adoption app, showing the CONTEXT DECISIONS at each stage:

| Stage | Context Decision | Tool Used | Operation |
|-------|-----------------|-----------|-----------|
| Research | "I need to understand adoption workflows" | NotebookLM (uploaded shelter docs, competitor apps) | Select |
| Memory | "I need to remember decisions across sessions" | Obsidian notes, GitHub repo | Write |
| Design | "I need to see it before building it" | SuperDesign (10 UI variants) | Compress |
| Build | "AI needs access to my codebase and data" | MCP (connected to files, DB) | Dynamic |
| Iterate | "Fresh context for each feature, not one giant chat" | New conversations per feature | Isolate |

---

## Slide 23: The Case Study Key Line

> "Every single thing here was written with AI. The difference isn't the prompts — it's the context I engineered around them."

---

## Slide 24: The Decision Framework — What Do I Need?

```
What do I need?
│
├── Research across many docs? --------→ NotebookLM
├── Remember things across sessions? --→ Obsidian + Vector Brain
├── Connect AI to live tools/data? ----→ MCP
├── Automate context assembly? --------→ N8N
└── Plan visually before building? ----→ SuperDesign
```

---

## Slide 25: The Decision Framework — What Operation?

```
What operation am I performing?
│
├── Need to save context? ----→ Write (Obsidian, docs, GitHub)
├── Need to retrieve context? → Select (NotebookLM, search, RAG)
├── Need to trim context? ----→ Compress (summarize, fresh chats)
└── Need to separate tasks? --→ Isolate (new chats, project separation)
```

---

## Slide 26: Context Audit Exercise

Interactive exercise for founders:

1. **List your top 3 business info sources** (email, CRM, docs, Slack, notes, calendar)
2. **Categorize each:** Static, Dynamic, Episodic, or Tool?
3. **Map the context problem:** Which operation do you need? (Write, Select, Compress, Isolate)
4. **Pick the tool:** Which tool from today unlocks this?
5. **Commitment:** One tool to try this week

---

## Slide 27: Common Context Mistakes

| Mistake | Why It Happens | Fix |
|---------|---------------|-----|
| Pasting everything into one chat | Think more = better | Attention budget — select, don't dump |
| Never starting fresh conversations | Don't want to "lose" context | Context rot — isolate and re-inject |
| Not saving important decisions | Live in the chat | Write — external storage (Obsidian, docs) |
| Manually copy-pasting data | Don't know about MCP/N8N | Connect tools — automate hydration |
| Same chat for every project | Convenience | Isolate — separate context per project |

---

## Slide 28: Quick Reference Card

**4 Types of Context:** Static | Dynamic | Episodic | Tool

**4 Operations:** Write | Select | Compress | Isolate

**5 Tools:**
| Tool | Solves |
|------|--------|
| NotebookLM | Research across many docs (Select) |
| Obsidian + Vector Brain | Memory across sessions (Write) |
| MCP | Live tools & data (Dynamic) |
| N8N | Automated context assembly (Hydration) |
| SuperDesign | Visual planning (Compress + Isolate) |

---

## Slide 29: Q&A

*What questions do you have?*

---

## Slide 30: Thank You

**JD Fiscus**
TechTown Start Studio

*Don't pray. Plan the context.*

**Takeaway Materials:**
- Quick reference card: 4 operations + 4 context types + tool map + decision tree
- QR codes to each tool
- Link to slides
