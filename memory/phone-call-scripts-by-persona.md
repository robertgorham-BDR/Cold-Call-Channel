# Phone Call Scripts by Persona
## Opening lines, voicemail, and objection responses for cold calling
## Last updated: April 10, 2026

> **Sequences that use phone:** Factor-First Outbound (Step 1 automated reminder ~30 min after email), G2 Intent (Step 1 automated reminder ~30 min)
> **Context:** These are Testsigma's phone call scripts — PERSONALIZE before use. Not a word-for-word read. Rob's voice and natural delivery matter more than script adherence.

---

## Before Any Call

**Prep checklist:**
1. Open contact's LinkedIn profile in Sales Nav (Rob's work Chrome)
2. Skim: headline, recent role changes, company news, mutual connections
3. Review: last email sent (T1), when they received it, subject line
4. Check: any prior call notes in `memory/call-log.md`
5. Have a calendar link ready for booking time
6. Test your audio (you're calling on behalf of Testsigma)

**Opening context:** "Hi [Name], this is Rob Gorham from Testsigma. I sent you an email about [30 minutes/earlier today]. Do you have 30 seconds?"

---

## Persona Scripts

### QA Manager / QA Lead (Primary — High-volume persona)

#### Cold Call Opener (15–20 seconds)
```
"Hi [Name], it's Rob from Testsigma. I know email is a lot,  so I'm calling because 
I think there might be a quick fit here. We work with companies like Hansard—they cut 
their regression testing from 8 weeks down to 5. And we found that QA Managers in your 
vertical deal with the same bottleneck.

Does that sound like something you're dealing with?"

[PAUSE for response. If YES → continue below. If NO → brief objection handling, then close.]
```

**If they say YES or "maybe":**
```
"Great. Just one quick question: when you run regression testing, what's taking the 
longest—creating the tests, running them, or fixing the flaky ones?

[LISTEN. Lock in on their top pain.]

That's exactly what we've built for. Would it make sense to spend 20 minutes looking 
at how companies like yours have handled that?"

[Close to calendar.]
```

#### Voicemail Script (20–25 seconds)
```
"Hi [Name], this is Rob Gorham from Testsigma. I sent an email your way earlier about 
test automation. I know you're busy, so I'll keep this quick. 

We just helped Hansard cut their regression testing from 8 weeks down to 5 using AI 
self-healing on flaky tests. If that's a problem you're seeing too, I'd love to show you 
a 20-minute look at how we do it.

Feel free to call back or just reply to my email. 

[SLOW DOWN SLIGHTLY]

That's R-O-B, at Testsigma. Thanks."
```

#### Common Objections (with responses)

| Objection | Your Response | Next Step |
|-----------|---|---|
| "We're happy with our current tool" | "Totally fair. A lot of teams we work with felt the same way until they saw what AI self-healing could do for their flaky tests. It's a pretty specific capability. Just worth a quick look?" | Re-frame, then calendar |
| "We don't have budget right now" | "I get it. What we usually find is teams like yours save money on maintenance costs. Even if it's not this quarter, would it make sense to see what you'd be looking at?" | Soft close, re-engage window |
| "We're using [Provar/Cypress/Playwright]" | "[Tool] is solid, and we see teams run us alongside it all the time. The thing it doesn't do is auto-heal flaky tests when the UI changes. That's where we're different. Worth 20 minutes to see?" | Competitive angle |
| "I'm not the right person, talk to [other title]" | "Totally get it. And I'll definitely connect with [name] too. Usually it helps if you give them a heads up that I'm reaching out. Should I still grab time with you, or would [name] be better?" | Confirm routing |

---

### Director / VP of QA (Upmarket — More reserved, asks harder questions)

#### Cold Call Opener (25–30 seconds)
```
"Hi [Name], this is Rob Gorham from Testsigma. I know you're probably in meetings, 
so I'll be direct.

I'm calling some of the larger QA organizations because we're seeing a pattern: 
regression testing is becoming a bottleneck even as you scale your teams. Hansard 
solved it by switching from manual healing to AI-powered self-healing.

I thought that might be relevant to what you're building. Does that sound fair?"

[PAUSE. They'll either say yes or ask a clarifying question. Answer directly.]
```

**If they engage:**
```
"What I'd suggest is a 20-minute call where I show you exactly what self-healing looks 
like for a team your size—what changes, what doesn't, and how fast you'd see the value.

Are you open to that in the next few days?"

[Calendar.]
```

#### Voicemail Script (25–30 seconds)
```
"Hi [Name], this is Rob Gorham from Testsigma. I'm reaching out because we're seeing 
a trend with QA leaders at your level: regression testing maintenance is eating 
bandwidth that should go to new coverage.

We helped Cisco cut their regression workload, and I think the approach might apply 
to your org. 

If it's interesting, let's grab 20 minutes. If not, totally understand.

That's Rob at Testsigma. Thanks."
```

#### Common Objections

| Objection | Your Response |
|-----------|---|
| "Send me some info and I'll review" | "Happy to. But honestly, the value is in seeing it live. How about I send the overview and you grab 15 minutes on my calendar—that way you can ask questions as you're reading?" |
| "We're in the middle of [initiative]" | "Totally get it. When's a better window—end of Q2?" [Note re-engage date in `memory/warm-leads.md`] |
| "We already looked at you guys" | "When was that? The product's evolved quite a bit, especially on self-healing. Worth a refresh call?" |
| "I need to see ROI numbers first" | "Absolutely. For a team your size, self-healing usually means [X% time savings on flaky test fixes]. I can run the math for your scenario in the first 10 minutes of our call. Does that work?" |

---

### Senior SDET / Automation Lead (Technical buyer — Wants deep product details)

#### Cold Call Opener (20–25 seconds)
```
"Hi [Name], this is Rob. I saw your background in test automation, and I wanted to 
reach out directly.

We built something pretty different—it's AI-powered test healing that actually reduces 
flaky test maintenance without rewrites. I know that's a problem you're solving right now.

Got a quick second?"

[If yes, continue. If no, ask for better time.]
```

**If they engage:**
```
"Here's what makes it different from Selenium or Cypress: when the DOM changes, it 
auto-remaps the locators. No breaking tests, no rewrites.

I'd love to show you the actual mechanism—like, how the XPath remapping works—because 
I think you'll have a lot of questions. Would 20 minutes make sense?"

[Calendar.]
```

#### Voicemail Script (20–25 seconds)
```
"Hi [Name], this is Rob Gorham from Testsigma. I'm reaching out because you've built 
some impressive test automation, and we're solving a specific problem you probably see 
every day: brittle tests that break when the DOM changes.

We do this with AI-powered self-healing—basically, intelligent XPath remapping. I think 
you'd have some good questions about how we do it.

Let's grab 20 minutes. That's Rob at Testsigma. Thanks."
```

#### Common Objections

| Objection | Your Response |
|-----------|---|
| "Sounds like magic—how does it actually work?" | "Fair question. It's not magic, it's deterministic: we collect XPath + ID pairs, build a recovery map, and when a selector fails, we check the map. Want to see the actual code structure?" |
| "We built our own in-house solution" | "That's smart. Most teams do. Two questions: how often does it catch cases your solution misses, and is maintaining it part of your job?" [Listen. If in-house solution is mature, they're not a fit.] |
| "Playwright handles this pretty well" | "Playwright's good at the framework level. Where we differ is cross-browser + mobile + Salesforce shadow DOM—Playwright struggles with those. If you're only doing Chrome, fair point." |

---

### VP Engineering / CTO (Only with Intent Signal — Strategic buyer)

#### Cold Call Opener (30–35 seconds)
```
"Hi [Name], this is Rob from Testsigma. I know this is unusual, so I'll be direct.

I'm calling because your company is scaling, and we're seeing a pattern: automation is 
becoming a bottleneck in your CI/CD. A lot of CTOs at your level are solving that with 
AI-powered test automation.

I thought it might be worth a brief conversation."

[Pause. They'll be interested or not. If interested, continue.]
```

**If they engage:**
```
"What I'd suggest is a strategic call—30 minutes—where I show you how teams like 
yours are un-blocking their CI/CD with automation that actually scales. 

Are you open to that?"

[Calendar — note: CTOs usually want to see competitive landscape and integration with their stack.]
```

#### Voicemail Script (Very rare — CTOs usually don't pick up)
```
"Hi [Name], this is Rob Gorham from Testsigma. I know you're managing a ton, so I'll 
be brief.

We help engineering teams un-block CI/CD with AI automation. I think there might be 
strategic fit with what you're building, but I'd rather not take your time if there's 
not interest.

If it makes sense, let's grab 30 minutes. That's Rob at Testsigma. Thanks."
```

---

## Post-Call Notes

**Always log the call in `memory/call-log.md` with:**
- Contact name + company
- Date/time of call
- Duration
- Key topics discussed
- Their stated pain/interest
- Next step (follow-up email, demo, re-engage date)
- Any objections mentioned
- Your assessment (P0/P1/P2/P3/P4)

**Example:**
```
**Apr 10, 2026** — Jane Doe, Acme Corp
- Duration: 7 minutes
- Topics: Regression testing bottleneck, current tool (Cypress), team size (8 QAs)
- Pain: Flaky tests eating 40% of time
- Interest: Moderate (P1) — asked to see demo
- Next: Schedule demo for Apr 17
- Notes: Mentioned budget cycle in Q2, not now. Follow up with value prop.
```

---

## Version History
- **Apr 10, 2026:** Created (extracted from call-prep-card skill + prior session notes)
- **Last validated:** Apr 10, 2026 (personas and objection responses aligned with current market)