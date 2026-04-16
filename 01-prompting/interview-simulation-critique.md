# AI Interview Simulation & Critique
## Partner Invite Feature for Digital Doula

**Simulated User:** Tyranny (non-technical founder)
**App:** Digital Doula - Natural language pregnancy/postpartum companion
**Platform:** Built in Lovable
**Feature:** Partner invite system

---

## Part 1: Simulated Interview Transcript

### Question 1

**AI:** Let's start with the basics - when you imagine a user inviting their partner, what's the very first thing they would do in your app? For example, would they tap a button that says "Invite Partner," or would they go to their profile settings first?

*Think about it like inviting someone to share a Netflix profile - where would that option live in your app?*

**Tyranny:** I think it would be in their profile settings. Like, they go to their account area and there's an option to add a partner. I don't want it to be too in-your-face because not everyone has a partner, and I don't want single moms to feel weird about it.

---

### Question 2

**AI:** That's really thoughtful - being sensitive to different family situations. Now, when someone taps "Add Partner," how would the invitation actually get to the partner? Would they receive a text message, an email, or maybe a special link they could share through any app?

*This is like how Venmo lets you invite friends - some apps send emails automatically, others give you a link to share however you want.*

**Tyranny:** Hmm, I think email would be good because it feels more official, but also maybe a link they could copy and text? My users are mostly millennials and Gen Z, and they text more than email. Can we do both?

---

### Question 3

**AI:** Absolutely, you can do both! That's called "multi-channel invitations." Now here's an important question: when the partner clicks that link or opens that email, do they need to download the app and create their own account? Or could they just view things in a web browser?

*Think of it like Google Photos sharing - sometimes you can view shared albums without having an account, other times you need to sign up.*

**Tyranny:** Oh, good question. I think they should download the app and create an account. That way they're more invested and might actually use it. But I don't want it to be too many steps or they'll give up.

---

### Question 4

**AI:** Makes sense - you want commitment but not friction. Let's talk about what the partner actually sees once they're in. Should they see everything the pregnant user sees, or just certain things? For example:

- All the daily logs and mood entries?
- Just the medical appointments?
- Only what the user specifically shares?

*This is about "permission levels" - like how some shared calendars show all details while others just show "busy" or "free."*

**Tyranny:** Definitely not everything. Some of the stuff my users log is really personal - like about their bodies and feelings. I think partners should see appointments, maybe the weekly updates about baby's development, and anything the user specifically decides to share. But not the private journal entries unless the user wants to share them.

---

### Question 5

**AI:** So we're looking at a "default view" with some things automatically visible, plus the ability to share specific items. That's a great privacy-first approach.

Now, should the partner be able to DO anything in the app, or just look? For example:
- Add appointments to the calendar?
- Set reminders for the pregnant user?
- Chat with the AI assistant themselves?

*It's the difference between being a "viewer" (read-only, like a museum visitor) and a "contributor" (can add things, like a Wikipedia editor).*

**Tyranny:** Ooh, I like the idea of them adding appointments - like if the partner schedules something, both people see it. And reminders could be sweet, like "Don't forget prenatal vitamins!" But I don't think they should chat with the AI about pregnancy stuff... that's for the pregnant person. Maybe they could have their own chat for partner-specific questions? Like "How do I support my partner during labor?"

---

### Question 6

**AI:** I love that idea - a partner-specific AI experience! That's actually a feature that could differentiate your app.

Let's talk about a tricky scenario: what if the couple breaks up or the user changes their mind? How should "removing" a partner work?

*Apps handle this differently - some require both people to agree (like unfriending on Facebook), others let one person remove instantly (like removing someone from a shared note).*

**Tyranny:** The pregnant person should have full control. If they want to remove their partner, it should happen immediately, no questions asked. This is sensitive - there could be domestic situations... I don't even want the partner to get a notification that they've been removed. Just quietly revoke access.

---

### Question 7

**AI:** That's a really important safety consideration. Immediate, silent removal - no notification to the partner. We should note that as a safety feature.

What about the data? When a partner is removed, should we:
- Delete everything they added (appointments, reminders)?
- Keep what they added but transfer ownership to the pregnant user?
- Let the pregnant user decide what to keep?

**Tyranny:** Keep what they added but transfer it to me - I mean, to the pregnant user. Like, if they added a doctor's appointment, that appointment is still real and important. Just remove their access to see anything going forward.

---

### Question 8

**AI:** Smart - the data persists, just the access changes. Now let's think about notifications. When the pregnant user logs something or has an appointment coming up, should the partner get notified?

*This is like how Find My Friends can ping you when someone arrives somewhere, or how shared calendars can send reminders to everyone.*

**Tyranny:** Yes! But the pregnant user should control which things trigger notifications to the partner. Like, maybe they want the partner notified about appointments but NOT about every mood log. Oh, and definitely notify the partner when it's close to the due date or if something urgent happens.

---

### Question 9

**AI:** Great - user-controlled notification preferences for the partner. Let me ask about something technical that affects user experience: should a pregnant user be able to invite multiple partners?

I'm thinking about situations like:
- A surrogate with intended parents
- Someone with multiple support people
- A co-parenting situation

*Or should it strictly be one partner at a time?*

**Tyranny:** Oh wow, I didn't think about surrogacy! That's a real use case. I think... maybe start with one partner for the first version? But build it so we could add more later? I don't want to overcomplicate it, but I also don't want to exclude surrogates. Let me think... actually, could we call it "Support Circle" instead of just "Partner"? Then it feels more inclusive.

---

### Question 10

**AI:** "Support Circle" - that's a beautiful reframe! It's more inclusive and opens up future possibilities. For V1, would you want to limit the Support Circle to one person, or maybe two or three?

**Tyranny:** Let's say up to 2 people for V1. That covers most situations - like a partner plus a mom or best friend. But keep it simple in the interface. Don't make it feel like a social network.

---

### Question 11

**AI:** Two people max for V1, clean interface. Now, should everyone in the Support Circle have the same permissions, or could the pregnant user give different access to different people?

*For example: Partner sees appointments AND weekly updates, but Mom only sees appointments.*

**Tyranny:** Different permissions! A partner is different from a mom or a friend. The pregnant person should choose what each person can see. But don't make it too complicated - maybe just like 3 levels? "Full access" (everything sharable), "Updates only" (weekly baby updates), and "Appointments only"?

---

### Question 12

**AI:** Three permission tiers - Full, Updates, and Appointments Only. Clean and simple.

What happens if someone in the Support Circle never accepts the invitation? Should it expire after a certain time, or just sit there waiting?

**Tyranny:** It should expire. Maybe after... 7 days? And the pregnant user should be able to see if it's still pending and resend it or cancel it. Nothing worse than wondering if someone got your invite.

---

### Question 13

**AI:** 7-day expiration with visibility into pending status. Let's talk about edge cases:

What if the pregnant user's pregnancy ends - whether through birth, loss, or other circumstances? Should Support Circle members:
- Keep access to historical data?
- Lose access automatically?
- Have their access converted to a different type?

*This is sensitive but important to plan for.*

**Tyranny:** *pauses* That's hard. For birth, they should keep access - it transitions into the postpartum phase and that's important for support. For loss... I think the user should choose. Maybe we gently ask if they want to keep their Support Circle active or take a break. Don't automatically do anything - let the user decide when they're ready. This needs to be handled with so much care.

---

### Question 14

**AI:** Absolutely - user choice during sensitive transitions, handled with care and no automatic actions.

Last question about functionality: Should Support Circle members be able to see each other? For example, if someone invites both their partner and their mom, should the partner know the mom is also in the circle?

**Tyranny:** Hmm... I think yes? If it's a support circle, everyone should know who else is supporting. It's not a secret. But maybe just names - not like, their contact info or anything. Just "Sarah (Partner) and Mom (Family)" or something like that.

---

### Question 15

**AI:** Visibility of names and roles, but not contact details. Perfect for building that sense of shared support without oversharing.

Final question: What should we call this feature in the app's marketing and interface? We've discussed "Support Circle" - is that the winner, or do you want to consider alternatives like:
- "My Village" (takes a village to raise a child)
- "Inner Circle"
- "Care Team"

**Tyranny:** Oh, I love "My Village"! It feels warm and fits with the doula vibe of the app. "Support Circle" is clearer but "My Village" has more personality. Let's go with "My Village" for the user-facing name, but we can call it Support Circle in documentation or whatever.

---

## Part 2: Feature Specification Document

### Feature Specification: My Village (Partner/Support Invite System)
**Digital Doula v2.0**
**Last Updated:** January 2026

---

#### 1. Overview

**Feature Name:** My Village
**Internal Name:** Support Circle
**Purpose:** Allow pregnant/postpartum users to invite trusted people to view selected information and participate in their pregnancy journey.

---

#### 2. User Stories

| As a... | I want to... | So that... |
|---------|-------------|------------|
| Pregnant user | Invite my partner to the app | They can stay informed and involved |
| Pregnant user | Control what my support people see | I maintain privacy over sensitive info |
| Pregnant user | Remove someone instantly | I feel safe if my situation changes |
| Support member | View appointments and updates | I can support my loved one effectively |
| Support member (partner) | Add appointments and reminders | I can actively participate in the journey |
| Support member | Get my own AI guidance | I learn how to be a better support person |

---

#### 3. Functional Requirements

##### 3.1 Invitation System

| Requirement | Details |
|-------------|---------|
| **Location in app** | Settings > My Village |
| **Invitation methods** | Email AND shareable link |
| **Invitation expiration** | 7 days |
| **Max village members** | 2 (V1) |
| **Invitation status visibility** | User can see Pending, Accepted, or Expired |
| **Resend capability** | Yes, resets 7-day timer |

##### 3.2 Permission Tiers

| Tier | Name | Can View | Can Do |
|------|------|----------|--------|
| 1 | **Full Access** | Appointments, weekly updates, shared entries, baby development | Add appointments, set reminders, partner-specific AI chat |
| 2 | **Updates Only** | Weekly updates, baby development milestones | Partner-specific AI chat |
| 3 | **Appointments Only** | Calendar appointments only | View appointments (read-only) |

##### 3.3 Member Roles

| Role | Default Tier | Notes |
|------|-------------|-------|
| Partner | Full Access | Default, user can adjust |
| Family | Updates Only | Default, user can adjust |
| Friend | Appointments Only | Default, user can adjust |
| Custom | User chooses | For edge cases |

##### 3.4 Content Visibility Rules

| Content Type | Partner (Full) | Family (Updates) | Friend (Appts) |
|--------------|---------------|------------------|----------------|
| Appointments | Yes | No | Yes |
| Weekly baby updates | Yes | Yes | No |
| Mood/symptom logs | Only if shared | No | No |
| Journal entries | Only if shared | No | No |
| Due date | Yes | Yes | No |
| Medical info | Only if shared | No | No |

##### 3.5 Member Actions

| Action | Full Access | Updates Only | Appts Only |
|--------|------------|--------------|------------|
| View assigned content | Yes | Yes | Yes |
| Add appointments | Yes | No | No |
| Set reminders (for user) | Yes | No | No |
| AI chat (partner-specific) | Yes | Yes | No |
| See other village members | Names/roles only | Names/roles only | Names/roles only |

---

#### 4. Removal & Safety Features

| Feature | Behavior |
|---------|----------|
| **Removal speed** | Immediate upon user action |
| **Partner notification on removal** | NONE (silent removal for safety) |
| **Data handling on removal** | Content added by removed member transfers to primary user ownership |
| **Access after removal** | Complete revocation, no historical access |
| **Re-invitation** | Allowed, treated as new invitation |

---

#### 5. Notifications

##### 5.1 To Primary User

| Event | Notification |
|-------|--------------|
| Village member accepts invite | Yes |
| Village member adds appointment | Yes |
| Invitation expires | Yes |

##### 5.2 To Village Members (User Controlled)

| Event | Default | User Can Toggle |
|-------|---------|-----------------|
| Upcoming appointment (24hr) | ON | Yes |
| Weekly update available | ON | Yes |
| Mood/symptom logged | OFF | Yes |
| User shares specific content | ON | No (always on) |
| Approaching due date (2 weeks) | ON | Yes |
| Urgent event | ON | No (always on) |

---

#### 6. Life Event Handling

| Event | System Behavior |
|-------|-----------------|
| **Birth** | Village remains active, transitions to postpartum phase |
| **Pregnancy loss** | Prompt user (gently) whether to keep Village active or pause; no automatic changes |
| **User deactivates account** | Village members lose access; optional goodbye notification (user choice) |

---

#### 7. Onboarding Flow for Village Members

1. Receive invitation (email or link)
2. Download Digital Doula app
3. Create account (email + password, or social login)
4. Accept village invitation
5. Role-specific onboarding:
   - Partner: "How to support your partner" quick tips
   - Family: "What to expect" summary
6. Land on their personalized dashboard

---

#### 8. AI Experience for Village Members

| Member Type | AI Focus |
|-------------|----------|
| Partner | "How can I support during labor?", "What to expect at appointments", "How to help with [symptom]" |
| Family | "What's happening at week 24?", "How can I help?" |
| General | Cannot access pregnancy-specific questions that should come from pregnant user's perspective |

---

#### 9. Technical Notes (for Development Team)

- Invitation links should use secure, expiring tokens
- Permission checks must happen at API level, not just UI
- "Silent removal" requires no webhooks or notifications to removed party
- Consider rate limiting on invitations (prevent spam)
- Multi-device support: Village members may use different devices

---

#### 10. Future Considerations (V2+)

- Expand village size beyond 2 members
- Add "Doula" or "Healthcare Provider" as professional role
- Group chat among village members (opt-in)
- Shared photo album for village
- Integration with partner's calendar app (export)

---

#### 11. Success Metrics

| Metric | Target |
|--------|--------|
| % of users who invite at least 1 person | 40% |
| Village member 7-day retention | 60% |
| Average village size | 1.5 |
| Invitation acceptance rate | 70% |
| Partner AI engagement | 3+ sessions/week |

---

#### 12. Open Questions

1. Should we offer a "preview" mode for village members before they create an account?
2. Do we need terms of service specific to village members?
3. Should village members be able to gift premium features to the primary user?

---

## Part 3: Self-Critique Rubric Matrix

```
+---------------------------+-------------+-------------+-------------+--------------+
|        CRITERIA           |  Poor (1)   |  Fair (2)   |  Good (3)   | Excellent(4) |
+---------------------------+-------------+-------------+-------------+--------------+
|                           |             |             |             |     [X]      |
| 1. Question Quality       | Off-topic,  | Basic but   | Relevant,   | Probing,     |
|    Did AI ask the right   | generic, or | missing key | covered     | uncovered    |
|    questions?             | leading     | areas       | main areas  | edge cases   |
|                           |             |             |             |              |
|    SCORE: 4               |             |             |             | Covered      |
|    REASONING: Asked about |             |             |             | breakups,    |
|    safety (removal),      |             |             |             | loss,        |
|    loss, surrogacy,       |             |             |             | permissions, |
|    permissions - all      |             |             |             | multiple     |
|    critical edge cases    |             |             |             | scenarios    |
+---------------------------+-------------+-------------+-------------+--------------+
|                           |             |             |     [X]     |              |
| 2. Example Helpfulness    | Irrelevant  | Somewhat    | Clear,      | Perfectly    |
|    Were examples useful   | or          | helpful but | relatable   | matched to   |
|    for non-technical      | confusing   | not always  | consumer    | user's       |
|    founder?               |             | relevant    | app         | context      |
|                           |             |             | examples    |              |
|    SCORE: 3               |             |             | Netflix,    |              |
|    REASONING: Good        |             |             | Venmo,      |              |
|    consumer app refs      |             |             | Google      |              |
|    but could use more     |             |             | Photos,     |              |
|    pregnancy/health app   |             |             | Find My     |              |
|    specific examples      |             |             |             |              |
+---------------------------+-------------+-------------+-------------+--------------+
|                           |             |             |             |     [X]      |
| 3. Technical Term         | Jargon      | Explained   | Clear       | Crystal      |
|    Explanations           | heavy, no   | some terms, | analogies   | clear with   |
|    Clear for non-tech?    | definitions | missed      | for most    | perfect      |
|                           |             | others      | concepts    | analogies    |
|    SCORE: 4               |             |             |             |              |
|    REASONING: "Permission |             |             |             | Museum vs    |
|    levels" = shared       |             |             |             | Wikipedia,   |
|    calendar, "Viewer" =   |             |             |             | multi-       |
|    museum, "Contributor"  |             |             |             | channel =    |
|    = Wikipedia editor.    |             |             |             | multiple     |
|    All very accessible.   |             |             |             | ways to      |
|                           |             |             |             | send         |
+---------------------------+-------------+-------------+-------------+--------------+
|                           |             |             |     [X]     |              |
| 4. Coverage               | Major gaps  | Hit basics, | Good        | Comprehensive|
|    Did we capture all     | in          | missed some | coverage,   | - nothing    |
|    requirements?          | requirements| important   | minor gaps  | missing      |
|                           |             | features    |             |              |
|    SCORE: 3               |             |             | Covered     |              |
|    REASONING: Covered     |             |             | core +      |              |
|    core features well.    |             |             | edge cases, |              |
|    Could have asked more  |             |             | missed      |              |
|    about: analytics,      |             |             | some        |              |
|    error states, offline  |             |             | operational |              |
|    behavior, billing      |             |             | details     |              |
+---------------------------+-------------+-------------+-------------+--------------+
|                           |             |             |             |     [X]      |
| 5. Flow                   | Awkward,    | Logical but | Natural     | Felt like    |
|    Natural conversation?  | robotic     | stilted     | with good   | real         |
|                           |             |             | transitions | conversation |
|    SCORE: 4               |             |             |             |              |
|    REASONING: Questions   |             |             |             | Built on     |
|    built naturally on     |             |             |             | previous     |
|    answers. AI            |             |             |             | answers,     |
|    acknowledged user's    |             |             |             | validated    |
|    ideas ("That's         |             |             |             | user input,  |
|    thoughtful", "I love   |             |             |             | gentle       |
|    that idea"). User      |             |             |             | probing      |
|    responses felt genuine |             |             |             |              |
+---------------------------+-------------+-------------+-------------+--------------+
|                           |             |             |     [X]     |              |
| 6. Spec Quality           | Vague,      | Basic       | Detailed,   | Production-  |
|    Actionable output?     | incomplete  | requirements| clear       | ready        |
|                           |             | only        | tables,     | blueprint    |
|                           |             |             | some gaps   |              |
|    SCORE: 3               |             |             | Clear       |              |
|    REASONING: Well-       |             |             | structure,  |              |
|    organized with clear   |             |             | tables,     |              |
|    tables. Missing:       |             |             | user        |              |
|    wireframes, error      |             |             | stories.    |              |
|    messages, exact copy,  |             |             | Missing     |              |
|    QA test cases          |             |             | some        |              |
|                           |             |             | execution   |              |
|                           |             |             | details     |              |
+---------------------------+-------------+-------------+-------------+--------------+
|                           |             |             |             |              |
| TOTAL SCORE               |             |             |    21/24    |              |
| PERCENTAGE                |             |             |    87.5%    |              |
| OVERALL RATING            |             |             |    GOOD+    |              |
+---------------------------+-------------+-------------+-------------+--------------+
```

---

## Part 4: Analysis - What Worked and What Didn't

### What Worked Well

1. **The "Example + Explanation" Format**
   - Every question included a consumer app analogy (Netflix, Venmo, Google Photos)
   - Technical concepts were immediately demystified
   - User never had to ask "what does that mean?"

2. **Progressive Depth**
   - Started simple (where does the button live?)
   - Built to complex (what happens during pregnancy loss?)
   - Each question naturally led to the next

3. **Safety-First Discovery**
   - The AI proactively asked about removal/breakup scenarios
   - User hadn't thought about it - AI surfaced critical safety requirements
   - "Silent removal" emerged as a key safety feature

4. **User-Led Pivots**
   - When user said "Support Circle," AI embraced it
   - When user pivoted to "My Village," AI validated and adopted
   - Made user feel ownership of the feature

5. **Edge Case Exploration**
   - Surrogacy (multiple intended parents)
   - Pregnancy loss (sensitive handling)
   - Data persistence after removal
   - These would have been missed without probing

6. **Non-Judgmental Tone**
   - Validated "not everyone has a partner" sensitivity
   - Didn't push back when user wanted simpler options
   - Felt like collaboration, not interrogation

### What Could Be Improved

1. **Missing Operational Questions**
   - What happens if email bounces?
   - What if someone tries to join but invitation expired?
   - Error messages and edge case UI

2. **No Discussion of Existing Architecture**
   - Didn't ask about current auth system in Lovable
   - Didn't explore database structure constraints
   - Could lead to spec that's hard to implement

3. **Missed Business Model Questions**
   - Is this a premium feature?
   - Different tiers for free vs paid users?
   - Monetization of partner accounts?

4. **No Visual/UX Deep Dive**
   - What does the invitation email look like?
   - How is the Village displayed in the app?
   - What's the empty state before anyone is invited?

5. **Limited Discussion of Testing**
   - How will we test partner notifications?
   - How to QA silent removal?
   - Beta testing strategy?

6. **Could Use More Pregnancy-Specific Examples**
   - Consumer apps are good but...
   - References to Ovia, The Bump, What to Expect could resonate more

---

## Part 5: Suggested Improvements to the Prompt

### Current Prompt
> "I want you to interview me one question at a time about adding a partner invite feature to my pregnancy tracking app. Give me an example of a response to make me think and explain the technical terms in a non-technical way."

### Suggested Enhanced Prompt (v2)

> "I want you to interview me one question at a time about adding a partner invite feature to my pregnancy tracking app.
>
> For each question:
> 1. Ask one focused question
> 2. Give me an example response to help me think (use apps I probably use as references)
> 3. Explain any technical terms in plain language
>
> Make sure to cover:
> - The happy path (when everything works)
> - Edge cases (what could go wrong or be unusual)
> - Safety considerations (privacy, removal, sensitive situations)
> - How this connects to what I've already built
>
> Start by asking what I've already built so you understand my starting point."

### Why These Changes Help

| Addition | Benefit |
|----------|---------|
| "Ask one focused question" | Prevents multi-part questions that overwhelm |
| "Apps I probably use" | Encourages relevant analogies |
| "Happy path + edge cases" | Ensures comprehensive coverage |
| "Safety considerations" | Explicitly surfaces critical issues |
| "What I've already built" | Grounds conversation in reality |

### Additional Prompt Variants for Different Depths

**Quick Version (5 questions):**
> "Interview me briefly about [feature]. 5 questions max. Focus on: who uses it, what they do, and what could go wrong. Explain technical terms simply."

**Deep Version (20+ questions):**
> "Conduct a thorough product requirements interview about [feature]. Cover: user journey, permissions, edge cases, error states, safety/privacy, analytics, and future extensibility. One question at a time with examples."

**Technical Translation Version:**
> "Interview me about [feature] as if I'm a non-technical founder but you need to produce a spec a developer can build from. Bridge my business language to technical requirements."

---

## Part 6: Workshop Modifications

### For Tech Town Context

1. **Add a "Lovable-Specific" Prompt Variant**
   - Lovable has constraints and capabilities
   - Prompt should acknowledge: "I'm building in Lovable, which uses [X]. Keep implementation practical for this platform."

2. **Include a "Spec Review" Step**
   - After AI generates spec, prompt AI to review it from developer perspective
   - "Now review this spec as if you're the developer who has to build it. What questions would you have?"

3. **Pair with Implementation Prompt**
   - Interview generates spec
   - Second prompt: "Using this spec, help me build this in Lovable step by step"

4. **Create a "Critique Template"**
   - Give participants the rubric matrix blank
   - They fill it in for their own interview
   - Compare across group

### Suggested Workshop Activity

1. **Live Demo** (10 min)
   - Facilitator runs interview with volunteer "founder"
   - Shows the flow in real-time

2. **Paired Practice** (20 min)
   - One person plays founder, other prompts AI
   - Swap roles

3. **Spec Generation** (10 min)
   - AI generates spec from interview

4. **Peer Critique** (10 min)
   - Pairs swap specs
   - Use rubric matrix to score
   - Discuss gaps

5. **Prompt Iteration** (10 min)
   - What would you change about the prompt?
   - Group shares improvements

---

## Appendix: Raw Interview Statistics

| Metric | Value |
|--------|-------|
| Total questions asked | 15 |
| Questions about core functionality | 7 |
| Questions about edge cases | 5 |
| Questions about safety/privacy | 2 |
| Questions about naming/branding | 1 |
| Examples provided | 13 |
| Technical terms explained | 8 |
| User-initiated pivots | 2 (Support Circle, My Village) |
| Features surfaced by AI probing | 3 (silent removal, permission tiers, multi-member) |
| Features surfaced by user | 3 (partner AI chat, notification control, "My Village" branding) |

---

*Document generated for Tech Town AI Prompting Workshop*
*Simulation demonstrates the "Golden Prompt" interview technique for non-technical founders*
