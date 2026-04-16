# Slide Outline: Meeting to Decision Dashboard in 45 Minutes

---

## 1. Hook (0:00 - 4:00)

**Talking Points:**
- "Meetings generate a ton of ideas. Almost none of them get built."
- Nick's quote: surface it as the problem statement. Every team has a version of this.
- The promise: by the end of this session, you will have a scored, estimated decision dashboard you can show your boss on Monday.
- Quick show of hands: "How many of you left a meeting this week with no clear next step?"
- Preview the pipeline: messy transcript --> brainstorm --> Fermi estimation --> live dashboard.

**VISUAL:** Single slide with the quote large and centered. Below it: a horizontal pipeline diagram showing VTT --> Brainstorm --> Fermi --> Dashboard, each step with an icon.

---

## 2. What's a Skill? (4:00 - 10:00)

**Talking Points:**
- A skill is structured markdown that tells any LLM how to think through a problem. Not code. Not a plugin. Just text.
- Show the lyndonkl/claude repo on GitHub. Walk through the folder structure: each skill is a markdown file with frontmatter.
- Open a SKILL.md file. Point out the sections: description, instructions, output format. "This is the whole thing."
- Demo in Claude Desktop: install thinking-frameworks, type "brainstorm," skill activates. 30 seconds.
- Demo portability: copy the same SKILL.md content, paste it into ChatGPT as context. Same framework, different LLM.
- Key takeaway: skills are portable text. They work anywhere that accepts a prompt.

**VISUAL:** Split screen. Left: GitHub repo file tree with a SKILL.md file open. Right: Claude Desktop showing the skill installed, then ChatGPT showing the same markdown pasted in.

---

## 3. The Scenario (10:00 - 14:00)

**Talking Points:**
- Setup: a 6-person support team is drowning. 1,400 tickets/week, 22-minute average handle time, $390K/year in labor.
- Show 2-3 raw VTT excerpts from the meeting transcript. Let the audience feel the chaos of a real meeting.
- "This is what most teams have after a brainstorm meeting: a messy transcript and good intentions."
- Hand out (or share link to) the problem template so the audience can follow along with their own scenario.
- Invite them to use the support scenario or swap in their own numbers.

**VISUAL:** A VTT transcript excerpt on screen, messy timestamps and all. Below it: a clean "Problem Card" showing the key anchors (1,400 tickets, 22 min, 6 agents, $65K each).

---

## 4. Brainstorm Converge (14:00 - 22:00)

**Talking Points:**
- Explain the three phases: Diverge (generate 20+ ideas), Cluster (group into themes), Converge (score and rank).
- Split-screen demo: Claude Desktop on the left (skill auto-loads via thinking-frameworks), ChatGPT on the right (skill pasted inline).
- Walk through diverge: both LLMs expand the raw idea list to 20+ ideas. Point out how each adds different ideas.
- Walk through cluster: both group ideas into 4-8 themes. Compare the cluster names.
- Walk through converge: both score on Impact, Feasibility, Speed-to-value. Show the top 3 winners.
- "Notice: same skill, same input, two different LLMs. The outputs are similar but not identical. That is the point -- you get multiple perspectives."

**VISUAL:** Split screen with Claude Desktop (left) and ChatGPT (right), both running the brainstorm-converge skill simultaneously. Highlight the top 3 results in each.

---

## 5. Fermi Estimation (22:00 - 30:00)

**Talking Points:**
- Take the top 2-3 ideas from the converge step. Feed them into the Fermi estimation skill.
- Show the Fermi card format: cost to implement, ticket deflection %, annual savings, time to impact, confidence level.
- Walk through one estimate live: decompose into components, show the math, sanity-check the number.
- Surface the surprising number: "This one idea could save $127K/year and pay for itself in 6 weeks."
- Audience follows along: paste their own top ideas into the Fermi prompt. Give them 3 minutes.
- "Fermi estimation turns gut feelings into defensible numbers. You do not need a spreadsheet."

**VISUAL:** A Fermi card rendered on screen, large and readable. Key numbers highlighted in color. Below: the decomposition math in smaller text.

---

## 6. Build with Horizons (30:00 - 40:00)

**Talking Points:**
- Switch to Hostinger Horizons. "We have scored ideas and Fermi numbers. Now let's make it visual."
- Paste a prompt that includes the brainstorm winners and Fermi estimates. Ask Horizons to generate a decision dashboard.
- Dashboard renders: show a comparison table, a cost-vs-impact chart, a recommendation summary.
- Walk through the output: "This is something you can screenshot and drop into a Slack thread or a board deck."
- One sentence on Lovable at [38:00]: "If you want to go further and turn this into a full interactive app, check out Lovable."
- Audience tries it: paste their own data into Horizons. Give them 3 minutes.

**VISUAL:** Hostinger Horizons generating a dashboard in real time. Show the rendered output: a clean dashboard with cards, a chart, and a recommendation block. Hostinger branding visible.

---

## 7. Share-Out (40:00 - 44:00)

**Talking Points:**
- "Who wants to share? Give us your top idea, the killer Fermi stat, and what your dashboard looks like."
- Call on 2-3 volunteers. Keep each to 60 seconds.
- React to each: reinforce how fast they went from transcript to dashboard.
- "You just did in 40 minutes what usually takes a week of follow-up meetings."

**VISUAL:** Audience camera / screen share from volunteers. If in-person, walk to the audience with a mic.

---

## 8. Close (44:00 - 45:00)

**Talking Points:**
- Recap: messy meeting --> structured brainstorm --> defensible estimates --> visual dashboard. All with portable skills.
- Assets link: "[PLACEHOLDER URL] -- everything from today: prompts, guides, the VTT file."
- Hostinger CTA: "Hostinger Horizons is free to try. Build your next dashboard in minutes, not days."
- Skills repo: github.com/lyndonkl/claude -- "Install thinking-frameworks and start using these skills today."
- Takeaway: "Skills are portable prompts. They work in Claude, ChatGPT, or any LLM. Go build something."

**VISUAL:** Final slide with three items stacked: assets link, Hostinger Horizons URL, lyndonkl/claude repo link. Hostinger and Tech Town logos at the bottom.
