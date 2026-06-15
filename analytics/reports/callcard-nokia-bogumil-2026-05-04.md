# Nokia Call Card — Bogumil + Faiz, 9:30–9:45 AM EDT

**Posture:** existing-customer renewal in flight. Discovery only. No pricing, no trial promises, no other-Nokia-contact name-drops.

**Goal of the call:** answer 4 questions — who is Faiz, what's the trial for, web or network scope, and what's the right next step.

---

## Pre-call (next 5 min, if you have time)

1. Slack Mithun + Tyler: *"Quick — who owns the Nokia renewal? 9:30 call with a Nuremberg system-verification engineer who signed up for a trial. Anything I should know?"*
2. Open the brief in a side window: `analytics/reports/callprep-nokia-bogumil-2026-05-04.md`
3. Have the trial-signup HubSpot record open if you can find it
4. Pull up your "Atto + self-healing" 30-second story so you can deliver it cleanly if asked

---

## Action plan — minute by minute

| Time | What you're doing | Why |
|------|------------------|-----|
| 0:00–0:30 | Quick intro, name only. "Rob, BDR @ Testsigma. Will may join. Want this to be useful to you, so let me start with a couple of quick questions." | Set tone, don't pitch first. |
| 0:30–2:00 | **Q1 + Q2** — frame role + trigger | Closes the two biggest gaps. |
| 2:00–6:00 | **Q3 + Q4 + Q5** — use case, scope, stack | Determines if you have product-fit. |
| 6:00–9:00 | **Q6 + Q7** — pain + process. React to what you've heard. | Decide pivot path. |
| 9:00–11:00 | Brief positioning if (and only if) it fits. 60-90 sec max. | Earn next step. |
| 11:00–13:00 | **Q8 + Q9** — qualify, decide route | Get the next-step commitment. |
| 13:00–15:00 | Confirm next step + recap. "I'll send a short note today with what we agreed." | Close clean. |

---

## Discovery questions — priority order

Ask in this order. Stop pushing if you've got a clear signal; don't force every question.

### Tier 1 — must ask in the first 3 minutes

1. **"Faiz, before we dig in — mind sharing what your role is and how you and Bogumil work together?"**
   *Closes the biggest gap. `.ext` suggests contractor; you need to know.*

2. **"Bogumil, what made you reach out — what are you trying to figure out from this call?"**
   *Single best discovery question. Don't lead them. Listen for: "we want to try X" / "we're evaluating" / "I just signed up to play with it."*

### Tier 2 — ask in minutes 3–6

3. **"What's your team building or testing today? Network elements, internal tools, customer-facing portals — or some mix?"**
   *Web vs. network. The fork in the road for everything you do next.*

4. **"You signed up for the trial last week — what's the first thing you want to try with it?"**
   *Direct. Tells you the use case in one sentence.*

5. **"What does your current test stack look like — what tools are you using day-to-day?"**
   *If you hear TTCN-3, IxLoad, Spirent, Robot Framework, internal Python rigs → network domain. If you hear Selenium, Cypress, Playwright, Postman → web domain. Calibrate.*

### Tier 3 — ask in minutes 6–10 if there's room

6. **"Where does your testing process bite the most right now — speed, flakiness, maintenance, coverage?"**
   *Pain question. Most useful one in the entire call.*

7. **"How does picking new tooling work in your group — central, BU-by-BU, team-by-team?"**
   *Tells you whether he has any decision authority and how the renewal motion connects to his team.*

### Tier 4 — qualify + close in minutes 10–14

8. **"Who else on your team should be in the loop on this?"**
   *Always ask. Even if there's no fit, you've expanded the contact map.*

9. **"What would make this useful enough that you'd want to bring a few teammates on the next call?"**
   *Soft commitment test. Better than "are you interested?".*

### Tier 5 — only if it comes up naturally

10. **"Are you connected with the Nokia teams already using Testsigma, or is this a separate look?"**
    *Only ask if he raises the existing customer relationship. Don't volunteer Sabrina/Marco's names.*

---

## Pivot decisions (mid-call)

| What you hear | What you do |
|---------------|-------------|
| "Web portals / dashboards / customer-facing tools" | Standard wedge: NLP authoring, self-healing, parallel runs. CRED proof point. Path to working session with Will. |
| "Network elements / RAN / 5G / protocol testing" | Honest: "Testsigma's wedge is web/mobile/API. Not where we play for radio. What other apps does your group own?" Pivot to web scope or thank them and route. |
| "Pricing / commercials / contract" | Defer. "Let me bring in our Nokia account team for that — I want to keep this clean given the relationship in flight. Can I get back to you tomorrow with a time?" |
| "We already have Testsigma elsewhere" | "Right — and that's why I want to take this carefully. What I want to understand is what your team specifically needs, then connect you with the right people on our side." |
| "We just want to play with the trial" | "Great — let me make sure your trial environment is set up right. Will and I will send a follow-up with the right contact and a working-session time." |

---

## Don't-do list

- ❌ Don't pitch in the first 3 minutes.
- ❌ Don't quote pricing.
- ❌ Don't promise the trial environment is enabled (existing tenant may overlap).
- ❌ Don't drop Sabrina, Marco, Bala, or Saritha's names unless Bogumil raises them.
- ❌ Don't oversell — Nokia already knows Testsigma.
- ❌ Don't dismiss his use case if it's not a fit. Listen, ask, route.

---

## Next-step CTAs (pick one based on the call)

- **A — fit + intent:** "Let me set up a working session with Will, our SC. He can pair with Faiz on the trial directly. Best day next week — Tue or Wed?"
- **B — fit but commercial questions:** "Let me bring in our team that owns the Nokia relationship for the next conversation. I'll get back to you tomorrow with a time."
- **C — wrong fit:** "Honestly, I don't think we're the right fit for [their scope]. If anything web/UI-shaped comes up later, I'm happy to pick this back up."
- **D — exploration only:** "I'll send a few resources tailored to what you described and circle back in 2-3 weeks. Sound good?"

Always close with: **"Mind if I send a short recap so we're aligned?"**

---

## Post-call (do within 30 min)

1. Slack Mithun + Tyler — 3 lines: who, what they want, any commercial questions raised
2. Update Apollo: title (already known for Bogumil), Faiz's role, trial status, notes
3. Log in `memory/call-log.md` + add Bogumil to `memory/warm-leads.md` Nokia entry
4. Draft follow-up email per `memory/sop-post-call-followup.md` — short, recap-style, no commercial detail
5. If trial enablement came up, ping the team that owns the Nokia tenant BEFORE any action

---

*Quick reference. Full context in `callprep-nokia-bogumil-2026-05-04.md`.*
