# Send Preflight Checklist — Inline Reference Copy
**⚠️ INLINE COPY (synced daily from source)**
**Source version: v3.0 (Apr 8, 2026) — Draft inspection protocol added**
**Last sync: 2026-05-15**
**Source: memory/playbooks/send-preflight-checklist.md**


---

# Consolidated Send Pre-Flight Checklist
## Version 3.0 — Apr 8, 2026 (Draft inspection protocol added — all drafts reviewed one by one before APPROVE SEND. Previous: v2.0 Mar 22.)

> **⚠️ AGENT: Always read this file fresh. Version number and date are in the header. If you are relying on a cached version from a session summary, discard it and read the live file.**

> **This checklist has three tiers:** Draft inspection (per draft, before presenting to Rob). Batch-level checks (run ONCE before presenting finalized batch). Per-send checks (before EACH individual send during execution).

---

## Tier 0: Draft Inspection (run ONCE per draft, before showing to Rob)

> **This is the most important gate in the entire process.** Over 90% of drafts require revision before they are ready. Do not shortcut this step.

### 0A. Auto-QA Score
- [ ] Run draft through `skills/draft-qa/SKILL.md` MQS rubric
- [ ] Score is >= 9/12 before presenting to Rob (sub-9 = rewrite first, don't show it)

### 0B. Present to Rob One at a Time
- [ ] Present each draft individually using this format:
  ```
  Draft #[N] of [total] — [Name], [Company], [Title]
  Email: [address]
  Subject: [subject line]

  ---
  [Full email body]
  ---

  MQS: [score]/12 | Proof Point: [story] | Email status: [verified/catchall/extrapolated]
  Notes: [any flags]

  Reply: APPROVE / [edits] / SKIP
  ```
- [ ] Wait for Rob's response on this draft before presenting the next one
- [ ] If Rob provides edits: rewrite and show the revised version before adding to queue
- [ ] Do NOT present a batch summary table and ask for one APPROVE SEND until ALL individual drafts have been reviewed

### 0C. What "Approved" Means
- Rob replied "APPROVE" or equivalent (not just "ok" or "looks fine" — ask for clarity if ambiguous)
- The exact draft Rob approved is what goes into the sends.json — no further changes
- If Rob's edits result in a new draft, the new version is what gets sent — not the original

### 0D. Expected Failure Rate
Expect to rewrite more than 90% of first-attempt drafts. Common issues:
- Opener uses title→pain inference instead of industry truth (Para 1 rule violation)
- Wrong proof point for the vertical
- Two contacts at the same company share the same angle or proof point
- Stale formula used (check SOP header date before drafting)
- Missing personalization from LinkedIn research (company-level fact attributed to individual)
- Em dash in subject line or body

---

## Tier 1: Batch-Level Pre-Flight (run ONCE before presenting to Rob)

These checks apply to ALL contacts in the batch. Run them during draft creation, not during send execution. If any contact fails, remove them from the batch before presenting to Rob.

### 1A. Contact Clearance (per contact)
- [ ] Contact's company is on TAM (tam-accounts-mar26.csv) or Factor (target-accounts.md) list
- [ ] Contact is NOT on DNC list (CLAUDE.md)
- [ ] Contact's domain is NOT on domain block list (memory/domain-block-list.md)
- [ ] Contact is NOT already in MASTER_SENT_LIST.csv (dedup check)
- [ ] Contact is not owned by another rep or enrolled in someone else's sequence
- [ ] Contact is not a current customer or in active talks with Testsigma

### 1B. Draft Quality (per draft — these run after Tier 0 inspection is complete)
- [ ] Draft has passed MQS >= 9/12 (confirmed during Tier 0)
- [ ] Rob has individually approved this specific draft (confirmed during Tier 0)
- [ ] Draft is the exact approved version — no changes made after Rob's approval
- [ ] Draft contains no placeholder text whatsoever
- [ ] Name and company spelled correctly and match the prospect's current info

### 1C. Batch Presentation Format (after ALL individual drafts are approved)
Only present this summary AFTER every draft in the batch has been individually reviewed and approved by Rob:
```
BATCH [N] — [count] contacts — all individually approved

| # | Name | Company | Title | Subject Line | MQS | Proof Point | Status |
|---|------|---------|-------|-------------|-----|-------------|--------|
| 1 | Jane Doe | Acme Corp | QA Manager | [subject] | 11/12 | Hansard | APPROVED |
| 2 | ... | ... | ... | ... | ... | ... | APPROVED |

All [count] drafts individually reviewed and approved above.
Sends JSON: batches/sends-json/batch{N}_sends.json

Reply APPROVE SEND to authorize send execution.
```

### 1D. Rob's Approval
- [ ] Every draft in the batch was individually reviewed by Rob (Tier 0 complete)
- [ ] Rob has replied "APPROVE SEND" for batch execution
- [ ] Any contacts Rob flagged as SKIP have been removed from the sends JSON

---

## Tier 2: Per-Send Checks (run before EACH individual send during execution)

Once Rob has given batch APPROVE SEND, the agent executes sends autonomously. These checks still run per contact but do NOT require Rob's input unless something fails.

### 2A. Send Configuration (verify at session start, spot-check every 10 sends)
- [ ] Sending from `robert.gorham@testsigma.ai` (NOT any other address)
- [ ] Using the blue/work Chrome profile (NOT red/personal)
- [ ] For T2: email is a REPLY to the original T1 thread (NOT a new email)
- [ ] Subject line is present and matches the approved formula

### 2B. INC-012 Readback Verification (EVERY send)
- [ ] JS readback: `document.querySelector('.ql-editor').innerText.trim().slice(0, 120)` matches approved draft
- [ ] If readback does NOT match → STOP immediately, do not send, log in friction-log.md

### 2C. Post-Send Verification
- [ ] After send: task completes in Apollo (check via JS or visual confirmation)
- [ ] Every 10 sends: batch verify via Gmail MCP that all 10 landed in Sent
- [ ] Update running send count in activity-log.md

### 2D. End-of-Batch Wrap
- [ ] Final Gmail MCP sweep — verify ALL sends from this batch landed in Sent
- [ ] Update MASTER_SENT_LIST.csv with all new rows
- [ ] Update batch tracker status for each contact
- [ ] Update activity-log.md with final send count
- [ ] If any sends failed verification: log in friction-log.md and flag for Rob

---

## Quick Reference: Common Failures

| Failure | What Goes Wrong | How to Prevent |
|---------|----------------|----------------|
| Placeholder text sent | "Replace this with draft" gets emailed to prospect | NEVER put placeholder text in composer. Only paste final draft. |
| Wrong sender | Email goes from .io or personal address | Always check "From" field at start of send session |
| T2 as new thread | Prospect gets disconnected email, looks like spam | Always use "Reply" on original thread, never compose new |
| Wrong body sent | Quill DOM disconnected from Apollo payload | Always do JS readback verification before every send |
| Double-send | Same person emailed twice from different batches | Run batch-level dedup against MASTER_SENT_LIST before presenting to Rob |
| Bounced domain | Email bounces, hurts sender reputation | Check domain-block-list.md during batch-level pre-flight |
| LinkedIn message rewritten at send time | Different text sent than approved (INC-022) | Use exact tracker message. See `memory/playbooks/linkedin-send-preflight.md`. |

---

## Failure Recovery During Send Execution

| Failure | Recovery |
|---------|----------|
| **Gmail MCP unavailable** during verification | Check Apollo UI directly (contact profile > "Last touched" timestamp). If Apollo shows current timestamp, send likely succeeded. If unverifiable after 60 seconds, STOP batch and escalate to Rob. |
| **Apollo session timeout** mid-batch | Navigate to Apollo home and back to Tasks. Re-verify "From" address. If 401/403 auth error, stop, re-authenticate, notify Rob. |
| **Send shows complete in Apollo but not in Gmail** | Wait 30 seconds, retry Gmail search. If still missing after 60 seconds, mark "SEND FAILED — UNVERIFIED" in tracker, stop batch, escalate to Rob. |
| **Git commit fails** during handoff | Run `git status`, resolve conflicts if any. If network error, retry once, then document in friction-log.md. |

## When to STOP and Escalate to Rob (even during autonomous send execution)

- JS readback does NOT match approved draft → STOP, do not send
- Apollo shows a warning about the contact (already contacted, opted out, etc.)
- Send fails or throws an error
- Contact is at a different company than expected
- "From" address has changed to wrong account
- More than 2 consecutive sends fail verification → possible system issue
- Gmail MCP AND Apollo UI both unable to verify sends → total verification failure
- Anything feels "off" — trust the instinct, stop and ask

---

## Session Scoping for Large Batches

If a batch has 50+ contacts to send:
- Send in blocks of 25-30 per session
- After each block: run Gmail verification sweep
- Checkpoint progress in activity-log.md: "Sent 30/80 — contacts 1-30 complete"
- If session needs to end mid-batch: full handoff protocol with exact count of remaining sends
- Next session resumes from the checkpoint, does NOT re-send completed contacts

---

---

## SOP Reference Chain (always check these in order before executing any send)

1. `memory/sop-tam-outbound.md` — end-to-end process, formula, draft rules (check version date)
2. `memory/playbooks/manual-email-send.md` — JS send workflow (check version date)
3. `memory/playbooks/send-preflight-checklist.md` — this file (check version date)
4. `memory/playbooks/linkedin-send-preflight.md` — **MANDATORY before any LinkedIn connection request send** (see INC-022)
5. `memory/incidents.md` — recent rule changes and failures (always scan the last 3 entries)
6. `memory/session/handoff.md` — current batch state and any active overrides

If any file's version date is older than 2 weeks and you've been working from it all session: re-read the live file before continuing. Instructions change.

*This checklist is referenced by: skills/apollo-send/SKILL.md, skills/compliance-gate/SKILL.md, sop-send.md, sop-tam-outbound.md, memory/bdr-agent-vision.md*
