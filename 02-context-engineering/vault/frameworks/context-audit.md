---
aliases: [audit, context audit exercise, self-audit]
tags: [framework, context-engineering, exercise, practical]
---

# Context Audit

> An exercise to map your own context engineering needs and pick the right tools.

## The 5-Step Audit

### Step 1: List Your Top 3 Business Info Sources
Where does your most important business information live?

Examples:
- Email, CRM, Google Docs, Slack, Obsidian notes, calendar, spreadsheets, databases, project management tools, customer support tickets

### Step 2: Categorize Each Source
For each source, identify the context type:

| Source | Type |
|--------|------|
| Product specs | [[static-context]] |
| CRM pipeline | [[dynamic-context]] |
| Meeting notes | [[episodic-context]] |
| Slack messages | [[tool-context]] |
| Brand guidelines | [[static-context]] |
| Sales metrics | [[dynamic-context]] |

### Step 3: Map the Context Problem
For each source, which operation do you need?

| Problem | Operation |
|---------|-----------|
| "I can't find it when I need it" | [[select-operation]] |
| "I keep losing track of decisions" | [[write-operation]] |
| "There's too much to paste in" | [[compress-operation]] |
| "Different projects get mixed up" | [[isolate-operation]] |
| "I'm always copy-pasting the same data" | [[context-hydration]] (automate it) |

### Step 4: Pick the Tool
Match your operation to the right tool:

See: [[decision-framework]] and [[tool-map]]

### Step 5: Commitment
**Pick ONE tool to try this week.** Start small. One tool. One workflow.

Recommended starting point: [[notebooklm]] — upload 3 documents you reference often and ask questions across them.

## Example Audit

| Source | Type | Problem | Operation | Tool |
|--------|------|---------|-----------|------|
| Customer interviews (20 transcripts) | [[static-context]] | Can't find patterns across them | [[select-operation]] | [[notebooklm]] |
| Pricing decisions (scattered notes) | [[episodic-context]] | Keep losing track | [[write-operation]] | [[obsidian-vector-brain]] |
| Slack customer feedback | [[dynamic-context]] + [[tool-context]] | Manual copy-paste | [[context-hydration]] | [[mcp]] or [[n8n]] |

## After the Audit

Now you have:
1. A clear picture of your **context landscape**
2. Specific **operations** you need to perform
3. **Tools** matched to your actual problems
4. A **starting point** for this week

---

**See also:** [[decision-framework]], [[tool-map]], [[context-engineering]], [[common-context-mistakes]]

#framework #exercise #practical
