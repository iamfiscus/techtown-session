---
aliases: [CE, context eng]
tags: [core-concept, context-engineering]
---

# Context Engineering

> "Context engineering is doing the 4 operations deliberately instead of accidentally."

Context engineering is the practice of **deliberately controlling what information AI sees** before and during a conversation. It's the bridge between [[prompt-engineering]] (what you say) and great AI output.

## Why It Matters

The quality of AI output depends more on the **context you engineer around it** than the prompt itself. Two identical prompts with different context produce wildly different results. See: [[the-email-test]].

## The Framework

### 4 Types of Context
1. [[static-context]] — Documents, specs, brand guidelines
2. [[dynamic-context]] — Live data that changes (CRM, metrics)
3. [[episodic-context]] — History and past decisions
4. [[tool-context]] — Outputs from connected systems

### 4 Operations
1. [[write-operation]] — Save context outside the [[context-window]]
2. [[select-operation]] — Pull the RIGHT context in
3. [[compress-operation]] — Keep only what matters
4. [[isolate-operation]] — Split context for different tasks

## Key Concepts
- [[context-hydration]] — Deliberately filling the context window with the right information
- [[attention-budget]] — AI has a limited budget for paying attention
- [[context-rot]] — Long conversations degrade over time
- [[optimal-context]] — The goal is optimal, not maximum

## Tools That Solve Context Problems
See: [[tool-map]] for the full mapping.

| Tool | Operation Solved |
|------|-----------------|
| [[notebooklm]] | [[select-operation]] |
| [[obsidian-vector-brain]] | [[write-operation]] |
| [[mcp]] | [[dynamic-context]] |
| [[n8n]] | [[context-hydration]] |
| [[superdesign]] | [[compress-operation]] + [[isolate-operation]] |

## Relationship to Prompting
[[prompt-engineering]] teaches you **what to say**. Context engineering teaches you **what AI should see**. They're complementary — great prompts with bad context still produce bad output.

## Case Study
See: [[adoption-app-case-study]] for an end-to-end example of context engineering in practice.

## Common Mistakes
See: [[common-context-mistakes]]

---

**See also:** [[decision-framework]], [[context-audit]], [[the-email-test]]

#core-concept #framework
