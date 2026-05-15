# Send SOP — Conference & Event Outreach
## Multi-channel send execution for conference contacts
## Updated: Apr 9, 2026

> Full pre-send preparation protocol: `memory/sop-conference-outreach.md` Part 1
> Full email send protocol: `memory/playbooks/manual-email-send.md` (v2.0)

---

## Prerequisites Before Any Send

1. ✅ Contact classified: WARM-HOT / WARM / COOL
2. ✅ Dedup check passed (MASTER_SENT_LIST.csv + Apollo)
3. ✅ DNC check passed (CLAUDE.md)
4. ✅ Domain block list check passed (`memory/domain-block-list.md`)
5. ✅ Draft approved by Rob (APPROVE SEND received)
6. ✅ Channel selected and credits verified (see below)
7. ✅ Batch JSON file built for the event

---

## Channel Selection

Conference contacts can be reached via multiple channels. Priority order:

| Priority | Channel | When to Use |
|----------|---------|-------------|
| 1 | Email | If verified email available. Always preferred. |
| 2 | LinkedIn InMail | If no email AND InMail credits available (~4 remaining — use sparingly) |
| 3 | LinkedIn Connect | If no email AND InMail credits depleted. Free. Good for WARM-HOT. |
| 4 | Skip for now | If no email, no LinkedIn URL, and no credits — flag to Rob |

For WARM contacts with a verified email: email is always the first move.

---

## Email Send — Manual Protocol

**DO NOT use Apollo's sequence task queue for sends.**

Conference emails are sent from the contact's individual Apollo profile page, same as Factor-First.

Full protocol: `memory/playbooks/manual-email-send.md` (v2.0)

**Key steps:**
1. Open contact's Apollo profile page
2. Click "Send Email"
3. Verify From field = `robert.gorham@testsigma.ai`
4. Inject subject (React native HTMLInputElement setter + dispatchEvent)
5. Inject body (execCommand insertText on .ql-editor)
6. Install fetch interceptor to verify send_now API returns 200
7. Visual verify before sending
8. Send → confirm interceptor caught 200 → confirm composer closes

---

## LinkedIn InMail Send

If verified email is not available and InMail credits permit:
1. Open contact's LinkedIn Sales Navigator profile in work Chrome
2. Click InMail
3. Use the WARM subject line format ("Following up from [Event]")
4. Send WARM formula body
5. Log in MASTER_SENT_LIST.csv with "LinkedIn InMail" as channel

⚠️ InMail credits: ~4 remaining (as of Apr 2026). Use only for high-priority WARM contacts where no email is available.

---

## LinkedIn Connection Request Send

For WARM-HOT contacts with no email and depleted InMail credits, or as a supplementary touch.

Full protocol: `memory/sop-send.md` → "Day 1 LinkedIn Connection Request Send"

Note message for conference connection requests:
```
Hi [Name], great meeting you at [Event]. [1 sentence referencing what you talked about.]
```

**Method: preload/custom-invite URL + shadow DOM dispatchEvent pattern** (see sop-send.md for full JS code). Do NOT navigate to profile and click Connect — LinkedIn renders invite modals in shadow DOM and standard DOM clicks are unreliable.

---

## CC Rules

| Situation | Rule |
|-----------|------|
| Tyler Kapeller introduced a contact (e.g., Irish Dreamin') | CC Tyler on T2 (NOT T1). Rob's direct T1 first, then Tyler is looped in on T2. |
| Conference organizer / sponsor contact | No CC needed unless Rob specifies |
| Any other colleague handoff | CC on T2 per Rob's direction |

---

## Event Batch JSON File

Every conference event gets a JSON file for tracking:

Location: `batches/sends-json/[event-slug]_sends.json`

Example: `batches/sends-json/qonfx-bay-mar24_sends.json`

Schema per contact:
```json
{
  "priority": 1,
  "name": "First Last",
  "title": "Job Title",
  "company": "Company Name",
  "email": "email@company.com",
  "linkedin_url": "https://www.linkedin.com/in/...",
  "tier": "WARM",
  "channel": "email",
  "subject": "Subject line here",
  "body": "Full approved draft body here",
  "conversation_notes": "What you talked about at the event",
  "sent": false,
  "sent_date": null,
  "send_method": null
}
```

Update `"sent": true` and `"sent_date"` after each confirmed send.

---

## Logging

After each send:
1. Update event batch JSON (`sent: true`, `sent_date`, `send_method`)
2. Log in MASTER_SENT_LIST.csv (Name, Company, Title, Email, Sequence: "Conference-[EventSlug]", T1 Date, Channel)
3. Update event file in `sequences/conference-outreach/events/`
4. Update `analytics/dashboards/conference-[event-slug]-tracker.html` if it exists

---

## Post-Send Verification

Run `skills/post-send-verifier/SKILL.md` to confirm email sends landed in Gmail Sent.

Conference sends are one-off, not batched — verify each one individually the same session.

---

## Post-Send Logging Gate (INC-024, v4.8)

**MANDATORY:** After every successful send (email, InMail, or LinkedIn connection), append a row to `MASTER_SENT_LIST.csv` BEFORE moving to the next contact. This is a hard stop — the send is NOT complete without the MASTER row.

**If logging fails, STOP the batch and alert Rob.**

Example rows:
- Email: `[Name], QonfX Bay Conf Apr15, 2026-04-15, Email Conf, 0, qonfx-contacts.html, [lowercase name]`
- InMail: `[Name], QonfX Bay Conf Apr15, 2026-04-15, LinkedIn InMail, 0, qonfx-contacts.html, [lowercase name]`

See `memory/sop-tam-outbound.md` Part 25 for full protocol.

---

*SOP updated Apr 15, 2026 (v4.8): Extended post-send logging gate from T2-only to ALL sends.*
