# Facilitator Script -- JD's Speaking Notes

---

## Hook

**[0:00]** SAY: "Alright, let's get into it. Here's the thing about meetings -- they are incredible idea machines. People riff, they build on each other's thoughts, someone says something brilliant between bites of a sandwich. And then... nothing happens. The transcript sits in a Google Drive folder and dies."

**[0:45]** SAY: "Nick put it perfectly --" (read Nick's quote from the slide). "That is the gap we are closing today."

**[1:30]** SAY: "Here is the promise. In the next 45 minutes, you are going to take a messy meeting transcript, run it through two AI skills, and walk out with a decision dashboard you could show your team on Monday. Not a toy. An actual artifact."

**[2:00]** DO: Raise your own hand first. SAY: "Quick show of hands -- how many of you left a meeting this week with action items that nobody wrote down?" (pause, look around) "Yeah. That is normal. We are going to fix that."

**[2:30]** SAY: "Here is the pipeline." DO: Point to the diagram on screen. "Messy transcript goes in. Brainstorm skill organizes and scores the ideas. Fermi estimation puts real numbers on the winners. And then we build a dashboard in Hostinger Horizons. Four steps, 45 minutes."

**[3:30]** SAY: "And the cool part -- everything we use today works in Claude Desktop AND ChatGPT. I will show you both. These are portable tools, not vendor lock-in."

---

## What's a Skill?

**[4:00]** TRANSITION: "Okay, so what even is a skill? Let me show you."

**[4:15]** DO: Switch screen to GitHub -- github.com/lyndonkl/claude. SAY: "This is a public repo by Kushal. It is full of thinking frameworks -- brainstorming, estimation, decision matrices, all kinds of stuff. Each one is a skill."

**[4:45]** SAY: "A skill is just a markdown file. That is it. No code, no API, no plugin architecture. It is structured text that tells an LLM how to think through a specific kind of problem."

**[5:15]** DO: Click into a SKILL.md file. SAY: "Look at this. There is a description, instructions, an output format. This is the entire skill. You could print this on a piece of paper."

**[5:45]** DO: Switch to Claude Desktop. SAY: "Now watch. In Claude Desktop, I install the thinking-frameworks skill set." DO: Show the installation (Settings > add skill or search for thinking-frameworks). SAY: "Done. Now when I type 'brainstorm,' the skill activates automatically."

**[6:30]** DO: Type "brainstorm" in Claude Desktop and show the skill kicking in. SAY: "See that? It loaded the framework. It knows the phases. I did not have to explain anything."

**[7:00]** TRANSITION: "Now here is where it gets interesting." DO: Switch to ChatGPT in a browser tab.

**[7:15]** SAY: "ChatGPT does not have a skill system. But skills are just markdown. So I copy the SKILL.md content --" DO: Copy the markdown from GitHub. "-- and I paste it right into the chat." DO: Paste it into ChatGPT.

**[7:45]** SAY: "That is it. ChatGPT now follows the same framework. Same structure, same phases, same output format. The skill is portable."

**[8:15]** SAY: "This is the big idea I want you to take away today. Skills are portable text. They are not locked to one tool. If your LLM can read, it can run a skill."

**[8:45]** SAY: "If you want to follow along, there are two setup guides in the repo. One for Claude Desktop, one for ChatGPT. Pick whichever tool you have open." DO: Drop links in chat or point to the handout.

**[9:30]** SAY: "Everyone good? Got a skill loaded? Great. Let's use it."

---

## The Scenario

**[10:00]** TRANSITION: "Alright, let's set the scene."

**[10:15]** SAY: "Imagine you run a support team. Six agents. They are handling 1,400 tickets a week. Average handle time is 22 minutes. That is almost $400K a year in labor alone. And they are drowning."

**[10:45]** DO: Show VTT excerpt on screen. SAY: "The team had a brainstorm meeting. Here is what the transcript looks like." (pause) "Messy, right? Timestamps, cross-talk, half-finished sentences. This is real life."

**[11:15]** SAY: "Somewhere in this mess are 15 to 20 solid ideas. But good luck finding them by reading through 45 minutes of transcript."

**[11:45]** SAY: "So step one: we already ran an extraction prompt on this transcript and pulled out a clean idea list. That is in your materials as prompt number one. We are going to skip that step live and start from the extracted ideas."

**[12:15]** DO: Show the extracted idea list on screen. SAY: "Here is what came out. A flat numbered list of every distinct idea from the meeting. Duplicates removed, tangents filtered."

**[12:45]** SAY: "Now, if you want to use your own scenario, go for it. Swap in your own numbers. The skills do not care about the specific problem -- they care about the structure."

**[13:30]** SAY: "Everyone got the idea list? Good. Let's brainstorm."

---

## Brainstorm Converge

**[14:00]** TRANSITION: "Time to run the brainstorm-converge skill. This has three phases: diverge, cluster, converge."

**[14:15]** DO: Set up split screen -- Claude Desktop on the left, ChatGPT on the right. SAY: "I am going to run this in both tools at the same time so you can see the portability in action."

**[14:45]** DO: Paste the brainstorm-converge prompt (prompt 02) into both tools, along with the extracted idea list. SAY: "Same prompt, same input, two different LLMs. Let's see what happens."

**[15:15]** SAY: "Phase one is diverge. Both models are expanding the idea list to 20-plus ideas. They are adding ideas we did not think of -- combinations, extensions, adjacent concepts." DO: Wait for outputs. Point at interesting additions.

**[16:30]** SAY: "Now clustering. They are grouping ideas into themes." DO: Point out the cluster names in each tool. "Notice the clusters are similar but not identical. Claude grouped these two together, ChatGPT kept them separate. Neither is wrong."

**[17:30]** SAY: "And now the converge phase. Each cluster gets scored on three things: impact, feasibility, and speed to value. One to ten scale."

**[18:00]** DO: Wait for scoring to finish. SAY: "Here are the top three from Claude..." (read them) "...and the top three from ChatGPT." (read them) "Two out of three are the same. The third is different. That is useful -- it gives you a fuller picture."

**[19:00]** SAY: "Go ahead and paste this into your tool now. Use prompt number two from the materials. You have about three minutes." DO: Walk the room. Help anyone stuck. Answer questions.

**[22:00]** SAY: "Alright, time's up. You should have your top three ideas. Let's put numbers on them."

---

## Fermi Estimation

**[22:00]** TRANSITION: "This is where it gets real. Brainstorming gives you ideas. Fermi estimation gives you numbers."

**[22:30]** SAY: "We are going to take the top two or three ideas and run them through a Fermi estimation skill. This breaks each idea down into: cost to implement, ticket deflection, annual savings, and time to first impact."

**[23:00]** DO: Paste prompt 03 into Claude Desktop with the top ideas from the converge step. SAY: "Watch the decomposition. It is not guessing a number -- it is building it up from components."

**[23:30]** DO: Point at the math on screen as it generates. SAY: "See this? It took '30 percent of tickets are onboarding questions' and multiplied that by handle time and agent cost to get an annual savings number. That is Fermi in action."

**[24:30]** SAY: "And here is the surprise." DO: Point to the biggest number. "This one idea -- [name the idea] -- could save roughly $127K a year and pay for itself in six weeks. That is not a guess. That is a structured estimate with assumptions you can challenge."

**[25:30]** SAY: "The Fermi card also shows a confidence level and the key assumption. If you disagree with the assumption, change it and re-run. That is the whole point."

**[26:00]** SAY: "Your turn. Paste prompt three with your top ideas. You have about three minutes." DO: Walk the room. Point out interesting numbers people are getting.

**[29:00]** SAY: "Raise your hand if your Fermi estimate surprised you." (pause) "Good. Surprises mean you learned something. That is the value."

---

## Build with Horizons

**[30:00]** TRANSITION: "Okay. We have scored ideas and real numbers. Now let's make it something you can share."

> **BACKUP NOTE:** If Horizons is slow or down, generate HTML locally with Claude ("Generate a single-page HTML dashboard with these data points") and screenshot it. The audience still gets the experience.

**[30:15]** DO: Switch to Hostinger Horizons in the browser. SAY: "This is Hostinger Horizons. It takes a prompt and builds a web page. We are going to use it to create a decision dashboard."

**[30:45]** DO: Paste a prompt that includes the top ideas, their Fermi estimates, and an instruction like "Build a decision dashboard comparing these options with a cost-vs-impact chart and a recommendation summary." SAY: "I am giving it our brainstorm winners and Fermi numbers. Let's see what it builds."

**[31:30]** DO: Wait for Horizons to render. SAY: "Look at that." DO: Walk through the output. "Comparison table. Cost-versus-impact chart. Recommendation summary. This took about 30 seconds."

**[33:00]** SAY: "This is something you can screenshot and drop into a Slack thread. Or share the link directly. Your boss does not need to know how you made it -- they just need to see the data."

**[34:00]** SAY: "Your turn. If you have a Hostinger Horizons account, paste your own data in. Free tier works fine. You have about four minutes." DO: Drop the Horizons URL in chat. Walk the room.

**[38:00]** SAY: "By the way -- if you want to go beyond a static dashboard and build a full interactive app from this data, check out Lovable. That is the next level." (One sentence. Move on.)

**[39:00]** SAY: "How are we doing? Anyone got a dashboard they are proud of?"

---

## Share-Out

**[40:00]** TRANSITION: "Alright, share-out time. I want to hear from two or three of you."

**[40:15]** SAY: "Give us three things: your top idea, the Fermi stat that surprised you most, and show us your dashboard if you have one. Sixty seconds each."

**[40:30]** DO: Call on the first volunteer. Listen. React. ("That savings number is wild. Your CFO would love that.")

**[41:30]** DO: Call on the second volunteer. Listen. React.

**[42:30]** DO: Call on the third volunteer if time allows. Listen. React.

**[43:30]** SAY: "You all just went from a messy transcript to a decision dashboard in 40 minutes. That usually takes a week of follow-up meetings and a spreadsheet nobody finishes."

---

## Close

**[44:00]** SAY: "Let's wrap up. Everything from today is available at:" DO: Show the final slide with links.

SAY:
- "All the prompts, guides, and the VTT file are at [ASSETS URL PLACEHOLDER]."
- "Hostinger Horizons is free to try -- build your next dashboard at horizons.hostinger.com. Huge thanks to Hostinger for sponsoring today."
- "The skills repo is at github.com/lyndonkl/claude. Install thinking-frameworks and you have these skills plus dozens more."

**[44:30]** SAY: "One takeaway. Skills are portable prompts. They are not locked to Claude or ChatGPT or any one tool. They are structured thinking you can carry anywhere. Go build something with them."

**[44:50]** SAY: "Thanks everyone. Go make your meetings worth having."

**[45:00]** END.
