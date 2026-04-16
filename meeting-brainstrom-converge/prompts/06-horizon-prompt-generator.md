# Horizon Build Prompt Generator

This is the missing step between `brainstorm-diverge-converge` output and a Hostinger Horizons build.

The brainstorm output ranks features. Horizons needs a build spec. This prompt translates one into the other.

---

## The Prompt

Take the brainstorm output below and produce a single paste-ready prompt for Hostinger Horizons that will build a working MVP in one shot.

The output prompt must:

1. **Name the app** and state what it does in one sentence
2. **Describe the user** (who uses it, why, in what context)
3. **List each "Ship with MVP" feature** as a concrete UI requirement — what's on screen, what data it shows, how it's interacted with
4. **Specify the data shape** with realistic mock data — field names, types, example values. Include a "Seed Data" button that generates 200+ realistic rows.
5. **Name the UI stack**: React + Tailwind + shadcn/ui + recharts (for any charts)
6. **Pre-resolve every ambiguity** — Horizon should have zero questions to ask before building

Do NOT include in the output prompt:
- Authentication or login
- Backend APIs or database connections
- Multi-user features (unless the brainstorm explicitly called for them)
- Features ranked "Month 2" or "Defer" — MVP only

Structure the output prompt so it:
- Starts with "Build a..."
- Ends with a specific call to action ("Include a button labeled 'Seed Data' that populates the app with 200 realistic mock tickets")
- Reads as a single confident instruction, not a conversation

---

**Paste your brainstorm output below this line:**

