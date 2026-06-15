# Call Prep — Jeyalakshmi Stephen @ Capital One

**Date / Time:** Thursday Apr 30, 2026, 4:45–5:00 PM EDT (15 min)
**Format:** Zoom — https://us02web.zoom.us/j/89503076250
**Attendees:** Rob Gorham (you), William Dalley (Testsigma), Jeyalakshmi Stephen (Capital One)
**Origin:** Inbound — Jeyalakshmi self-booked through Tyler Kapeller's testsigma.com booking link this morning (~5:19 PM UTC). Tyler transferred ownership to you at 5:29 PM UTC.
**Type:** Net-new account, NOT in your TAM-mar26 list. No prior outreach in MASTER_SENT_LIST. Clean inbound.

---

## TL;DR — what to expect

Most likely she is a senior QA / test-automation engineer (likely TCS-badged contractor on the Capital One Frisco campus) doing personal vendor research on Testsigma. This is **discovery only** — go in to qualify, not to pitch. Capital One has heavy in-house testing tooling (AWS-native, Pytest, Cypress, QMetry, Selenium); your job is to find out which team, which app, what's broken today, and whether she's an evaluator or a champion-in-waiting.

---

## Contact intel (with confidence levels)

| Field | Value | Confidence | Source |
|------|------|-----------|--------|
| Name | Jeyalakshmi Stephen | High | Calendar invite |
| Email | jeyalakshmi.stephen@capitalone.com | Medium — Apollo flagged "email_domain_catchall: true" so this may be inferred, but the calendar invite was delivered, so it's deliverable | Calendar + Apollo |
| Location | Frisco, TX (America/Chicago) | Medium | Apollo enrichment |
| Title / role | **Unknown** — Apollo returned null, no LinkedIn experience visible | LOW | Apollo |
| LinkedIn (public) | https://www.linkedin.com/in/jayalakshmi-stephen-038263246/ — listed at "Tata Consultancy Services, Chennai" — 15 connections, 15 followers, no posts, you are 3rd+ degree | Medium — name + spelling close enough to be plausible, but identity not 100% confirmed | LinkedIn |
| Apollo Contact ID | 69f3994154c0d200111deb60 | High | Apollo |

**Why this matters:** the LinkedIn → TCS Chennai detail combined with the Apollo → Frisco TX detail is the classic pattern for a TCS contractor placed on-site at a US client. Capital One is one of TCS's largest US accounts. If true, she's likely a senior SDET / automation lead working *inside* Capital One but employed by TCS. Per your CLAUDE.md: senior SDET / automation lead is your **Influencer** persona (39.3% reply rate). **Do not assume she has buying authority — assume she is an evaluator and possibly a future champion.**

**Open the call by clarifying her role.** It's the single most important data point you don't have.

---

## Account intel — Capital One (COF)

- **Industry:** Financial services / consumer banking (credit cards, retail banking, auto loans)
- **HQ:** McLean, VA. Frisco, TX is a major engineering hub (~thousands of engineers; their public Plano/Frisco campus runs a huge slice of digital banking and card platforms).
- **Size:** ~77,000 employees (Apollo). Public on NASDAQ as COF, ~$69.3B revenue, ~$113.7B market cap.
- **Ticker / market position:** Top-10 US bank by assets, well-known cloud-first transformation story (one of the first major banks to go all-in on AWS).

### Tech stack (from Apollo org enrichment, supplemented by Capital One's public engineering blog)

- **Cloud-first AWS shop:** Lambda, EC2, S3, RDS, Glue, Fargate, CloudHSM, KMS — also some GCP, Azure
- **Languages in QA scope:** Python, Java, .NET, TypeScript, Scala, Kotlin
- **Front-end:** React, Node.js, REST + GraphQL APIs
- **Test automation already in use:** **Pytest, QMetry Automation Studio, Cypress, Selenium** (their blog confirms Selenium-based regression suites)
- **Data layer:** Snowflake, Redshift, DynamoDB, MySQL, Spark; in-house "Slingshot" data-test framework
- **CI/CD:** Jenkins, Terraform, Docker, Kubernetes
- **BI:** Tableau, Looker, Databricks, Airflow, dbt

### Capital One's stated testing philosophy (from their public engineering blog)

- "**Test early, test automatically, test often**" — the explicit mantra of their senior testing specialists
- They publish a "**Quality Filtration Stack**" model — a layered view of where coverage exists vs. needs investment
- They've built **internal frameworks** (e.g., Slingshot for data testing) — they prefer building over buying when scale demands it
- They are vocal about "right-sized testing strategy" matched to DevOps velocity

**Why this matters for your pitch:** Capital One folks are sophisticated. They are NOT going to be impressed by "we replace Selenium." They've already invested in Selenium, Cypress, and Pytest, and built internal tooling on top. Your value prop has to be sharper than "AI-powered testing" — they've heard that pitch from every vendor at every conference. **The opening worth reaching for is maintenance burden / flaky tests / coverage gap on a specific app**, not a generic platform sell.

---

## Most likely scenarios for why she booked

In rough order of probability:

1. **Personal vendor research / curiosity (40%)** — saw Testsigma in a webinar, ad, Reddit thread, or G2 listing and is sizing up the market for her own knowledge / future pitch to her team. Common pattern with TCS-badged engineers.
2. **Active project pain (30%)** — her team is wrestling with maintenance / flakiness / coverage on a specific app and she's in evaluation mode. If so, expect her to bring up **specific pain** in the first 5 minutes.
3. **Tool consolidation / RFP work (15%)** — Capital One does periodic tool rationalization. She could be doing a market scan as part of an RFP shortlist.
4. **Champion building from below (10%)** — she's a senior IC who wants to bring something new in and is pre-vetting before pitching her director.
5. **Looking for a job change (5%)** — if she's TCS, she may also be evaluating tools for general career growth. Lower priority but possible.

The first 60 seconds of her answer to "what made you reach out today" will tell you which one.

---

## Suggested opening (15-min intro flow)

You have **15 minutes**. Be efficient.

**Min 0–2 — Quick intros**
- Who you are (Rob, BDR at Testsigma, agentic AI test automation)
- Who Will Dalley is (let him introduce himself briefly — likely AE / SC role)
- "Before I pitch anything, I want to understand what you came here to learn — that way I make these 15 minutes useful for you."

**Min 2–5 — Discovery (her turn)**
Open question first, then BANT + Techstack:
- "What made you reach out to Testsigma today — what are you trying to solve, or just exploring?"
- "Tell me about your team — are you on the Capital One side or with a partner like TCS, and what apps are you covering?"
- "What does your test automation stack look like today?" (You expect Selenium / Cypress / Pytest / QMetry per their tech stack)

**Min 5–10 — Targeted dig based on her answer**
If she names a pain (flaky tests, slow runs, coverage gap, maintenance burden):
- Anchor on the **CRED proof point** if it's coverage: 90% regression coverage, 5x faster releases
- Anchor on the **Medibuddy proof point** if it's maintenance: 2,500 tests, 50% maintenance cut
- Anchor on the **Hansard proof point** if it's regression cycle time: 8 weeks → 5 weeks

If she's exploratory:
- Quick 60-second story on Atto (your AI coworker / agent suite — Generator, Runner, Healer, Optimizer)
- Hit on **self-healing** as the wedge — that's the part that's hard to dismiss because every team in production has flaky locator pain

**Min 10–13 — Qualify**
- "Who else on your team would care about what we're talking about? Who owns the test strategy?"
- "What does evaluating a new tool look like in your org — is there a formal process?"
- "Are you under any timeline pressure on this — release cadence, coverage targets?"

**Min 13–15 — Next step**
- If qualified: "Would it make sense to set up a working session with Will to walk through Atto on one of your apps? I can hold something for next week."
- If exploratory only: "Happy to send you a few resources tailored to your stack and circle back in 2-3 weeks. Sound good?"
- ALWAYS: get the names of one or two other people on her team, even if she's not the buyer.

---

## Discovery questions to keep in your back pocket

| Domain | Question |
|--------|----------|
| Role | "Are you on the Capital One side directly, or are you with a partner like TCS or another vendor team?" |
| App scope | "What product or app does your team test — credit card platform, retail banking, auto, internal tooling?" |
| Stack | "What's your current automation stack — Selenium, Cypress, Pytest, QMetry, something internal?" |
| Pain | "What's the biggest pain in your testing process right now — speed, flakiness, coverage, maintenance?" |
| Volume | "How many tests are in your regression suite, and how often do you run it?" |
| Team size | "How many SDETs on your team, and how many manual QA still doing scripted work?" |
| Authority | "Who decides on automation tooling at Capital One — is it team-by-team or central?" |
| Process | "If you wanted to bring a new tool in, what would the evaluation look like — POC, security review, procurement?" |

---

## Likely objections to be ready for

- **"We've already invested heavily in Selenium / Cypress."** → Validate, don't fight. "Totally — most of our Capital One-tier customers come to us not to rip out Selenium but to take the maintenance burden off it. The self-healing piece tends to be where teams get the first 50% maintenance cut without changing what they already have."
- **"We build our own tooling."** → "Makes sense — Capital One's published a lot on Slingshot and the Quality Filtration Stack, so I know your team isn't shy about building. The teams that buy us usually do so when they're losing more time maintaining locators than building new test logic. Is that ringing true at all on your side?"
- **"Security / compliance is hard at Capital One."** → "We have SOC 2, on-prem deploy options, and customers in regulated banking and pharma — happy to send our security one-pager. Where in your stack would something like us need to land?"
- **"Pricing?"** → "Our pricing scales with parallel test runs and platforms covered. Will can put together a custom quote based on your scope. Want me to put that on the next call?"

---

## Conference / proof points worth name-dropping (pick 1–2 max)

- **CRED** (FinTech) — 90% regression coverage, 5x faster releases — closest analog to a Capital One-style dev velocity story
- **Medibuddy** — 2,500 tests, 50% maintenance reduction — speaks to maintenance burden
- **Hansard** — regression cycle 8 weeks → 5 weeks — speaks to release cadence
- Logos worth dropping: **Cisco, Samsung, Honeywell, Bosch, Nokia, DHL, Oscar Health, Sanofi**

---

## Open gaps to clarify on the call (or after)

1. **Her actual role and team** — Apollo gave us nothing, LinkedIn is sparse. This is question #1.
2. **TCS vs. Capital One badge** — affects authority and what kind of follow-up makes sense.
3. **What specifically prompted her to book** — referral, ad, content, conference, or something else.
4. **App / domain** — credit card, retail, auto, ML platforms, internal? Determines which proof points land.
5. **Decision-making structure on her team** — central QA org? Embedded SDETs? Hybrid?

---

## Post-call to-do list (for after the meeting)

- Update Apollo contact with title, team, and notes
- Add Capital One to your TAM list if she qualifies (you'd want to do this through Akhil — Capital One isn't currently TAM)
- If qualified: book a follow-up demo with Will — record it, transcript, draft a follow-up email per `memory/sop-post-call-followup.md`
- If exploratory: schedule a check-in cadence (2–3 weeks) and send a tailored resource pack
- Log the meeting outcome in `memory/call-log.md` and `memory/contact-lifecycle.md`
- If she shares her role / team, save that as a contact note — useful intel for any future Capital One outreach

---

*Generated 2026-04-30, ~3 hr before call. Sources: Google Calendar, Gmail thread 19ddf676ed56c24d, Apollo people_match (Contact ID 69f3994154c0d200111deb60), LinkedIn public profile, Capital One engineering blog, Apollo org enrichment for capitalone.com, MASTER_SENT_LIST.csv, tam-accounts-mar26.csv.*
