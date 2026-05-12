# Speaker Outline — Prompting Techniques Workshop

**Total time:** ~47 min (45 + 2 added for concept slides) + 1–2 hr build time after
**Audience:** ~250, fresh TechTown crowd, building with Lovable
**Deck:** 28 slides total

---

## 0:00 — Title Slide

**Slide:** 1

**Say:** "Welcome. By the end of the next 45 minutes you'll have a prompt that's 4 layers better than the one you'd write today. And then you'll have time to actually use it in Lovable."

**Cue:** Advance after ~30 sec.

---

## 0:01 — Logistics

**Slide:** 2

**Say:** "Open ChatGPT or Claude.ai. Free is fine. Think of ONE project — the thing you'd build if Lovable just worked. No idea? Look for a red-shirt volunteer; they have starter cards. Or scan this QR."

**Cue:** Point to QR. Wait 30 sec for laptops to open.

**Say:** "If you fall behind at any point, just watch my screen. You'll still walk out with the prompt."

**Cue:** Advance.

---

## 0:03 — Mindset Shift

**Slide:** 3

**Say:** "Most people pray when they prompt. 'Build me Uber.' That's a wish. Today we're stacking. Each layer is something the AI can't guess about your business."

**Cue:** Advance to the conversation-roles slide.

---

## 0:04 — How AI conversations work (NEW)

**Slide:** 4

**Say:** "Quick mental model before we start. Every chat with an AI has three roles. SYSTEM is the hidden setup — Lovable manages that for you. USER is what you type — that's where everything we do today lives. ASSISTANT is what comes back. When I say 'stack layers' I mean: pack more useful context into your USER message."

**Cue:** Point to each of the 3 cards. Linger on USER. Advance.

**Volunteer cue:** No action needed.

---

## 0:05 — Context Window (NEW)

**Slide:** 5

**Say:** "Second mental model: AI has a memory limit. It's called the context window. Each chat can only hold so much in mind. Long chats — stuff at the top starts slipping away. That's why R-C-T-F works: it packs the critical context up front. That's also why iteration works — fresh chat, focused attention. Practical tip: when output gets weird, start a NEW chat with your V4 prompt."

**Cue:** Hold for 10 seconds. Then advance to Layer 1.

**Volunteer cue:** No action needed.

---

## 0:06 — Layer 1: Write Your V1

**Slide:** 6

**Say:** "No rules yet. Don't overthink it. Just write what you'd actually type if no one was watching."

**Cue:** Start 90-second timer visible to audience. Hold slide. Let them type.

**Volunteer cue:** Float quietly. Do not interrupt anyone mid-type. Note anyone who seems stuck — approach only if they look frozen after 60 seconds and offer a fallback project card.

---

## 0:09 — V1 Diagnosis

**Slide:** 7

**Say:** "Pencils down. Here's mine: 'build me a booking app for my salon.' I ran it. Got 800 lines of generic React. No business logic, no stylist names, nothing about how my salon actually works. Vague in, vague out."

**Cue:** Show the V1 output on screen — the wall-of-generic-React. Let it land for a beat before advancing.

**Volunteer cue:** No action needed. Return to neutral position near the walls.

---

## 0:11 — The 4 Missing Things

**Slide:** 8

**Say:** "Show of hands — your V1 about that level?" *[pause for hands]* "Yeah. So the AI isn't dumb. It just doesn't know anything about your business. We're about to fix that in 4 moves."

**Cue:** Poll the room. Let a few hands go up. Don't linger — acknowledge and advance.

**Volunteer cue:** Look around for hands. If the room is shy, raise your own hand as a prompt.

---

## 0:12 — Markdown Primer

**Slides:** 9–10

**Say:** "Quick detour. AI reads structure. If your prompt looks like a text message, you'll get a text message back. You need exactly four moves — I'll show you in 90 seconds."

**Cue:** Walk through each of the four elements on the slide: `#` for major sections, `-` for lists, `**bold**` for emphasis, backticks for exact text or code. Then flip to the before/after example.

**Say:** "Same content, two formats. Look at the difference in output. That's it — that's the whole trick. These four are all you need today. Don't overthink it."

**Cue:** Advance. 90 seconds total for this section — keep it tight.

**Volunteer cue:** No action needed.

---

## 0:15 — Layer 2: R-C-T-F Framework

**Slide:** 11

**Say:** "Now we have a framework. Role, Context, Task, Format. Each one is a markdown section. Role tells the AI who it is. Context gives it the business facts it can't guess. Task is the one thing you want done. Format is how you want it back."

**Cue:** Read the example prompt on screen as markdown sections — don't rush it. Audience should be reading along.

**Say:** "Four sections. That's your V2 structure. Watch me build it live."

**Cue:** Advance to demo.

**Volunteer cue:** No action yet.

---

## 0:17 — V2 Live Demo

**Slide:** 12

**Say:** "Okay, live. I'm pasting my salon V1 and rewriting it as R-C-T-F right now."

**Cue:** Switch to browser. Type or paste the R-C-T-F version of the salon prompt live. Run it. While it loads, narrate briefly — "Role: senior product engineer. Context: solo stylist, Asheville, paper appointment book." Show the result side-by-side with the V1 output.

**Say:** "See that? It's actually about a salon now. That's what context does."

**Cue:** Return to slides. Advance to audience prompt time.

**Volunteer cue:** Begin moving toward the edges of the room. You're about to be needed.

---

## 0:20 — Audience V2 Upgrade

**Slide:** 13

**Say:** "Your turn. Three minutes. Rewrite your V1 as R-C-T-F. If you freeze on Context, ask yourself: what would a new employee need to know on day one? Write that."

**Cue:** Start 3-minute timer. Circulate if possible, or stay at stage. Hold slide — don't advance until time is called.

**Volunteer cue:** Float actively. Prioritize anyone still on a blank screen. Coaching script for Context: "What would a new employee need to know on day one?" Don't write for them — ask the question and let them answer it.

---

## 0:23 — V2 Share-Back

**Slide:** 14

**Say:** "Pencils down. Show of hands — who's got something noticeably better than their V1?" *[pause]* "Good. We've got one coming up on screen."

**Cue:** Show-of-hands poll. Signal the volunteer who surfaced the best example. Display it on screen via the AV mechanism. Spend no more than 30 seconds on it — acknowledge it, name what's working, move on.

**Volunteer cue:** One designated volunteer should have a strong V2 example ready to surface to the AV station. Text/Slido/AirDrop — whatever the confirmed mechanism is. Send it during the final 60 seconds of audience prompt time, not after pencils down.

---

## 0:24 — Layer 3: Examples + Reasoning

**Slide:** 15

**Say:** "Layer 3 is two moves stacked. Few-Shot and Chain-of-Thought. Research shows few-shot examples improve accuracy 15 to 40 percent. That's a real number, not marketing. Examples teach the AI the shape of what you want. Step-by-step reasoning teaches it the process."

**Cue:** Advance to the next point on the slide after the few-shot stat lands.

**Say:** "Two new sections on top of your V2: `# Examples` with two or three references — 'something like Acuity booking' is fine — and `# Process` with 'think step-by-step before you write anything.' That's it."

**Cue:** Advance to V3 example slide.

**Volunteer cue:** No action needed. Reset position near the walls.

---

## 0:27 — V3 Example

**Slide:** 16

**Say:** "Here's what those two sections look like dropped into the salon prompt. `# Examples` — Acuity, Square Appointments. `# Process` — before you write anything, think through what could break in the booking flow."

**Cue:** Point to each section on screen. Let them read for 10 seconds. Then advance to the live demo or continue narrating — this beat can be tight since you just showed the framework. Run the V3 prompt live and call out one specific thing that improved because of the examples or the process step.

**Say:** "See how it's reasoning through the edge cases now? That's the Process section doing work."

**Cue:** Advance to audience prompt time.

**Volunteer cue:** Begin moving toward the edges of the room.

---

## 0:29 — Audience V3 Upgrade

**Slide:** 17

**Say:** "Three more minutes. Add `# Examples` and `# Process` to your V2. Your examples don't have to be perfect — 'something like Acuity booking' is enough. Just give it a reference point."

**Cue:** Start 3-minute timer. Hold slide.

**Volunteer cue:** Float actively. If someone is stuck on examples, prompt them: "What app does something close to what you want?" If they can't name one, suggest a category — booking app, CRM, marketplace. One volunteer should be scouting for a strong example to surface.

---

## 0:32 — V3 Share-Back

**Slide:** 18

**Say:** "Pencils down. Show of hands — even better than V2?" *[pause for hands]* "One more up on screen."

**Cue:** Show-of-hands poll. Display the volunteer-surfaced V3 example. Briefly name what the examples or process step added. Keep it under 45 seconds.

**Volunteer cue:** Same as V2 share-back — one volunteer surfaces the best example to AV during the final 60 seconds of audience prompt time. Flag it early.

---

## 0:33 — Why XML? (NEW)

**Slide:** 19

**Say:** "Before we wrap your prompt — why XML at all? Models are trained on a ton of tagged content. HTML, XML, all of it. When the AI sees `<role>` and `<context>`, those tags act as hard boundaries: 'this is the role, that's the context.' Claude in particular is tuned for it. ChatGPT and Gemini parse it fine too — no downside. And the tag names? They don't have to be magic. Use whatever's clear to you: `<my_business>`, `<the_thing>`, whatever."

**Cue:** Read the bullets at a steady pace. The "tag names don't have to be magic" point is the unlock — let it land before advancing.

**Volunteer cue:** No action needed.

---

## 0:34 — Layer 4: Wrap + Meta-Prompt

**Slide:** 20

**Say:** "Two moves stacked. First: wrap your V3 sections in tags. Second — and this one's my favorite — meta-prompt it. Paste your prompt into the AI and say 'What's missing? Rewrite this prompt to get a better result.' Then run THAT rewritten version. You don't have to be the best prompt writer in the room. You just have to ask the AI to be one."

**Cue:** Point to the two-column slide as you describe each move. Advance.

**Volunteer cue:** Get ready — this is the "whoa" moment; watch the room.

---

## 0:35 — Voice it. Then read it. (NEW)

**Slide:** 21

**Say:** "Quick aside — if typing isn't your thing, voice it. Open the voice mode in the ChatGPT or Claude app. Just talk out your messy thoughts — no structure needed. Then ask the AI: 'Turn what I just said into a R-C-T-F prompt with XML tags.' It will. And then — this is the actual skill — you READ what comes back. Edit it. Run it. Reading prompts is harder than writing them. The 4 layers we just learned? That's your reading checklist."

**Cue:** Hold the slide for ~30 seconds. The "reading > writing" insight is the takeaway here — don't rush. Then advance to the live demo.

**Volunteer cue:** No action needed.

---

## 0:36 — V4 Live Demo (The "Whoa" Moment)

**Slide:** 22

**Say:** "Live. I'm wrapping the V3 salon prompt in XML, then sending it to the AI and asking it to improve itself."

**Cue:** Switch to browser. Paste V3 with XML tags, then send the meta-prompt: "What's missing? Rewrite this prompt to get a better result." While it runs, narrate briefly — "It's reading the prompt right now. It's going to tell us what we missed." Display the AI-rewritten prompt. Then run THAT version and show the output side-by-side.

**Say:** "That's the one you paste into Lovable."

**Cue:** Let the room absorb it for 5–10 seconds before advancing. This is the moment — don't rush past it.

**Volunteer cue:** Watch the room. If you see people jaw-drop or laugh, that's the signal. You don't need to do anything — just be ready to help them replicate it in the next 3 minutes.

---

## 0:39 — Audience V4 Upgrade

**Slide:** 23

**Say:** "Your turn. Three minutes. Wrap your V3 in XML, then meta-prompt it. Or — if you'd rather — open voice mode and try it that way. Don't be precious about what comes back — let the AI rewrite your prompt. That's the move."

**Cue:** Start 3-minute timer. Hold slide.

**Volunteer cue:** Float actively. This is the hardest step — some people will freeze on the XML syntax. Coaching script: "Just wrap each section in a tag that matches the header name." Show them on their screen if needed. If someone wants to try voice, point them to the voice button in their app. One volunteer should be scouting for the best final example.

---

## 0:42 — Final Share-Back

**Slide:** 24

**Say:** "Pencils down. Final show of hands — who's got a prompt that's noticeably better than what they walked in with?" *[pause for hands]* "That's the glow-up. One more on screen."

**Cue:** Show-of-hands poll. Surface the best V4 example via AV. Spend 30 seconds max on it — name one specific thing that the XML or meta-prompt unlocked. Transition immediately.

**Volunteer cue:** Surface the best V4 example to the AV station. Have it ready before pencils-down is called.

---

## 0:43 — Cheat Sheet QR

**Slide:** 25

**Say:** "You just stacked 4 layers. Everything you need — all four layer templates, the interview rescue, what to do after V4 works — it's on the cheat sheet. Scan that QR right now if you haven't already. The URL's also at the bottom of every slide if you missed it."

**Cue:** Hold slide for 20 seconds. Let people scan. Then advance.

**Volunteer cue:** Walk the room. If anyone is struggling to scan, help them get the URL typed in manually.

---

## 0:44 — Interview Technique (5th Move)

**Slide:** 26

**Say:** "One more move. This one's for when you get stuck during build. Lovable's doing something weird, you don't know what to ask for next — flip to the interview technique. Paste this into the AI: 'I want to build X. Before we write anything, interview me about my project. Ask one question at a time.' It'll ask you the questions. You just answer. That's how you unblock."

**Cue:** 60 seconds total. Show the template on screen. Don't demo it live — that's build-time territory. Advance.

**Volunteer cue:** No action needed.

---

## 0:45 — Bridge to Build

**Slide:** 27

**Say:** "Here's your first move when build time starts: paste your V4 into Lovable. That's it. Don't start fresh. Don't rewrite. Paste the thing you just built. Then iterate. We're all here."

**Cue:** Advance to closing slide.

**Volunteer cue:** Begin transitioning mindset to floating tech support. Build time starts in under 2 minutes.

---

## 0:46 — Q&A / Closing Energy

**Slide:** 28

**Say:** "Any questions before we go?" *[take 1–2 questions max — if it's a build question, defer to build time]* "Alright. You've got V4, you've got the cheat sheet, you've got a room full of people to help you. Let's build."

**Cue:** Hold for applause. Transition directly into build time announcement. No lingering on stage — get moving.

**Volunteer cue:** Full transition to build support. Spread out across the room. Primary job is now: unblock Lovable questions, point to the cheat sheet, keep energy high.

---

## Recovery Moves

**Running 5 min behind:**
- Cut V3 audience prompt time to 2 min instead of 3
- Skip the volunteer-surfaced example on V3 layer
- Compress takeaway to 2 min
- Skip the "Voice it" beat at 0:35 (it's a nice-to-have)

**Running 5 min ahead:**
- Add live interview-technique demo at 0:42 (audience watches AI interview JD)
- Demo the voice-input flow live at 0:35
- Extend Q&A buffer

**Audience is lost / slow:**
- Skip V4 meta-prompt step, end at XML wrap
- Tell them: "The cheat sheet has V4. Get V3 solid for build time."
- Slide 5 (context window) can be cut if early beats are running long

**Tech failure mid-demo:**
- Use pre-prepared screenshots saved in `assets/` (capture day-of)
- Keep moving; the layer concept lands even without live AI response

---

## Volunteer Briefing (give this 15 min before start)

1. Hand out fallback project cards to anyone looking lost in first 60 sec
2. During each 3-min audience prompt time, float and unblock individuals
3. Watch for good examples on attendee screens
4. During "pencils down" transition, snap a photo of one good example with your phone
5. Send to AV station via [mechanism — Slido/AirDrop/doc cam — confirm before show day]
6. DO NOT use mics to ask audience to speak — visual surface only
7. During build time, transition to floating tech support
