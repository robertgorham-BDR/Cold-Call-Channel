# Sequence: Conference & Event Outreach — Rob Gorham
## Status: 🟢 ACTIVE — Event-driven motion (not a fixed Apollo sequence)
## Last updated: Apr 9, 2026

---

## 🆕 New Agent? Read Files in This Order

Before any work on this sequence, read these in order:
1. `/Work/CLAUDE.md` → hard rules, DNC list, tool stack
2. `/Work/memory/session/handoff.md` → current pipeline state + any warm leads from conferences
3. `sequences/_shared/README.md` → shared resource index + recent updates
4. This file (README.md) → active events, WARM/COOL distinction, how to start a new event
5. `sequences/conference-outreach/events/[event-slug].md` → the specific event you're working on
6. `sequences/conference-outreach/sop-draft.md` → WARM vs. COOL formula
7. `sequences/conference-outreach/sop-send.md` → channel selection + CC rules
8. `memory/sop-conference-outreach.md` → full authoritative conference SOP

**Core rule: WARM = you spoke with them. COOL = same event, no direct contact. Never confuse the two — different formula, different tone, very different reply rates.**

---

## What This Is

Conference outreach is its own motion — distinct from both cold TAM outbound and inbound leads.

These contacts are warm-ish: they either spoke with Rob at an event (WARM) or attended the same event without connecting (COOL). The outreach formula, channel priority, and expected reply rates are all different from standard cold outreach.

**Key point:** There is no single Apollo sequence ID for conference outreach. Each event gets its own batch file and tracker. Sends use the same manual-email-send.md protocol as Factor-First.

---

## Active Events

| Event | Date | Contacts | Status | Event File |
|-------|------|----------|--------|-----------|
| QonfX Bay Area | Mar 24, 2026 | 13 | T2/T3 overdue — triage needed | `events/qonfx-bay-mar24.md` |
| Irish Dreamin' | Apr 8, 2026 | 4 | T1 sent. T2 due ~Apr 12. CC Tyler. | `events/irish-dreamin-apr26.md` |

> Add new events here when they occur. Create a new file in `events/` for each.

---

## WARM vs. COOL — The Core Distinction

Everything about conference outreach flows from whether you actually spoke with the person.

| Tier | Definition | Reply Rate | T1 Approach |
|------|-----------|-----------|-------------|
| WARM-HOT | Spoke with, specific next step agreed at event | 40-60%+ | Reference exact conversation + agreed next step |
| WARM | Spoke with, no specific commitment | 25-40% | Reference the conversation warmly, advance the relationship |
| COOL | Attended same event, didn't connect directly | 8-15% | Standard TAM T1 formula with conference-context opener |

Do NOT treat COOL contacts as WARM. It reads as presumptuous and can damage credibility.

---

## How to Start a New Event

When a new conference or event comes up:

1. **Collect the attendee/speaker list** — event app, sponsor portal, or organizer
2. **Segment WARM vs. COOL** — tag everyone Rob physically spoke with as WARM
3. **Run dedup** — check MASTER_SENT_LIST.csv and DNC list for all contacts
4. **Enrich** — run Apollo enrichment (`apollo_people_match`) for verified emails
5. **Build batch JSON** — `batches/sends-json/[event-slug]_sends.json`
6. **Create an event file** in `sequences/conference-outreach/events/[event-slug].md`
7. **Draft messages** — WARM formula (see `sop-draft.md`), COOL contacts use standard TAM T1
8. **Get Rob's APPROVE SEND** for all drafts
9. **Send** via manual-email-send.md protocol
10. **Create tracker** — `analytics/dashboards/conference-[event-slug]-tracker.html`

Full detailed protocol: `memory/sop-conference-outreach.md` (the authoritative master SOP)

---

## Apollo: No Dedicated Sequence

Conference contacts are typically NOT enrolled in a fixed Apollo sequence.

Options for tracking/sending:
- **Factor-First Outbound** (`69afff8dc8897c0019b78c7e`) — if the contact is also a TAM/Factor target, they can be enrolled here
- **Ad-hoc sends** — manual email from Apollo contact profile, tracked in the event's batch JSON file and MASTER_SENT_LIST.csv
- **LinkedIn InMail** — if InMail credits available and email is not verified (currently ~4 credits remaining — use sparingly)
- **LinkedIn Connection Request** — free, always available, good for WARM-HOT contacts if they're not reachable by email

---

## T2 Timing

Conference T2s follow a faster cadence than cold outreach because the relationship context is already established.

| Tier | T1 Channel | T2 Timing | T2 Method |
|------|-----------|----------|----------|
| WARM-HOT | Email | Day 3-4 | Reply to T1 thread |
| WARM | Email | Day 5-7 | Reply to T1 thread |
| COOL | Email | Day 5 (same as Factor-First) | Reply to T1 thread |

For Irish Dreamin' contacts where Tyler Kapeller was referenced — T2 must CC Tyler.

---

## Key Rules

| Rule | Detail |
|------|--------|
| WARM ≠ COOL | Never use WARM formula for someone you didn't speak with |
| No meeting ask in T1 (WARM-HOT only exception) | If a specific next step was agreed at the event, T1 can reference it |
| Subject lines | Use event-reference subjects. "Following up from [Event]" works. No em dashes. |
| Sender | `robert.gorham@testsigma.ai` only |
| Proof points | Avoid in WARM messages unless specifically requested — the warm context is the hook |
| T2 CC rule | If a colleague introduced the lead (e.g., Tyler at Irish Dreamin'), CC them on T2 |

---

## Performance Targets — What Good Looks Like

Conference contacts are among the warmest leads in the system. WARM reply rates should dramatically exceed cold outbound. If they don't, the WARM formula is too cold, or the contact was misclassified.

| Tier | T1 Reply Rate Target | Meeting Booking Target | Notes |
|------|---------------------|----------------------|-------|
| WARM-HOT (specific next step agreed) | ≥ 50% | ≥ 30% direct | These should convert fastest |
| WARM (spoke with, no commitment) | 25–40% | ≥ 15% | Warm relationship is the hook |
| COOL (same event, no contact) | 8–15% | ≥ 5% | Closer to cold outreach benchmarks |
| Post-T2 (WARM no T1 reply) | +15–20 pts vs COOL T1 | — | T2 closes most WARM conversations |

> **If WARM reply rates fall below 25%:** Review whether contacts were correctly classified as WARM. Also check the message formula — WARM messages should feel like a warm personal follow-up, not a product pitch.
> **If reply window > 14 days:** WARM contacts cool quickly. If 14+ days pass after an event with no contact, reassess whether WARM or COOL formula is still appropriate.

---

## Escalation Protocol — When and How to Flag to Rob

**Stop and message Rob immediately in session chat:**
- WARM contact has replied with a hard decline (P4) — add to DNC immediately
- Tyler Kapeller CC rule is unclear for a specific contact (ask before sending)
- InMail credits below 2 remaining (conserve for true WARM-HOT contacts only)
- Any contact where Rob's exact words from the event are unclear and the message will attribute a conversation that didn't happen

**Log async in `memory/session/messages.md`:**
- WARM contact hasn't replied after T2 — Rob may want to call instead
- New event announced (flag so Rob can decide whether to attend + build outreach list)
- WARM contact is now appearing in Factor-First or inbound pipeline (flag for dedup)

**After an incident:** Log in `memory/incidents.md` immediately.

**Escalation format for session chat:**
```
⚠️ CONFERENCE HOLD — [short description]
Event: [event name]
Contact: [Name], [Company], [WARM/COOL]
Issue: [what needs Rob's decision]
Recommendation: [what you think should happen]
```

---

## How to Update This File

When a new event is added, completed, or when rules change:
1. Add new events to the "Active Events" table when they're confirmed
2. Update event status (T1 sent, T2 due, completed) as the sequence progresses
3. Move events to "Completed Events" section (create if needed) when all contacts have reached final status
4. Update "Last updated" date at the top
5. Log significant changes in `sequences/_shared/README.md` → "Recent Updates"
6. Create a new event file in `events/` for every new event: `events/[event-slug-month-year].md`

---

## Shared Resource Versions

> Check `sequences/_shared/README.md` → "Recent Updates" before each session.
> If any resource below was updated AFTER your "Last Verified" date — review it before working.

| Resource | Last Verified Against |
|----------|----------------------|
| DNC list (CLAUDE.md) | 2026-04-09 |
| MASTER_SENT_LIST.csv | Live — check every session |
| sop-conference-outreach.md | 2026-04-09 |
| manual-email-send.md (v2.0) | 2026-04-09 |
| send-preflight-checklist.md | 2026-04-09 |
| proof-points.md | 2026-04-07 |

---

## Files & Links

| What | Where |
|------|-------|
| **Master conference SOP (full protocol)** | `memory/sop-conference-outreach.md` |
| Draft formulas (this folder) | `sequences/conference-outreach/sop-draft.md` |
| Send execution (this folder) | `sequences/conference-outreach/sop-send.md` |
| QonfX Bay event file | `sequences/conference-outreach/events/qonfx-bay-mar24.md` |
| Irish Dreamin' event file | `sequences/conference-outreach/events/irish-dreamin-apr26.md` |
| QonfX tracker dashboard | `analytics/dashboards/conference-qonfx-bay-mar24-tracker.html` |
| QonfX draft batch | `batches/active/qonfx-bay-mar23-drafts.md` |
| Dedup protocol | `memory/playbooks/dedup-protocol.md` |
| Manual email send protocol | `memory/playbooks/manual-email-send.md` |
| DNC list | `CLAUDE.md` → Do Not Contact List |
| Master sent list | `/Work/MASTER_SENT_LIST.csv` |
| Shared resource index | `sequences/_shared/README.md` |
