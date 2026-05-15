# CONFERENCE OUTREACH — Getting Started

## What Is This Sequence?

**Conference Outreach** is an event-driven sequence that targets warm and cool prospects attending specific conferences. It combines pre-event outreach, in-event engagement, and post-event follow-up.

**Key characteristics:**
- **Warm contacts:** Previous conversations, warm replies, people who know Testsigma
- **Cool contacts:** Met at prior events, low-touch prior engagement
- **Event-focused:** LinkedIn connection requests, in-event DMs, post-event meetings/follow-ups

**Goal:** Connect with QA/testing leaders at key conferences → schedule meetings → drive pipeline

**Events covered:** See `sequences/conference-outreach/events/` for list of active conference trackers

---

## Decision Tree: Should I Use This Sequence?

```
Question 1: Is this contact attending a conference in our active list?
├─ YES → Continue to Question 2
└─ NO → Use Factor-First Outbound or different sequence

Question 2: Is this contact a WARM or COOL prospect (prior relationship or low-touch)?
├─ YES (warm/cool) → Continue to Question 3
└─ NO (completely cold) → Use Factor-First Outbound instead

Question 3: Is the conference within the active event window (pre-event → 30 days post)?
├─ YES → Proceed with Conference Outreach
└─ NO → Archive contact. Event is past 30-day window.
```

---

## Event Phases Explained

**Conference Outreach has 3 phases:**

1. **PRE-EVENT** (14 days before): LinkedIn connection requests to attendees
2. **IN-EVENT** (day of): DMs on LinkedIn/Twitter, booth meetings, real-time engagement
3. **POST-EVENT** (1–30 days after): Follow-up emails from meetings, schedule calls

---

## How to Execute: Phase-Based Workflow

### Phase 1: Pre-Event (LinkedIn Outreach)

**When:** 14 days before event

**Files to read:**
- `sequences/conference-outreach/events/[event-slug]-tracker.html` — Attendee list for event
- `sequences/conference-outreach/sop-draft.md` — Drafting SOP

**What to do:**
1. Check if event is in PRE-EVENT phase (see event tracker)
2. Search event attendee list for QA/testing leaders
3. Verify contact is WARM or COOL (not completely cold)
4. Draft LinkedIn connection request message (warm, brief, event-focused)
5. Send via LinkedIn (use browser automation or manual send)
6. Log in event tracker

**Expected output:** LinkedIn connection requests sent, logged in tracker

---

### Phase 2: In-Event (Real-Time Engagement)

**When:** Day of event

**Files to read:**
- `sequences/conference-outreach/events/[event-slug]-tracker.html` — Real-time engagement log
- `/Work/docs/navigation/HELP-INDEX.md` → "I need to TRACK something" → Event engagement

**What to do:**
1. Monitor attendee list for responses to pre-event outreach
2. If accepted connection → send brief DM (30 seconds on-topic)
3. If booth visitors → chat, take notes, exchange contact info
4. Log all interactions in event tracker (name, time, outcome, next step)
5. Schedule same-day or next-day follow-up for anyone who expressed interest

**Expected output:** In-event interactions logged, immediate follow-ups scheduled

---

### Phase 3: Post-Event (Follow-Up)

**When:** 1–30 days after event

**Files to read:**
- `sequences/conference-outreach/sop-send.md` — Follow-up SOP
- `sequences/conference-outreach/events/[event-slug]-tracker.html` — Post-event template
- `memory/sop-post-call-followup.md` — If meetings occurred

**What to do:**
1. For every attendee you met/connected with, send follow-up email within 2 days
2. Email should:
   - Reference specific conversation ("Great chatting about [topic] at [event]")
   - Acknowledge their interest or challenge
   - Offer next step (demo, comparison, quick call)
   - Include relevant proof point (if applicable)
3. Log send in event tracker
4. Monitor replies
5. For interested replies → use Call Prep Card → schedule call
6. Archive event after 30 days post

**Expected output:** Follow-ups sent, replies tracked, meetings scheduled

---

## Active Events

**To see current active events:**

1. Navigate to `sequences/conference-outreach/events/`
2. Look for folders named `[event-slug]/` with active trackers
3. Check tracker status: PRE-EVENT, IN-EVENT, or POST-EVENT
4. Each tracker shows attendee list, contact status, and next steps

**Events are tracked in HTML format for ease of updates**

---

## Common Questions

**Q: How is Conference Outreach different from Factor-First?**
A: **Conference** = warm/cool contacts at a specific event, event-context messaging. **Factor-First** = cold contacts at TAM/Factor accounts, account-signal messaging.

**Q: Can I use Conference Outreach for completely cold contacts?**
A: No. If contact is completely cold, use Factor-First Outbound. Conference Outreach is for warm/cool relationships only.

**Q: What counts as "warm" vs. "cool"?**
A: **Warm** = prior conversation, warm reply, introduced by mutual connection, prior meeting. **Cool** = met at prior event, saw Testsigma booth, low-touch prior engagement.

**Q: What if the event already happened?**
A: If it's past 30 days post-event, archive the contacts. Conference Outreach window is time-bounded.

**Q: Can I batch Conference Outreach contacts like Factor-First?**
A: Partially. For pre-event LinkedIn requests, yes (batch multiple). For post-event emails, each contact gets a personalized follow-up based on their specific conversation/meeting.

**Q: Where do I find the attendee list for an event?**
A: Check `sequences/conference-outreach/events/[event-slug]/` for the tracker HTML. It includes attendee list.

---

## Files in This Sequence

| File | Purpose |
|------|---------|
| `sop-draft.md` | Drafting SOP for event outreach (connection requests + follow-ups) |
| `sop-send.md` | Sending SOP |
| `README.md` | Sequence overview |
| `SEQUENCE-MAP.md` | Visual sequence workflow |
| `_MANIFEST.md` | File inventory |
| `_ref-conference-formula.md` | Conference outreach email formula |
| `events/` | Folder containing per-event trackers (HTML files) |

---

## Next Steps

1. **Check active events:** Navigate to `sequences/conference-outreach/events/` → identify active event in right phase
2. **Check phase:** Open event tracker → confirm PRE-EVENT, IN-EVENT, or POST-EVENT
3. **If pre-event:** Draft LinkedIn connection requests → log in tracker
4. **If in-event:** Monitor connections → send DMs → log interactions
5. **If post-event:** Draft follow-ups → log sends → monitor replies
6. **Monitor replies:** Use Reply Classifier skill → advance interested contacts to calls

---

## Need Help?

- **I can't find the event tracker:** See `sequences/conference-outreach/events/` → look for [event-name]-tracker.html
- **I don't know if contact is warm enough:** See `_ref-conference-formula.md` → "Warm vs. Cold" section
- **Event is past 30 days:** Archive contacts. Sequence window is time-limited.
- **I need to add a new event:** Contact Rob. New events are added to `events/` with new tracker HTML.
- **Meeting scheduled, need follow-up email:** See `memory/sop-post-call-followup.md`
- **Contact replied with interest:** See `memory/warm-leads.md` → log as P0/P1 → use Call Prep Card skill
