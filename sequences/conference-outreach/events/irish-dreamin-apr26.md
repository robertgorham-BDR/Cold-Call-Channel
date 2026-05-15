# Event: Irish Dreamin'
## Date: ~April 7-8, 2026
## Status: ✅ T2s SENT Apr 21 — Shankar Kulkarni on HOLD (see below)
## Last updated: Apr 23, 2026

---

## Event Summary

| Field | Value |
|-------|-------|
| **Event** | Irish Dreamin' (Salesforce community conference) |
| **Date** | ~April 7-8, 2026 |
| **Location** | Ireland |
| **Context** | Tyler Kapeller (Testsigma) attended and passed leads to Rob |
| **Total contacts** | 4 |
| **T1 sent** | April 8, 2026 |
| **T2 due** | ~April 12, 2026 (Day 4) |

---

## Key Rule: CC Tyler Kapeller on T2

Tyler Kapeller met these contacts at the conference and passed them to Rob. He specifically said: "You can go ahead and send these emails. Just copy me on..." T2 for ALL Irish Dreamin' contacts must CC Tyler.

**Tyler's email:** Find in Apollo or Slack contact list. Do NOT send T2 without CC.

---

## Contact List

| Contact | Company | Title | T1 Status | T2 Status | Notes |
|---------|---------|-------|-----------|-----------|-------|
| **Tony Melvin** | StoreConnect | President | ✅ SENT Apr 8 (Gmail compose, .com) | ✅ SENT Apr 21 (reply-thread, CC Tyler) | P2 warm lead. Monitor for reply. See `memory/warm-leads.md`. |
| **Shankar Kulkarni** | Mastercard | — | ✅ SENT Apr 8 (Apollo, 8:23 AM) | ⛔ HOLD — unauthorized Apollo sequence email fired Apr 21 at 3:01 AM (generic template, no Tyler CC, "last week" error). Proper T2 not sent. Rob decision needed. | MASTER_SENT_LIST: T1 logged, unauth send logged. |
| Aoife Conway | PwC | — | ✅ SENT Apr 8 (Apollo, 8:37 AM) | ✅ SENT Apr 21 (reply-thread, CC Tyler) | Monitor for reply. |
| Jessica Smith | PwC | — | ✅ SENT Apr 8 (Apollo, 8:40 AM) | ✅ SENT Apr 21 (reply-thread, CC Tyler) | Monitor for reply. |

---

## Shankar Kulkarni — HOLD Details

The Irish Dreamin' Apollo sequence (`69c5895cd9da8f0021047ae6`) fired an unauthorized email to Shankar on Apr 21 at 3:01 AM ET:
- Wrong subject: "Irish Dreamin' — Saw you at the conference" (generic template)
- NOT a reply-thread to T1
- No Tyler Kapeller CC
- "Last week" reference error (event was Apr 7-8, two weeks prior)

**Rob's decision needed:** (1) Send a proper personalized T2 reply-thread with Tyler CC in a few days, or (2) hold and wait for a reply signal from the Apr 21 Apollo send. Do NOT send anything until Rob explicitly approves.

**Apollo cleanup needed:** Mark Shankar as finished in the Irish Dreamin' sequence to prevent additional unauthorized sends.

---

## Apollo Sequence Status

Irish Dreamin' Mar 2026 sequence (`69c5895cd9da8f0021047ae6`): 1 officially delivered (Shankar T1 Apr 8 via Apollo). Tony, Aoife, Jessica T1s were sent via Gmail compose, not via this sequence. All 4 contacts should be marked as finished in the sequence — no more email steps should fire.

---

## Known Data Issue — RESOLVED

Pipeline-state.md (Session 64) listed "Shankar Subramanian | PwC" — incorrect. Correct record is Shankar Kulkarni | Mastercard. MASTER_SENT_LIST.csv updated Apr 23 with correct name.

---

## ICP Notes

**Tony Melvin (StoreConnect):** StoreConnect is a Salesforce-native platform with web, mobile, and in-store channels. Multiple test surfaces — strong ICP fit. Tyler confirmed positive conversation at the event. Top priority for T2 and eventual meeting.

**PwC contacts (Aoife Conway, Jessica Smith):** PwC delivers Salesforce implementations for enterprise clients. QA of Salesforce delivery pipelines is a real pain point. Moderate-high ICP fit.

**Shankar Kulkarni (Mastercard):** Mastercard has Salesforce deployment. Standard ICP fit. Note: Other Mastercard contacts are on the DNC list (Supriya Sarade, Ksenia Shchelkonogova) — Shankar is a separate contact and is NOT on DNC.

---

## Files

| What | Location |
|------|---------|
| Tony Melvin warm lead entry | `memory/warm-leads.md` → Tony Melvin section |
| Pipeline state | `memory/pipeline-state.md` |
| MASTER_SENT_LIST verification needed | `/Work/MASTER_SENT_LIST.csv` → Shankar row |
