# SOP: Cold Call — Full Loop
**Version:** 2.1 — Updated Apr 29, 2026 (Account-Level Prep v2.1 — dual-persona intros, opener TBD)
**Previous:** v2.0 Apr 22, 2026 (account-level prep format), v1.0 Apr 17, 2026 (condensed card format)
**Author:** Claude (Cowork session)
**Scope:** All cold calls to TAM + Factor account contacts — pre-call prep, live call execution, post-call logging.

---

## When to Run Cold Calls

Cold calling runs as a **separate block from the daily T1/T2 email motion** — not mixed in. Best practice is dedicated calling blocks of 30-90 minutes.

**Who to call:**
1. **Warm leads P0-P1** — always call these first. Check `memory/warm-leads.md`. Any prospect who replied positively or showed buying intent gets a live call attempt before next email touch.
2. **T3+ sequence contacts** — contacts who have received at least 2 emails without reply. Stage monitor surfaces these in `memory/call-log.md → Active Call Targets`.
3. **Factor account contacts** — highest intent, always worth a call attempt alongside email outreach.
4. **Inbound leads** — if assigned via Salesforce and no meeting booked yet, call immediately. See `sequences/inbound-leads/`.

**When NOT to call:**
- Contacts on the Do Not Contact list in CLAUDE.md
- Anyone who explicitly said "not interested" or opted out via email
- Contacts outside TAM/Factor account universe

**Daily call targets (benchmark):**
- Active calling day: 20-30 dials minimum
- Blocked calling session: 50-100 dials
- Connect rate target: 8-15% (current average: 3.6% — see call-log.md)

---

## Phase 1: Pre-Call Prep

**Time required:** 5-10 min for a batch of 5-10 contacts. Do this the night before or first thing in the AM calling block.

### Step 1 — Pull Today's Call List and Request Research Cards

Paste your Apollo call task list directly into the Cowork chat. Claude will return one **Company Research Card** per account — formatted for fast scanning on the phones.

**Account-Level Call Prep Format (locked v2.1 — Apr 29, 2026)**

This replaces the v2.0 format. Rob dials off the v2.1 format because (a) the prep card has to be glanceable on the phone — no walls of text, (b) Pain has to be real and account-specific, not vertical-generic, (c) the intro frame has to bridge directly into how Testsigma helps THIS persona, and (d) the opener is still being workshopped — see "Opener (workshop)" note below.

Each account gets ONE prep card with three blocks: **Pain**, **Adaptive Intro (split by persona)**, **Opener**. No Source line, no Pivots block, no Close.

```
## [COMPANY]

**Pain:**
- [Platform/product 1] — [specific, account-real QA pain — what breaks, where, why it matters]
- [Platform/product 2 OR a different angle of pain on platform 1] — [specific QA pain, NOT vertical-generic filler]

**Adaptive intro — QA persona** *(QA Manager / Director / VP QA)*:
"[Conversational opening framing the QA leader's day-to-day pain] — [what Testsigma actually does about it] — [the payoff for THEIR team / their release rhythm]."

**Adaptive intro — Engineering persona** *(Director / VP / Senior Director of Engineering)*:
"[Same pain reframed through engineering's lens — QA as bottleneck, velocity, headcount cost] — [what Testsigma does to remove that drag] — [the payoff in eng terms — ship cadence, team cost, output]."

**Opener:** [WORKSHOP — see Rules #6 below — currently iterating on the right opener formula]

**Persona routing for this account:**
- [Contact 1 name + title] → QA intro / Engineering intro
- [Contact 2 name + title] → QA intro / Engineering intro
- ...
```

**v2.1 Rules (locked Apr 29, 2026):**

1. **Pain = 1-2 short bullets, glanceable.** Each bullet is `[platform/product] — [specific QA pain]`. No prose paragraphs. No Source line. The platform must be a real product/system at this company.
2. **Second bullet must be a real, account-specific QA pain.** Not vertical-generic filler ("ops back-office quality control," "regulatory cycles," "release cadence"). It must be something a QA leader at THIS company would immediately recognize as their own. The clearest second-bullet pattern is something Testsigma directly fixes — brittle UI tests, login/transfer/MFA flows, mobile+web parity, integration test surface explosion.
3. **No Source line.** Sources stay in research notes; they're noise on the prep card.
4. **Adaptive intro is split into TWO versions — QA persona + Engineering persona.** Same pain, two angles:
   - **QA intro** speaks to the QA leader's daily pain (test maintenance, flakiness, coverage pressure) and names what Testsigma does (self-healing AI, AI-generated tests, NLP authoring).
   - **Engineering intro** reframes the same pain through engineering's lens — QA as bottleneck to release velocity, headcount scaling pressure, ship cadence — and names how Testsigma removes that drag.
   - Each intro must do three things in one breath: (a) name a specific pain, (b) name what Testsigma does about it, (c) name the outcome in *that persona's* language.
   - **Conversational, not observational.** "Most QA teams I talk to..." beats "Healthcare teams typically..." Sound like a peer, not an analyst.
5. **No pivots block, no close block.** Proof points + close come from live discovery + Phase 2 of this SOP, not from the prep card.
6. **Opener (workshop, Apr 29).** Rob is iterating on the right cold-call opener formula. The framework being tested:
   - Honest about being a cold call ("I'll be upfront")
   - Honest about wanting time eventually ("hoping to earn your time, not take it") but **not** asking for a meeting in the opener
   - Account-specific hook ("saw something specific on how [Company] is testing [platform]")
   - Transition question that doesn't sound like typical phone-sales (no "Do you have a minute?" / "How are you doing today?")
   - Current top candidates being tested: "mind if I get into it?" / "cool to compare notes for a sec?" / "mind if I run it past you?"
   - **Once locked, this section will be replaced with the locked opener template.**
7. **Persona routing block is required.** Every prep card lists which contact at the account gets the QA intro vs. the Engineering intro, by name + title. No guessing on the phone.
8. **DNC + persona-mismatch flags surface BEFORE the cards.** If any contact in the batch is on the DNC list, has a known persona mismatch (CRO clinical QA, defense systems engineering, hardware QA at a manufacturer, etc.), or is at a competitor (Automation Anywhere, etc.), flag at the top of the batch — never inside the card.
9. **Job postings + tech stack are still the gold-standard signals** (see v2.0 rules — research process unchanged), but the signals stay in research notes, not on the prep card itself.
10. **Headcount = departmental count from Apollo**, not total employees. **Apollo subsidiary figures override assumed size/HQ.**

**v2.1 sample (Citizens Bank — Apr 29, 2026 reference):**

```
## Citizens (Citizens Bank)

**Pain:**
- Citizens.com + mobile app — SOX/OCC-gated regression on every release
- Brittle UI tests — login, transfer, and MFA flows shift constantly, breaking the automation suite faster than QA can rebuild it

**Adaptive intro — QA persona**:
"Most bank QA teams I talk to spend more time fixing broken tests than running them — we use AI to self-heal scripts the moment a UI flow shifts, so you're not rebuilding the same automation every release just to hold SOX coverage."

**Adaptive intro — Engineering persona**:
"At most banks, QA ends up being the gate that slows releases — every UI change cascades into broken automation and stalled regression cycles. We use AI self-healing to take that drag off so engineering ships on cadence and QA scales without adding headcount."

**Opener:** [WORKSHOP — see v2.1 Rule #6]

**Persona routing:**
- Laurelle Brennan (QA QC Manager) → QA intro
- Tiffany Friend (VP Head of Ops QA & Control) → QA intro
- Rachandeep Kaur (VP QA Engineering Manager) → QA intro
- Vikas Y (Engineering Director) → Engineering intro
```

**How cards are built (research order):**
1. **Apollo enrich** — `apollo_organizations_enrich` for departmental headcount, confirmed tech stack, revenue, funding
2. **Apollo job postings** — `apollo_organizations_job_postings` — QA/SDET/automation roles = confirmed pain. Zero QA postings at large eng org = blind spot.
3. **Web search** — recent news, engineering blog, press releases (fill gaps Apollo doesn't cover)
4. **DNC cross-check** — run against CLAUDE.md before any card is produced
5. **Wrong persona flags** — surfaced before dial, not after
6. **Pain tags** — 3 per company, each grounded in a specific Apollo signal
7. **Testsigma tags** — map to their exact pain with proof point routed by persona and vertical

**Proof point routing:**
- Test maintenance / brittle tests → Medibuddy (2,500 tests, 50% maintenance cut)
- Regression coverage gaps → CRED (90% coverage, 5x faster)
- Regression cycle time → Hansard (8→5 weeks)
- Fragmented tooling / unification play → Hansard + Cisco (enterprise scale)
- GenAI / AI feature testing → CRED + Cisco (AI-ready platform)
- Brand credibility (VP/CTO, enterprise) → Cisco, Samsung, Bosch

**To trigger:** Paste Apollo call list (raw text from task queue is fine). Claude runs enrich + job postings for each company, then builds cards.

Check these sources in order:
1. `memory/call-log.md → Active Call Targets` — stage monitor populates this with T3+ and warm leads
2. `memory/warm-leads.md` — any P0/P1 with "call" listed as next action
3. `memory/session/handoff.md` — any specific call-back promises from prior sessions
4. `sequences/inbound-leads/` — any inbound leads not yet reached by phone

**If building a new list from scratch:** Pull directly from Apollo call tasks page (Tasks → Calls), or ask Claude to surface due-date contacts from batch tracker HTML files.

### Step 2 — Generate Prep Cards

For each contact, trigger the call-prep-card skill:

```
"Prep call for [Name] at [Company]"
```
or for a batch:
```
"Batch prep: [Name 1], [Name 2], [Name 3], [Name 4], [Name 5]"
```

The skill will:
- Pull their email touch history from MASTER_SENT_LIST.csv
- Pull warm lead status from warm-leads.md
- Generate persona-specific opener + voicemail + 3 discovery Qs + objection pivots

### Step 3 — Quick Context Check (for warm leads only)

Before calling a warm lead (P0/P1), do a 2-minute context check:
1. Open their Apollo contact profile in work Chrome — verify phone number is present and correct
2. Skim their LinkedIn profile (Sales Nav) for any recent activity, job changes, or posts
3. Re-read your last email exchange so you can reference it naturally on the call

For cold list dials (T3+ contacts without prior interaction), skip this — volume matters more than per-contact research here.

### Step 4 — Set Up Your Call Environment

Before starting the dial block:
- Have the call companion cheat sheet open in a browser tab (or printed)
- Have call-log.md open in a text editor for immediate post-call logging
- Have Apollo open to the contact's profile so you can log call outcomes directly
- Set a timer for your block (commitment = more dials)

---

## Phase 2: The Call

### If They Pick Up

Cold calls follow a 4-stage flow. Each stage has a target duration. Total call target: 2-5 minutes for a cold connect, 10-15 minutes for a discovery call with a warm prospect.

**Stage 1 — Permission Opener (20-30 seconds)**

Lead with your opener from the prep card. The goal is NOT to pitch. It's to get 30 more seconds.

Structure:
1. Say their name. State who you are and where you're calling from — plainly.
2. Land the pain hook (one specific problem tied to their role).
3. Name-drop a proof point. Ask a question.

Example (QA Manager):
> "Hey [Name], Rob Gorham calling from Testsigma. Most QA managers I talk to are losing 40-50% of their sprint to test maintenance. We helped Medibuddy cut that in half with AI self-healing. Is that a pain point on your side?"

What to do if they say "I'm busy" or "Can you call back?":
> "Absolutely. Quick question before I let you go — is test maintenance actually a headache for you, or are you set?"

If they engage on the pain → move to Stage 2. If they say no interest → close gracefully (see objections below).

**Stage 2 — Discovery (60-90 seconds)**

Goal: uncover their current state, pain depth, and urgency. You talk 30%, they talk 70%.

Run through your 3 discovery questions (from prep card). Don't ask all 3 in a row — let them answer each one and react before moving to the next. Mirror their language.

Core discovery themes (pick the most relevant):
- Current state: "How much of your sprint is going to test maintenance right now?"
- Urgency: "What does your regression cycle look like before a major release?"
- Decision process: "Who owns the automation roadmap with you?"
- Budget angle: "Is QA headcount on the table for this year?"

**Red flags to listen for:**
- "We just signed a new contract" → note it, ask when renewal is
- "We don't have budget until [Q]" → note it, ask permission to follow up then
- "Not the right person" → ask who the right person is before hanging up

**Stage 3 — Value Bridge (30-45 seconds)**

Tie their specific pain (what they just told you) to one Testsigma proof point. One story only. Don't list features.

Formula:
> "So here's why I ask — [Customer X] was dealing with exactly that. They [result in their own words]. That's what we built Atto to solve."

Proof point routing:
- Test maintenance / brittle tests → Medibuddy (2,500 tests, 50% maintenance cut)
- Regression coverage → CRED (90% coverage, 5x faster)
- Regression cycle time → Hansard (8 → 5 weeks)
- Brand credibility (VP/CTO) → Cisco, Samsung, Bosch

**Stage 4 — CTA / Close (15-20 seconds)**

One ask. Don't give options. Don't give an easy out.

Default CTA (all personas):
> "Would it make sense to put 15 minutes on the calendar to show you how that'd look on your stack? What day works?"

If they say "send me info first":
> "Happy to. But honestly a 15-minute call would cover more ground than a deck — you'd actually see it on your own app. What day works?"

If they agree to a meeting:
- Lock in a day + time before you hang up
- Say "I'll send a calendar invite to [email] — is that still the best address?"
- Send the invite immediately after the call

---

### If Voicemail

Leave a voicemail every time. 30 seconds max. Use your prep card voicemail script.

**Voicemail formula:**
> "Hey [Name], Rob here from Testsigma — [1 sentence value prop tied to their pain]. [One proof point sentence]. Happy to show you how that works for your team. What day works for a quick call? [Callback number]. Talk soon."

Always end with: "I'll shoot you an email as well." This sets up a natural reply.

**Voicemail cadence rule:** Leave a voicemail on T3+ contacts and warm leads. For cold TAM list dials (no prior email interaction), voicemail is optional — move fast.

---

### Objection Quick Reference

| What they say | What you say |
|---------------|-------------|
| "Not interested" | "Totally fair. Out of curiosity — is test maintenance actually not a problem for you, or is the timing just off?" |
| "We have a tool" | "Smart. Most teams I talk to using [tool] still deal with maintenance overhead. Self-healing is a different category — would you be open to seeing what that means in practice?" |
| "Send me info" | "Happy to. A 15-minute call would actually be faster — you'd see it on your own app. What day works?" |
| "I'm busy" | "Appreciate that. Quick question before I let you go — is test maintenance a headache on your side? Yes or no?" |
| "We don't have budget" | "Got it. When does your next budget cycle open up? I'll reach back out then — who's the right person to keep in touch with?" |
| "Not the right person" | "Who owns QA automation on your side? Happy to reach out to them directly." |
| "We're happy with what we have" | "Good to hear. Just out of curiosity — how much of your sprint is going to test maintenance right now?" |

---

## Phase 3: Post-Call Logging

**Do this immediately after the call or at the end of the calling block — not later.**

### Step 1 — Log to call-log.md

Open `memory/call-log.md` and add a session entry:

```markdown
### [YYYY-MM-DD] — [Morning/Afternoon]
- Dials: [N]
- Connects: [N]
- Voicemails: [N]
- Meetings booked: [N]
- Notable connects:
  - [Name @ Company] — [outcome: positive / not interested / callback / wrong person / meeting booked]
  - [Name @ Company] — [outcome]
```

**Minimum viable entry (if pressed for time):**
```markdown
### [DATE]
- Dials: [N] | Connects: [N] | Meetings: [N]
```

Even 30 seconds of logging gives the analytics system enough to compute your connect rate.

### Step 2 — Triage Outcomes

After logging, triage each notable connect:

| Outcome | What to do |
|---------|-----------|
| **Meeting booked** | Log to `memory/pipeline-state.md`. Send calendar invite immediately. Update warm-leads.md to P0. |
| **Positive interest, no meeting** | Add to `memory/warm-leads.md` as P1. Note their exact language. Set follow-up date. |
| **"Send me info"** | Send your T1 or T2 email that same day — reference the call in the opener ("I just left you a voicemail..."). |
| **Callback requested** | Add reminder to `memory/call-log.md → Active Call Targets`. Note exact date they asked for. |
| **Not interested** | Log outcome in call-log.md. No action — sequence continues per Apollo cadence. |
| **Wrong person** | Note who the right person is. Prospect that name in Apollo if they're in a TAM/Factor account. |
| **Hard no / hostile** | Add to Do Not Contact list in CLAUDE.md. Mark as "Skip permanently" in Apollo. |

### Step 3 — Meeting Follow-Ups

If you booked a meeting on the call:
1. Send calendar invite to prospect within 5 minutes of hanging up
2. Send a brief warm confirmation email ("Great talking with you, sending the invite now — looking forward to [date]")
3. Log to `memory/pipeline-state.md` with: name, company, title, meeting type, date/time, source (cold call)
4. Update `memory/warm-leads.md` status to P0

If the meeting was recorded via Gong (already happened), use `memory/sop-post-call-followup.md` for the follow-up email.

### Step 4 — Warm Lead Updates

For any connect that showed interest (even mild):
1. Open `memory/warm-leads.md`
2. Add or update their P-status entry with: call date, what they said, next action, next touch date
3. If they're already in the warm leads file, update their entry — don't create a duplicate

### Step 5 — Apollo Logging (optional but recommended)

If you connected with someone in your TAM/Factor accounts, log the call in Apollo:
1. Open their contact profile in work Chrome
2. Log activity: Call → Outcome → Notes (brief, factual — what they said, what was covered)
3. This feeds Apollo sequence timing and surfaces contacts for next steps

---

## Key Rules

1. **Calling block discipline.** Dedicate a block to calls — don't mix calls with email drafting. Phone momentum is real.
2. **Always leave a voicemail.** Even if they never call back, it warms the next email touch.
3. **Log immediately.** Call stats are only useful if they're logged. 30-second log is better than zero.
4. **One CTA per call.** Don't offer multiple options. Don't give an easy out. "What day works?" is the only close.
5. **Prep cards are required for warm leads.** For cold TAM list dials, batch prep or cheat sheet is enough.
6. **Never promise what you can't deliver.** If they ask for a specific feature or capability, verify before confirming.
7. **Connect rate vs win rate.** Rob's connect rate is stable (~3.6%). Win rate (18% → 0%) is the problem to fix. Every call is a chance to run Stage 2 discovery and learn what's causing drop-off.
8. **Referrals are gold.** "Wrong person" connects always end with "who should I talk to?" — never let them go without a name.
9. **All discovery questions must be open-ended.** Never ask a yes/no question during discovery. Yes/no questions let the prospect close the conversation. Open-ended questions keep them talking and surface real intel. Every question on every prep card must start with: How, What, Walk me through, Tell me about, Describe, or What does [X] look like. If a question can be answered with "yes" or "no", rewrite it before the call.

**Open-ended question starters (use these, not yes/no):**
- "How does your team..."
- "What does [X] look like for you?"
- "Walk me through how you..."
- "Tell me about your process for..."
- "What happens when..."
- "How are you handling..."
- "What's your biggest challenge with..."
- "Describe what [X] looks like before a release"

**Closed questions to avoid (rewrite these):**
- ❌ "Are you running manual testing?" → ✅ "What does your regression process look like right now?"
- ❌ "Do you have a QA team?" → ✅ "How is QA structured on your side?"
- ❌ "Is test maintenance a problem?" → ✅ "How much of your sprint is going to test maintenance?"
- ❌ "Would you be open to a demo?" → ✅ "What day works for a quick 15 minutes?"

---

## Files Referenced by This SOP

| File | Use |
|------|-----|
| `memory/call-log.md` | Session logging + active call targets |
| `memory/warm-leads.md` | P0-P3 status + call outcomes for warm contacts |
| `memory/pipeline-state.md` | Log meetings booked + deal stage updates |
| `skills/call-prep-card/SKILL.md` | Pre-call card generation |
| `memory/sop-post-call-followup.md` | Post-meeting follow-up emails (Gong-recorded calls) |
| `CLAUDE.md` | Do Not Contact list + persona profiles + proof points |
| `MASTER_SENT_LIST.csv` | Email touch history for any contact |
| `sequences/inbound-leads/` | Inbound lead call protocol |
| `memory/bdr-agent-vision.md` | North Star — call volume targets, quota math |

---

## Scheduled Integration

The `morning-briefing` scheduled task (weekdays 6:00 AM) surfaces Active Call Targets in the daily dashboard. The `stage-monitor` task (weekdays 6:20 AM) populates `call-log.md → Active Call Targets` with T3+ contacts due for a call.

`weekly-analytics` (Fridays 5:00 PM) reads `call-log.md` and syncs call_activity to `analytics/outreach.db`. `system-diagnostics` (Sundays) runs coaching insights from call data.

---

_Created: Apr 17, 2026. Author: Claude. Companion file: `Work/call-companion-cheat-sheet.html`_
