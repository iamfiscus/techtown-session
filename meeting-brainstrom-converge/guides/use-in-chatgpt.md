# Use Skills as Portable Markdown in ChatGPT

1. Go to [github.com/lyndonkl/claude](https://github.com/lyndonkl/claude) and find the skill you want (e.g., `brainstorm-diverge-converge`).
2. Open the **SKILL.md** file and click **Raw**. Select all and **copy** the full contents.
3. In ChatGPT, you have two options:
   - **Option A -- Custom Instructions:** Go to **Settings > Personalization > Custom Instructions**. Paste the skill markdown into the "What would you like ChatGPT to know?" field. Save.
   - **Option B -- Inline context:** Start a new chat. Paste the skill markdown as your first message, then follow up with your actual prompt.
4. Prompt normally. ChatGPT will follow the skill's framework, phases, and output format.
5. To switch skills, just paste a different SKILL.md. Each skill is self-contained.

**Tip:** You can do this with ANY skill from the repo -- they are just markdown. Browse the full list at the repo to find frameworks for estimation, decision-making, postmortems, and more.

> This works with any LLM that accepts system prompts or long context -- Gemini, Mistral, local models, etc.
