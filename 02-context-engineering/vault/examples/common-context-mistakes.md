---
aliases: [mistakes, common mistakes, anti-patterns, what not to do]
tags: [example, context-engineering, mistakes]
---

# Common Context Mistakes

> What most people get wrong with AI context — and how [[context-engineering]] fixes each one.

## The 5 Most Common Mistakes

### 1. Pasting Everything Into One Chat
**Why it happens:** People think more context = better results.
**Why it's wrong:** Depletes the [[attention-budget]]. Noise drowns out signal.
**Fix:** [[select-operation]] — be deliberate about what goes in. See: [[optimal-context]].

### 2. Never Starting Fresh Conversations
**Why it happens:** Fear of "losing" context from the current chat.
**Why it's wrong:** [[context-rot]] makes long conversations progressively worse.
**Fix:** [[isolate-operation]] — Write key context externally ([[write-operation]]), then start fresh.

### 3. Not Saving Important Decisions
**Why it happens:** Decisions "live" in the chat and feel accessible.
**Why it's wrong:** Chat context is ephemeral. Close the tab, lose the decisions.
**Fix:** [[write-operation]] — Save to [[obsidian-vector-brain|Obsidian]], docs, or GitHub. Build a [[second-brain]].

### 4. Manually Copy-Pasting Data
**Why it happens:** Don't know about [[mcp]] or [[n8n]].
**Why it's wrong:** Manual hydration is slow, error-prone, and quickly stale.
**Fix:** Connect tools. Use [[mcp]] for interactive data access. Use [[n8n]] for automated [[context-hydration]].

### 5. Same Chat for Every Project
**Why it happens:** Convenience — one chat is easier to manage.
**Why it's wrong:** Projects contaminate each other. Feature A's context confuses Feature B.
**Fix:** [[isolate-operation]] — Separate chats per project. See: [[grocery-list-analogy]].

## Root Causes

Most mistakes trace back to **not knowing the framework**:

| Root Cause | Leads To | Framework Solution |
|-----------|----------|-------------------|
| Don't know about [[attention-budget]] | Context dumping | [[select-operation]], [[optimal-context]] |
| Don't know about [[context-rot]] | Endless conversations | [[isolate-operation]], [[compress-operation]] |
| Don't know about [[write-operation]] | Lost decisions | [[second-brain]], [[obsidian-vector-brain]] |
| Don't know about [[mcp]]/[[n8n]] | Manual data entry | [[tool-context]], [[workflow-automation]] |

## Connection to Session 1

Session 1 covered "Common Prompting Mistakes." Most of those were actually context problems in disguise:
- "Too vague" → Missing [[static-context]]
- "Too much at once" → Needed [[isolate-operation]]
- "No context" → Needed [[context-hydration]]

See: [[prompt-engineering]]

---

**See also:** [[context-engineering]], [[attention-budget]], [[context-rot]], [[the-email-test]]

#example #mistakes
