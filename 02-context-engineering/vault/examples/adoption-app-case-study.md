---
aliases: [adoption app, case study, pet adoption app]
tags: [example, context-engineering, case-study]
---

# Adoption App Case Study

> End-to-end walkthrough of [[context-engineering]] applied to building a real application.

## The Project

A dog/cat adoption app — built entirely with AI. The key: it wasn't the prompts that made it work. It was the **context decisions at each stage**.

## Stage-by-Stage

### 1. Research — [[select-operation]]
- **Context decision:** "I need to understand adoption workflows"
- **Tool:** [[notebooklm]] — uploaded shelter docs, competitor apps, adoption process guides
- **What happened:** NotebookLM connected dots across 20+ sources, identified key workflows and edge cases

### 2. Memory — [[write-operation]]
- **Context decision:** "I need to remember decisions across sessions"
- **Tool:** [[obsidian-vector-brain]] — saved decisions, architecture choices, user stories
- **What happened:** Every major decision was documented with rationale, creating [[episodic-context]] that persisted

### 3. Design — [[compress-operation]]
- **Context decision:** "I need to see it before building it"
- **Tool:** [[superdesign]] — generated 10 UI variants from plain language descriptions
- **What happened:** Visual designs compressed intent into artifacts. Picked the best one → high-signal context for the build phase

### 4. Build — [[dynamic-context]]
- **Context decision:** "AI needs access to my codebase and data"
- **Tool:** [[mcp]] — connected to files, database, build tools
- **What happened:** AI could read the actual codebase, query the database, and run commands — not just theorize

### 5. Iterate — [[isolate-operation]]
- **Context decision:** "Fresh context for each feature, not one giant chat"
- **What happened:** Each feature got its own conversation. Relevant context from [[obsidian-vector-brain|Obsidian]] was re-injected. No [[context-rot]].

## The Key Line

> "Every single thing here was written with AI. The difference isn't the prompts — it's the context I engineered around them."

## What This Demonstrates

| Principle | How It Showed Up |
|-----------|-----------------|
| [[optimal-context]] | Each phase got exactly the context it needed |
| [[context-rot]] prevention | Fresh conversations per feature |
| [[second-brain]] | Decisions persisted across all sessions |
| [[tool-map]] | Right tool for right context problem |
| All 4 operations | Write, Select, Compress, Isolate all used |

## The Workflow Pattern

This pattern works for any project:
1. **Research** with [[notebooklm]] (Select)
2. **Document** with [[obsidian-vector-brain]] (Write)
3. **Design** with [[superdesign]] (Compress)
4. **Build** with [[mcp]] (Dynamic)
5. **Iterate** with fresh conversations (Isolate)

See: [[decision-framework]] for choosing tools.

---

**See also:** [[context-engineering]], [[decision-framework]], [[tool-map]]

#example #case-study
