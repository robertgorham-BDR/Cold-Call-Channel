# Conference Outreach SOP — Inline Reference Copy
**⚠️ INLINE COPY (synced daily from source)**
**Source version: Current as of 2026-05-08 (Apr 7, 2026 last edit)**
**Last sync: 2026-05-15**
**Source: memory/sop-conference-outreach.md**


---

# Conference & Event Outreach SOP

*Created: 2026-03-24 — Based on QonfX Bay Area Edition (first live conference send session)*
*Reference event: QonfX Bay Area, March 2026 — 13 contacts, multi-channel*

---

## Scope
This SOP covers outreach to prospects met or encountered at in-person conferences, trade shows, and sponsored events. This is NOT cold TAM outreach — these are warm-ish contacts who either:
- (A) You actually spoke with at the event (WARM), or
- (B) Were at the event but you didn't get to connect (COOL — attended same event, shared context)

This distinction drives everything: messaging tone, channel priority, ask structure, and expected reply rates.

---

## Part 1: Pre-Send Preparation

### 1.1 Attendee List Collection
- Collect the full attendee/speaker list from the event app, sponsor portal, or organizer
- Export to a working CSV or JSON with: name, company, title, LinkedIn URL, email (if available)
- Identify which contacts you physically spoke with — tag them WARM
- Identify contacts you didn't speak with but are TAM/ICP targets — tag them COOL

### 1.2 Contact Segmentation
| Tier | Definition | Expected Reply Rate | Channel Priority |
|------|-----------|-------------------|-----------------|
| WARM-HOT | Spoke with, specific next step agreed | 40-60%+ | Email first, then InMail |
| WARM | Spoke with, no specific commitment | 25-40% | Email first, then InMail |
| COOL | Attended same event, no direct contact | 8-15% | Standard TAM T1 formula |

Do not treat COOL contacts as WARM. COOL contacts use the standard TAM T1 formula from `sop-outreach.md` with a conference-context opener. WARM contacts use the conference follow-up formula below.

### 1.3 Contact Enrichment & Dedup
- Run each contact through the dedup protocol (`playbooks/dedup-protocol.md`)
- Check `MASTER_SENT_LIST.csv` — never re-outreach someone already in sequence
- Check `Do Not Contact` list in CLAUDE.md
- Run Apollo enrichment to get verified email if possible (`apollo_people_match`)
- Record enrichment results in the batch JSON file before any sends

### 1.4 Build the Batch JSON File
Location: `batches/sends-json/[event-slug]_sends.json`
Example: `qonfx-bay-mar24_sends.json`

Schema per contact:
```json
{
  "priority": 1,
  "name": "First Last",
  "title": "Job Title",
  "company": "Company Name",
  "email": "email@company.com or NO VERIFIED EMAIL",
  "linkedin_url": "https://www.linkedin.com/in/...",
  "tier": "WARM",
  "channel": "email or linkedin_inmail or linkedin_connect",
  "subject": "Subject line here",
  "body": "Full approved draft body here",
  "conversation_notes": "What you talked about at the event",
  "sent": false,
  "sent_date": null,
  "send_method": null
}
```

**Priority ordering rule:**
1. WARM-HOT with verified email (Apollo email sends)
2. WARM with verified email (Apollo email sends)
3. WARM without email — InMail if credits available
4. WARM without email — Connect request if InMail credits are low
5. COOL contacts — standard TAM T1 batch process

---

## Part 2: Message Drafting — WARM Contacts

These are people you actually spoke with. The goal is to continue a conversation, not start one.

### 2.1 WARM Message Framework (proven at QonfX)

**Structure:**
1. **Opener** — Acknowledge the meeting, express genuine appreciation (1 sentence)
2. **Conversation recall** — Specific thing you discussed, detail makes it real (1-2 sentences)
3. **Bridge** — Connect that conversation detail to a reason to talk again (1 sentence)
4. **Ask** — Low-friction, specific time ask (1 sentence)
5. **Fallback** — Optional: "If not, happy to answer any questions" for HOT contacts only
6. **Close** — "Cheers," only (NO em dash, NO "- Rob", NO "— Rob")

**Word count target:** 75-110 words. These are warmer than cold T1s so can run slightly longer.

### 2.2 Example Drafts (QonfX — approved and sent)

**Rishabh Rais (Malwarebytes) — Event organizer, no specific next step:**
> Hi Rishabh,
>
> First, thank you for putting QonfX together. It was a really well-organized event and I walked away with some genuinely good conversations, yours included.
>
> I know you were pulled in a hundred directions that day, but I appreciated the few minutes we got to talk about what your team is working through at Malwarebytes on the automation side. Would you have any time this week to pick that back up now that things have settled down a bit? Or let me know if you have some followup questions first!
>
> Cheers,

**Kavya Vishnu Bhat (SK Hynix) — Specific technical concern discussed (air-gapped environments):**
> Hi Kavya,
>
> It was great meeting you at QonfX, really appreciated you taking the time to chat.
>
> I remember we got into some of the security requirements on your end, specifically around running in isolated, air-gapped environments and what that means for a tool like Testsigma. That's not a trivial requirement and I want to make sure I give you an accurate answer rather than just saying "yes we can do that."
>
> Would it be worth a conversation this week so I can loop in our solutions team and walk through your specific setup?
>
> Cheers,

**Pramod Kumar Koli (Infosys) — Demo interest stated at event:**
> Hi Pramod,
>
> It was really great meeting you at QonfX. I appreciate you taking a few minutes to stop by and chat with me and Will.
>
> If I remember correctly, you had mentioned wanting to see if a demo would make sense, would sometime this week work for you?
>
> If not, I'm happy to answer any questions you might've had that I forgot to write down.
>
> Cheers,

### 2.3 Drafting Rules for WARM Contacts

**DO:**
- Recall something specific from the conversation. If you can't remember a detail, ask Rob before drafting.
- Acknowledge WHO you were with (e.g., "me and Will") when relevant — it adds authenticity.
- Use "would sometime this week work" as the default CTA.
- Keep the ask low-pressure. These are warm relationships being built, not pitches.
- Mirror the energy of the conversation: if it was exploratory, be exploratory; if they showed interest, be direct.

**DON'T:**
- Pitch the product in the follow-up. The meeting was the pitch. This is the continuation.
- Use "I wanted to reach out" or "I'm following up on" — too formal, too cold.
- Use em dashes, hyphens mid-sentence, or AI-sounding openers.
- Say "per our conversation" — sounds like a lawyer.
- Drop customer proof points in conference follow-ups unless the prospect specifically asked for evidence.
- Make it longer than 120 words. The relationship was already established in person.

### 2.4 WARM-HOT Specific Notes
If a specific next step was agreed at the event (e.g., "send me a demo link," "let's get on a call"):
- Reference that commitment directly: "You mentioned wanting to see a demo — would [specific time] work?"
- Provide the specific thing they asked for if possible (e.g., a calendar link, a case study PDF)
- Do NOT make them re-discover the interest. Remind them.

---

## Part 3: Channel Selection & Send Execution

### 3.1 Channel Priority Logic

```
Has verified email via Apollo?
  YES → Send via Apollo (manual compose if batch <15, sequence if >15)
  NO  → InMail credits available (>5 remaining)?
         YES → Send via LinkedIn InMail
         NO  → Is contact 2nd-degree connection?
                YES → Send LinkedIn Connect request with note
                NO  → Skip for now, revisit next session
```

**InMail credit conservation rule:** If you have fewer than 5 InMail credits remaining, switch to Connect requests for 2nd-degree contacts. Connect requests have a 300-character note limit — condense the message.

### 3.2 Email Sends via Apollo (for WARM contacts with verified email)

See `memory/sop-send.md` and `memory/playbooks/send-preflight-checklist.md` for full protocol.

Key differences for conference emails vs. standard TAM T1:
- **Subject lines:** Use event-reference subjects. Tested: "Following up from [Event]" works. No need for mystery subject lines — the warm context IS the hook.
- **Sender:** Always `robert.gorham@testsigma.ai`. Verify Apollo "From" field before every send.
- **Sequence:** Do NOT enroll in the standard TAM sequence. These are one-off sends tracked in the batch JSON, not Apollo sequences. Use Apollo Manual Compose for individual sends.
- **Body injection:** Use `execCommand` method ONLY. Never Quill API. See INC-007/008/012/015.

### 3.3 LinkedIn InMail Sends (no verified email)

**Prerequisite:** Open LinkedIn Sales Navigator in the Work/Blue Chrome profile (PID for Rob's profile — verify via Windows MCP before starting).

**Compose flow (Tab bypass method — discovered Mar 24, 2026):**

The SN InMail compose form has a "Personalize your message" button that intercepts direct clicks on the body field. Bypass:

1. Click "Compose new message" button in the Inbox panel
2. In the "Type a name" ComboBox, paste the recipient's name → wait for dropdown → click correct result (verify title + company match before clicking)
3. Click Subject field → paste subject via `Set-Clipboard` + `Ctrl+V`
4. Press **Tab** once → body edit field receives focus (`has_focused: 1`)
5. Paste body via PowerShell here-string + `Ctrl+V` (see below)
6. **Gate 2 readback:** Take a DOM Snapshot — verify Subject value and body value both match approved draft exactly
7. Click Send button

**PowerShell here-string method for body text:**
```powershell
$body = @"
Hi [Name],

[Paragraph 1]

[Paragraph 2]

Cheers,
"@
Set-Clipboard -Value $body
```
Use here-string (`@"..."@`) any time the body contains double quotes, apostrophes, or multi-line content. This avoids escaping issues that break the clipboard content.

**Gate 2 readback check (MANDATORY before every Send click):**
```
Element: Edit "Type your message here…" — value must start with "Hi [Name],"
Element: Edit "Subject (required)" — value must exactly match approved subject
Character count button should show realistic number (not 0 or placeholder-length)
```
If readback does NOT match approved draft → DO NOT click Send. Refresh the compose form and re-inject.

### 3.4 LinkedIn Connect Request Sends (credit preservation)

Use when: InMail credits < 5 AND contact is 2nd-degree connection.

**Connect flow (Updated Apr 7, 2026 — preload/custom-invite + shadow DOM dispatchEvent):**

> ⚠️ Do NOT navigate to profile and click Connect. LinkedIn renders invite modals in shadow DOM — standard DOM queries and ref-based clicks are unreliable. Use the `preload/custom-invite` URL + shadow DOM `dispatchEvent` pattern for all sends. Full procedure with JS code: `memory/sop-send.md` → "Day 1 LinkedIn Connection Request Send." Skill reference: `skills/linkedin-connect/SKILL.md` Phase 5.

1. Find the contact's LinkedIn vanity URL from their Sales Navigator profile
2. Navigate to: `https://www.linkedin.com/preload/custom-invite/?vanityName=[vanity]`
3. Wait 4 seconds. Verify modal: `document.body.innerText.includes('Add a note to your invitation?')`
4. Use shadow DOM `dispatchEvent` to click "Add a note," fill note via native textarea setter, click Send — full JS in `sop-send.md` Day 1 procedure
5. Verify sent: `!document.body.innerText.includes('Add a note to your invitation')` returns `true`

**300-char message template for Connect notes:**
```
Hi [Name], great meeting you at [Event]. [1 sentence referencing what you talked about.]
Would sometime this week work to continue the conversation?
Cheers, Rob
```
Keep it under 250 characters to leave breathing room. Verify character count in PowerShell:
```powershell
$note = "Hi [Name], ..."
$note.Length
```

---

## Part 4: Tracking & Verification

### 4.1 Batch JSON Updates (post-send)
After every send, update the contact's JSON record:
```json
"sent": true,
"sent_date": "YYYY-MM-DD",
"send_method": "email_apollo | linkedin_inmail | linkedin_connect"
```
Verify all contacts show `"sent": true` before closing the session.

### 4.2 MASTER_SENT_LIST.csv Entries
Append one row per contact after all sends complete. Column format:
```
name,batch,send_date,channel,credits,file,norm
Rishabh Rais,QonfX Bay Edition Mar24,2026-03-24,LinkedIn InMail (QonfX Follow-up),1,qonfx-bay-mar24_sends.json,rishabh rais
```
- `credits`: InMail credits consumed (1 per InMail, 0 for Connect or Email)
- `channel`: Use descriptive value so the analytics engine can filter correctly
- `norm`: Lowercase full name (for dedup matching)

### 4.3 Contact Lifecycle Entries
Update `memory/contact-lifecycle.md` with a brief entry for each contact sent:
```
[Name] | [Company] | [Event] follow-up | T1 sent [channel] [date] | [notes]
```

---

## Part 5: Performance Tracking

### 5.1 Tracking Windows
Conference follow-ups typically have faster reply windows than cold TAM outreach. Track at:
- **Day 3** (72 hours): First reply wave — HOT contacts who are actively looking
- **Day 7**: Second wave — contacts who needed to decompress from the event
- **Day 14**: Third wave — contacts who flagged it for later
- **Day 30**: Final sweep — move non-responders to standard TAM pipeline if ICP match

### 5.2 What to Track
Use the conference performance tracker HTML file (see `analytics/dashboards/conference-[event-slug]-tracker.html`):
- Reply rate by channel (Email vs InMail vs Connect)
- Reply rate by tier (WARM-HOT vs WARM vs COOL)
- Reply rate vs. baseline TAM T1 cold outreach
- Meetings booked from conference leads
- Conversion: reply → meeting → demo → pipeline

### 5.3 Reply Classification (use `skills/reply-classifier/SKILL.md`)
Same P0-P4 classification as standard warm leads:
- P0: Positive with time ask / wants to meet immediately
- P1: Positive but needs scheduling
- P2: Interested but not ready (re-engage in 30+ days)
- P3: Not now — flag for later
- P4: Opt-out / unsubscribe — add to Do Not Contact list immediately

**Conference-specific reply note:** Expect more P1 and P2 replies than from cold outreach. The warm context makes people more likely to reply politely even if not immediately ready.

### 5.4 T2 Follow-Up Decision (if no reply after Day 7)
For WARM contacts who don't reply to T1:
- Day 7-10: Send T2 via the OTHER channel (if T1 was InMail → T2 is email; if T1 was email → T2 is InMail)
- T2 tone: Brief re-engagement, reference the event again lightly, don't re-pitch
- T2 template: "Wanted to bump this up in case it got lost — still happy to pick up where we left off at [Event] if timing works."
- Do NOT use the standard TAM T2 formula for conference contacts. They already know the context.

---

## Part 6: Post-Conference Lessons — QonfX Mar 2026

### What Worked
- Short, warm messages that recalled specific conversation details got the best responses
- Mentioning colleagues by name ("me and Will") added authenticity
- "Would sometime this week work" CTA felt natural for warm follow-ups
- Tab navigation from Subject field to body field reliably bypassed the SN "Personalize" overlay
- PowerShell here-string solved multi-line + special character clipboard issues cleanly
- Segmenting by channel early (email → InMail → Connect) prevented credit waste

### What to Improve Next Time
- Get attendee list BEFORE the event, not after — pre-enrich contacts so you have verified emails ready
- Take notes on each conversation at the event (voice memos, scratch pad) — richer recall = more specific messages = higher reply rate
- Tag who made intros or was present ("me and Will") for every contact at time of meeting
- For WARM-HOT contacts (explicit next step agreed), send within 24 hours of the event ending, not 48-72 hours
- Consider a tiered send schedule: HOT contacts day 1, WARM contacts day 2-3

### QonfX Specific Results (track over 30 days — update here)
| Date | Channel | Sent | Replies | Reply Rate | Meetings |
|------|---------|------|---------|-----------|---------|
| 2026-03-24 | Email (Apollo) | 9 | — | — | — |
| 2026-03-24 | LinkedIn InMail | 3 | — | — | — |
| 2026-03-24 | LinkedIn Connect | 1 | — | — | — |
| **Total** | **All** | **13** | — | — | — |

*Update this table as replies come in. Day 3 check: 2026-03-27. Day 7 check: 2026-03-31. Day 14 check: 2026-04-07. Day 30 check: 2026-04-23.*

---

## Part 6B: Apollo Campaign Deconfliction (CRITICAL — learned QonfX Mar 2026)

When contacts are enrolled in an Apollo conference campaign AND were also manually sent via Apollo Manual Compose, the campaign's Step 1 T1 task will still be queued and will fire separately — creating a duplicate send.

### The QonfX Pattern
All 13 QonfX contacts were enrolled in the "QonfX Bay Edition Mar 2026" Apollo campaign (ID: `69c17867c6d5c70019c4d267`) at Step 1. The 9 email contacts (P1-P9) were ALSO manually sent via Apollo Manual Compose on the same day. This created a deconfliction problem: the campaign's T1 email task will appear in the Apollo task queue and would send a second T1 email if clicked.

### Rules by Channel

**For contacts sent via Email (Manual Compose) — P1-P9 pattern:**
- Apollo campaign Step 1 task WILL appear in the task queue
- **SKIP that task** — mark as completed without sending. The manual compose was the T1.
- The campaign Step 2 (T2 followup) should run on its normal schedule
- When you see a T1 task for a contact who has `"sent": true` and `"send_method": "manual_apollo_compose"` in the sends.json → SKIP

**For contacts sent via LinkedIn InMail or Connect only — P10-P13 pattern:**
- Apollo campaign Step 1 email task WILL appear (if the contact has a verified work email)
- This email T1 has NOT been sent — it would be their first email touch
- **Rob's decision gate:** When this task appears, ask Rob: "Send email T1 to [Name] — they got LinkedIn already but no email yet. Send or skip?"
- If email_status in Apollo is "unavailable" or no verified email → Apollo will skip automatically, no action needed

### Pre-Send Checklist Addition (REQUIRED for future conferences)
Before doing manual composes for conference contacts who are also enrolled in an Apollo campaign:
1. Confirm which contacts already have verified emails in Apollo
2. For those with verified emails: plan to SKIP their campaign T1 task after manual send
3. For those without verified emails: the campaign will handle their first email touch naturally when email is found
4. Add a note to the sends.json: `"apollo_campaign_t1_pending": true/false` per contact

### Apollo Task Queue Deconfliction Protocol
When opening the Apollo task queue after a conference manual send:
1. Filter tasks by the conference campaign name
2. For each Step 1 task: check sends.json — if `"sent": true` and channel is email → SKIP (click through without sending OR mark task done via UI without sending)
3. For each Step 1 task where LinkedIn was T1 and email hasn't been sent → surface to Rob for decision
4. Never auto-click "Send Now" on a T1 task for a conference contact without this check

---

## Part 7: Agent Instructions for Future Conference Events

When Rob says "we just got back from [Event]" or "I have a list of people I met at [Conference]":

1. **Ask for:**
   - Event name and date
   - Attendee/met-contact list (names, companies, titles, LinkedIn URLs)
   - Which contacts Rob actually spoke with vs. just attended same event
   - Any specific notes on what was discussed per contact
   - Rob's approximate InMail credit count remaining

2. **Build** the batch JSON file using the schema in Part 1.4

3. **Enrich** each contact via Apollo `apollo_people_match` — prioritize verified email

4. **Draft** messages using the WARM framework (Part 2) for spoken-with contacts, standard TAM T1 for attendee-only contacts

5. **Present to Rob** for approval — all drafts in one organized view before any send

6. **Execute sends** after APPROVE SEND is given:
   - Email sends via Apollo Manual Compose (not sequence)
   - InMail sends via LinkedIn SN compose (Tab bypass method, PowerShell here-string, Gate 2 readback)
   - Connect requests via SN overflow menu → Add note (300 char max)

7. **Update records** — batch JSON, MASTER_SENT_LIST.csv, contact-lifecycle.md

8. **Set performance tracking reminders** — Day 3, 7, 14, 30 checkpoints

9. **Create the conference performance tracker HTML** at `analytics/dashboards/conference-[slug]-tracker.html`
