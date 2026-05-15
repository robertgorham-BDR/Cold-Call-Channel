---
name: Conference Outreach Sequence Manifest
description: Event-driven warm outreach sequence. Pre-event prospecting, at-event connections, and post-event follow-ups to conference attendees.
type: reference
created: 2026-04-10
---

# CONFERENCE OUTREACH SEQUENCE MANIFEST
**Event-Driven Warm Prospecting**  
**Focus:** Conference attendees (pre-event outreach, at-event connection, post-event follow-up)  
**Status:** ACTIVE (event-dependent)

---

## QUICK START

1. Check `events/` folder for upcoming/active conferences
2. Read `README.md` (sequence definition, event timeline)
3. Access `events/[conference-name]-tracker.html` (attendee list + status)
4. For pre-event: Draft connection request (LinkedIn + email)
5. For post-event: Draft warm follow-up (reference meeting/conversation)
6. Follow approval + send workflow

---

## SEQUENCE DEFINITION

**Name:** Conference Outreach  
**Timeline:** Pre-event (2-3 weeks before) → At-event (live connections) → Post-event (5-7 days after)  
**Target Pool:** Conference attendees from QA/testing-focused events  
**Target Personas:** QA Manager, Director QA, VP QA, CTO  
**Cadence:** Event-dependent (2-4 conferences per quarter typical)  
**Status:** ACTIVE  
**Reply Rate Target:** 40-50% (warm, already met or will meet)

---

## FOLDER STRUCTURE

```
sequences/conference-outreach/
├── README.md ........................ Sequence definition (timeline, personas, event strategy)
├── sop-prospect.md .................. Prospecting conference attendees (LinkedIn research, list building)
├── sop-draft.md ..................... Conference outreach email formulas (pre/post event variants)
├── sop-send.md ...................... Sending procedures for conference campaigns
├── _MANIFEST.md ..................... This file
├── docs/ ............................ Inline reference copies (synced daily)
│   ├── contact-lifecycle.md ......... Copy of global contact stage machine
│   ├── cadence-rules.md ............. Conference sequence cadence rules
│   ├── domain-block-list.md ......... Hard bounce domains
│   ├── decision-trees.md ............ Operational decision flowcharts
│   ├── checklists.md ................ All operational checklists
│   └── dnclist.md ................... Conference-specific DNC entries
├── events/ .......................... Per-event folders (1 folder per active conference)
│   ├── [event-slug]-tracker.html ... Real-time attendee tracking + reply status (30-day window)
│   ├── [event-slug]-attendees.csv . Attendee list (name, title, company, LinkedIn)
│   ├── [event-slug]-notes.md ....... Event-specific notes (agenda, key talks, themes)
│   ├── [event-slug]-status.md ...... Phase status (pre-event, during, post-event)
│   └── ...more events as they occur
├── templates/ ....................... Event-specific templates
│   ├── linkedin-connection-template.md  Pre-event LinkedIn connection request
│   ├── t1-pre-event-template.md ... Pre-event email (see you at [event])
│   ├── t1-post-event-template.md .. Post-event email (great to meet you at)
│   ├── subject-lines.md ............ Event-specific subjects
│   └── proof-points-events.md ...... Event-relevant proof points
├── active-campaigns/ ................ Current event campaign trackers
├── completed-events/ ................ Historical event data
└── notes/ ........................... Sequence-specific learnings
    ├── event-roi-analysis.md ........ Which events generate most replies/meetings
    └── attendee-source-performance.md  Which attendee sources reply best
```

---

## EVENT TIMELINE & PHASES

**Phase 1: Pre-Event (2-3 weeks before event date)**
- Get attendee list (sponsor/registration data)
- LinkedIn research on key attendees
- Draft connection requests + emails
- Send connections + initial emails (warm touch)

**Phase 2: At-Event (during event)**
- Network at event (if attending)
- Make live connections with prospects
- Add contact notes in Apollo
- Follow-up email draft (reference meeting)

**Phase 3: Post-Event (5-7 days after event ends)**
- Send warm follow-ups (reference conversation/meeting)
- Track replies (30-day post-event window)
- Move warm replies to inbound-leads sequence
- Document ROI metrics

---

## ACTIVE EVENTS (Current Quarter)

Check `events/` folder for real-time status. Current active events:

| Event | Dates | Status | Tracker |
|-------|-------|--------|---------|
| [Event Name] | [Date Range] | [PRE/DURING/POST] | [event-slug]-tracker.html |

---

## PROSPECTING RULES

✅ **Attendee Verification:** LinkedIn-verified attendee info before reach-out  
✅ **Persona Matching:** QA titles prioritized (manager, director, VP); SDE secondary  
✅ **Connection First:** LinkedIn connection request before email (warms the relationship)  
✅ **Company Research:** Company size, vertical, potential fit before outreach  
✅ **List Cleanliness:** Remove competitors, vendors with conflicts, prior DNC entries

---

## DRAFTING RULES

### Pre-Event Email
✅ **Angle:** "Coming to [Event]? Would love to connect."  
✅ **Proof Point:** Brief mention of event relevance or shared interests  
✅ **CTA:** Light ("see you there?" or "coffee?" if attending; "would love to chat before the event")  
✅ **Length:** <100 words (friendly, not salesy)

### Post-Event Email (If Met)
✅ **Opening:** Reference specific conversation or moment from event  
✅ **Value:** Brief mention of how Testsigma relates to conversation  
✅ **CTA:** "Want to learn more?", "Curious how this applies to your team?", "Quick 30-min call?"  
✅ **Length:** <100 words

### Post-Event Email (If Didn't Meet)
✅ **Opening:** Reference event + shared interest in [topic discussed at event]  
✅ **Value:** "Many teams at [event] are exploring X, we help with that."  
✅ **CTA:** Engagement-first ("Any thoughts on how QA automation fits into your roadmap?")  
✅ **Length:** <100 words

---

## CADENCE

**Pre-Event Phase:** 2-3 weeks before
- Day 1: Attendee list received
- Day 2-5: LinkedIn research + list cleaning
- Day 6-7: Drafts created + approved
- Day 8-14: Connections sent + emails queued

**Post-Event Phase:** 5-7 days after
- Day 0-2: Event occurs
- Day 3-4: Rob captures meeting notes / names
- Day 5-7: Follow-up drafts created for met contacts
- Day 8+: Sends executed + reply tracking begins (30-day window)

---

## EVENT TRACKER FILES

Each active event has a `.html` tracker file (real-time Kanban board):

**Tracker Columns:**
1. **To Contact** — Identified attendees not yet contacted
2. **Contacted** — Connection request sent or email sent
3. **Connected/Replied** — Response received or connection accepted
4. **Demo Scheduled** — Meeting booked
5. **Evaluating** — In product evaluation
6. **Lost/Out** — Declined or went cold

**30-Day Window:** Tracker auto-archives 30 days after event for data preservation.

---

## INTEGRATION POINTS

| Component | Location |
|-----------|----------|
| Attendee Research | LinkedIn Sales Navigator |
| Event Data | Google Drive shared events folder (when available) |
| Drafting | `skills/draft-qa/` (same MQS rubric) |
| Sending | `skills/apollo-send/` |
| Reply Capture | Event tracker + `response-tracking/[event]-replies.md` |
| Handoff to Sales | Direct to Rob if meeting scheduled |

---

## SUCCESS METRICS

| Metric | Target | Status |
|--------|--------|--------|
| Attendees Identified (per event) | 50-150 | [TBD] |
| Connection/Email Success Rate | 70%+ | [TBD] |
| Reply Rate (pre-event) | 20-25% | [TBD] |
| Reply Rate (post-event) | 35-50% | [TBD] |
| Meetings Booked (per event) | 3-8 | [TBD] |
| Post-Event Conversion to Demo | 20-30% | [TBD] |

---

## NOTES & LEARNINGS

**What's Working:**
- Post-event personalized follow-ups (met at event) have highest reply rate (40-50%)
- Pre-event connections + email combo higher than either alone
- QA Manager titles have best conversion rate (meeting → demo)

**What Needs Improvement:**
- Attendee list accuracy (some duplicates, some no-shows)
- Event timing (some events have poor attendee engagement)
- Follow-up timing (best window is 5-7 days, not too early/late)

See: `notes/event-roi-analysis.md` (full historical analysis)

---

## MANIFEST METADATA
- **Version:** 1.0 (Phase 2)
- **Created:** 2026-04-10
- **Status:** ACTIVE (event-dependent)
- **Next Review:** 2026-05-10 (Monthly Audit)

---

**END OF CONFERENCE OUTREACH MANIFEST**

🎪 **Current Events:** Check `events/` folder for active conferences  
📊 **Tracker Files:** Each event has .html real-time tracker (30-day window)  
🎯 **Best ROI:** Post-event warm follow-ups (40-50% reply rate)
