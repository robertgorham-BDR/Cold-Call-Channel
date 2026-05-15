# Manual Email Send Protocol — Inline Reference Copy
**⚠️ INLINE COPY (synced daily from source)**
**Source version: v2.1 (Apr 29, 2026) — Sender domain switched to .com per Rob override**
**Last sync: 2026-05-15**
**Source: memory/playbooks/manual-email-send.md**


---

# Manual Email Send Playbook
**Version 2.1 — Updated Apr 29, 2026 | Last confirmed working: Inbound batch (Saikrishna Y + Om Prakash, Apr 29, both 200 OK + Gmail verified)**
**Effective: March 25, 2026 | Reason: INC-019 — Apollo sequence email steps deactivated**

**v2.1 changelog (Apr 29, 2026):** Sender domain changed from `testsigma.ai` to `testsigma.com` per Rob's explicit override of the prior Akhil-era .ai-only directive. All Step 4 / Step 7 / "What NOT to Do" references updated. Apollo email account ID for `.com` sender = `68e3b53ceaaf74001d36c206`. The .ai account (`69d3b43d5821320021612c00`) is still active and can be re-selected if the rule reverts.

> **⚠️ AGENT: Always read this file fresh each session. The JS workflow is updated after each incident or confirmed improvement. Never rely on a cached or summarized version of this playbook.**

## Why This Exists
The Factor-First Outbound - Rob Gorham sequence Step 1 and Step 2 email steps are permanently deactivated. Apollo's task queue sends the sequence template body regardless of any Quill editor injection. Seven incidents (INC-007/008/012/015/016/017/018) all had the same root cause. The fix: bypass the task queue entirely and send manually from each contact's Apollo profile.

---

## Pre-Send Setup (once per session)

1. **Read the approved batch JSON** — `batches/sends-json/t1-drafts-mar24.json` (or the active batch file). Know who is queued, in what order.
2. **Check DNC list** — `CLAUDE.md` → "Do Not Contact List." Skip any contact who appears there.
3. **Check MASTER_SENT_LIST.csv** — confirm the contact has not already been sent.
4. **Confirm APPROVE SEND** — Rob must have given APPROVE SEND for the batch before any sends begin.
5. Open Rob's **work Chrome profile** (blue/Testsigma profile). Never use the personal red profile.

---

## Per-Contact Send Protocol

### Step 1 — Navigate to Contact Profile
- Go to `app.apollo.io` → search for the contact by name + company
- OR navigate directly via Apollo contact URL if known
- Open their **Activity** tab first — verify no existing T1 send, no opt-out, no reply

### Step 2 — Verify Contact Status
- Confirm email address matches what's in the approved draft
- Confirm the contact is NOT on the DNC list
- If any bounce, opt-out, or prior contact exists: STOP. Do not send. Flag to Rob.

### Step 3 — Open Send Email Composer
- Click **"Send Email"** button on the contact's profile (NOT from the sequence task queue)
- Composer opens as a standalone email, NOT tied to the sequence template

### Step 4 — Set From Address
- **Always verify From field = `robert.gorham@testsigma.com`** (effective Apr 29, 2026 — Rob override)
- Apollo defaults to `testsigma.in`. If any other sender appears, change it before proceeding via the React fiber `selectValue` method below.

### Step 5 — Enter Subject
- Copy the personalized subject from the approved batch JSON
- Type or paste into the Subject field
- Do NOT use Apollo's auto-suggested subject

### Step 6 — Enter Body
- Set clipboard to the full approved body text (Windows MCP Clipboard tool, or PowerShell here-string)
- Click into the body field
- Ctrl+A to select all → Ctrl+V to paste
- **Verify the body looks correct** — read first 2-3 lines in the compose window
- Body must end with: "Cheers," + full signature block:
  ```
  Robert Gorham - BDR
  Robert.gorham@testsigma.com
  www.testsigma.com
  ```
  (Apollo's "Include signature" checkbox auto-appends the standard signature block. Body content just needs to end with the casual close — e.g. "Cheers," or "have a good day, Rob".)

### Step 7 — Pre-Send Verification (MANDATORY — cannot be skipped)
Take a Windows MCP snapshot and confirm all three:
- [ ] **From:** `robert.gorham@testsigma.com` (effective Apr 29, 2026 — Rob override)
- [ ] **Subject:** matches approved subject (personalized, NOT template)
- [ ] **Body:** starts with "Hi [FirstName]," — NOT "Placeholder"

If any check fails: STOP. Do not send. Fix the issue and re-verify.

### Step 8 — Send
- Click **Send** (or Send Now)
- This sends a standalone email from Rob's account — NOT through the sequence

### Step 9 — Post-Send Gmail Verification (within 60 seconds)
- Use `gmail_search_messages` to find the sent email in Gmail Sent folder
- Confirm: recipient name, subject, and body snippet match the approved draft
- If body shows "Placeholder": **HALT ALL SENDS immediately.** Log as new incident.
- If send confirmed correct: log it

### Step 10 — Log the Send
- Update MASTER_SENT_LIST.csv: name, batch, date, "Email (Apollo Manual - TAM Outbound T1)", 0, filename, norm
- Update the batch tracker HTML: change status from "Draft Ready" → "T1 Sent [date]"
- Note: T2 due date = T1 sent date + 4 days minimum (Day 4 gate)

---

## T2 Manual Send Notes

Because the sequence email steps are deactivated, T2s also require manual sends.

- T2 must be sent as a **reply to the T1 thread** — find the original sent email in Gmail, reply from there
- T2 subject must start with **"RE:"**
- T2 body from the approved T2 draft (once written)
- Same verification steps as T1 (From, Subject, Body, Gmail confirm)
- T2 timing: Day 4 minimum after T1 send (Day 5 is ideal)

---

## Tracking Note
Since Apollo sequence email steps are deactivated, Apollo will not auto-record these sends in the sequence activity log. All tracking lives in:
- `MASTER_SENT_LIST.csv` — source of truth for all sends
- Batch tracker HTML files in `batches/active/` — per-contact status
- Gmail Sent folder — confirmation record

---

---

## Full JS-Only Apollo Send Workflow (v2.0 — Confirmed Working Apr 8, 2026 — Batch 23, 8/8 sends)

This is the authoritative send method for Apollo contact profile pages. All interaction is via JavaScript through the Chrome extension (`mcp__Claude_in_Chrome__javascript_tool`). No coordinate-based clicks, no Windows MCP, no screenshot targeting.

**Confirmed working:** Batch 23 (Apr 8, 2026) — 8 sends, all `send_now` API returned 200, all composers closed on success. Jeb Watkins, Ying Gan, Sunil Erramsetty, Carolyn Gaudette, Joi Hepler, Robert Peworchik, Jignesh Pandya, Tommy Ho.

---

### Pre-Session Setup (run once before the first send)

**1. Ensure work Chrome is connected**

Use `mcp__Claude_in_Chrome__switch_browser` at session start to connect to the work (blue/Testsigma) Chrome profile. Do NOT use the red/personal profile.

```
switch_browser → connect to "work"
```

**2. Create a clean tab**

Use `mcp__Claude_in_Chrome__tabs_context_mcp` with `createIfEmpty: true`. This creates a new tab in the current MCP group.

```
tabs_context_mcp(createIfEmpty: true) → note the new tabId
```

**⚠️ Do NOT reuse a tab from a previous session context.** Old tab IDs expire when the context window resets. Always call `tabs_context_mcp` at the start of each session to get a valid current tabId.

**3. Verify Apollo session is active**

Navigate to Apollo and confirm you land on the app (not the login page):
```javascript
// After navigate to https://app.apollo.io/
document.title  // Should be "Apollo" or a contact name — NOT "Login - Apollo"
```
If login page appears: stop and tell Rob. The session expired. Rob needs to re-authenticate in the work Chrome window.

---

### Per-Contact Send Sequence (repeat for each contact)

**Step 1 — Navigate to contact profile**
```javascript
// Use mcp__Claude_in_Chrome__navigate:
// url: https://app.apollo.io/#/contacts/[APOLLO_CONTACT_ID]
// tabId: [current tabId]
```
Wait for navigation to complete. Then verify:
```javascript
({ title: document.title, sendEmailBtn: !!document.querySelector('button[aria-label="Send email"]') })
```
Expected: `title` = "[Contact Name] - Apollo", `sendEmailBtn` = true.

If page title is still the previous contact: call `window.location.reload()` — React SPA hash navigation sometimes doesn't update content.

**Step 2 — Set up fetch interceptor (do this once, before first send in the session)**
```javascript
window._apiCalls = [];
const origFetch = window._origFetch || window.fetch;
window._origFetch = origFetch;
window.fetch = function(...args) {
  const url = args[0]?.toString() || '';
  const entry = { url, time: Date.now(), method: args[1]?.method || 'GET' };
  window._apiCalls.push(entry);
  return origFetch.apply(this, args).then(res => { entry.status = res.status; return res; });
};
'interceptor active'
```

**Step 3 — Open the Send Email composer**
```javascript
document.querySelector('button[aria-label="Send email"]').click();
'compose opened'
```
Wait ~300ms, then verify:
```javascript
({ qlEditorExists: !!document.querySelector('.ql-editor'), selectCount: document.querySelectorAll('.Select').length })
```
Expected: `qlEditorExists` = true, `selectCount` = 3.

**Step 4 — Set From to testsigma.com (React fiber method) — UPDATED Apr 29, 2026**

Apollo defaults to `testsigma.in` or another address. Always override. Note: `.Select` index in the composer is not consistent across Apollo UI versions (sometimes the From dropdown is index 0, sometimes 1). Search for the .Select that contains "robert.gorham" rather than hardcoding an index:

```javascript
const selects = document.querySelectorAll('.Select');
let fromSelect = null;
for (const s of selects) {
  const v = s.querySelector('.Select-value')?.textContent?.trim() || '';
  if (v.includes('robert.gorham')) { fromSelect = s; break; }
}
const control = fromSelect.querySelector('.Select-control');
let fiber = control[Object.keys(control).find(k => k.startsWith('__reactFiber') || k.startsWith('__reactInternalInstance'))];
let selectInstance = null;
for (let i = 0; i < 30 && fiber; i++) {
  if (fiber.stateNode && typeof fiber.stateNode.selectValue === 'function') { selectInstance = fiber.stateNode; break; }
  fiber = fiber.return;
}
const comOpt = (selectInstance.props.options || []).find(o => (o.label || o.value || '').toString().includes('robert.gorham@testsigma.com'));
selectInstance.selectValue(comOpt);

// Verify
fromSelect.querySelector('.Select-value')?.textContent?.trim()?.substring(0, 60)
```
Expected result: `"You <robert.gorham@testsigma.com>"`. If not: retry once. If still wrong: STOP and tell Rob.

**If Rob ever reverts to .ai:** swap the `comOpt` filter from `'robert.gorham@testsigma.com'` to `'robert.gorham@testsigma.ai'` and update the verification expected value accordingly.

**Step 5 — Inject subject line (React native setter — required)**

⚠️ **Do NOT use `execCommand` for the subject input.** Apollo's subject field is a React-controlled component. `execCommand` writes to the DOM but doesn't update React state, so the subject never registers. Use the native setter:

```javascript
const subjectInput = document.querySelector('input[placeholder*="Subject"], input[name="subject"]');
const nativeSetter = Object.getOwnPropertyDescriptor(window.HTMLInputElement.prototype, 'value').set;
nativeSetter.call(subjectInput, "YOUR APPROVED SUBJECT HERE");
subjectInput.dispatchEvent(new Event('input', { bubbles: true }));
subjectInput.dispatchEvent(new Event('change', { bubbles: true }));

subjectInput.value  // Verify: should return the full subject
```

**Step 6 — Inject body (Quill execCommand method — the only authorized method)**

⚠️ **Do NOT use Quill API methods** (dangerouslyPasteHTML, setText, setContents, clipboard.convert) — these cause incidents. `execCommand('insertText')` is the only authorized method:

```javascript
const bodyText = `Hi [First],

[Full approved email body]

Cheers,`;

const e = document.querySelector('.ql-editor');
e.focus();
document.execCommand('selectAll', false, null);
document.execCommand('insertText', false, bodyText);

({ bodyLength: e.innerText.length, bodyStart: e.innerText.substring(0, 60) })
```
Expected: `bodyLength` > 200, `bodyStart` starts with "Hi [First]," — NOT "Placeholder" and NOT empty.

**Step 7 — Pre-send verification**

Run this before clicking Send Now:
```javascript
({
  from: document.querySelectorAll('.Select')[1]?.querySelector('.Select-value')?.textContent?.trim()?.substring(0, 50),
  subject: document.querySelector('input[placeholder*="Subject"], input[name="subject"]')?.value,
  bodyStart: document.querySelector('.ql-editor')?.innerText?.substring(0, 80),
  sendNowFound: !!Array.from(document.querySelectorAll('button')).find(b => b.textContent.trim() === 'Send Now'),
  sendNowDisabled: Array.from(document.querySelectorAll('button')).find(b => b.textContent.trim() === 'Send Now')?.disabled
})
```
**All four must pass:**
- `from` = `"You <robert.gorham@testsigma.com>"` ✓ (effective Apr 29, 2026 — Rob override)
- `subject` = exact approved subject (not empty, not template) ✓
- `bodyStart` = starts with "Hi [FirstName]," ✓
- `sendNowDisabled` = false ✓

If any check fails: STOP. Fix and re-verify before proceeding.

**Step 8 — Click Send Now and verify via fetch interceptor**
```javascript
window._apiCalls = [];  // Reset log
const sendNowBtn = Array.from(document.querySelectorAll('button')).find(b => b.textContent.trim() === 'Send Now');
sendNowBtn.click();
'Send Now clicked'
```

Wait ~1-2 seconds, then check:
```javascript
({
  apiCalls: window._apiCalls.map(c => ({ url: c.url.substring(0, 80), status: c.status, method: c.method })),
  composeStillOpen: !!document.querySelector('.ql-editor')
})
```

**Send success indicators (all three should be true):**
- A `POST` to `/api/v1/emailer_messages/[id]/send_now` with `status: 200`
- A `PUT` to `/api/v1/emailer_messages/[id]` with `status: 200`
- `composeStillOpen: false` (composer closed)

**Send failure indicators:**
- `window._apiCalls` is empty after 3 seconds → button click did not register
- `send_now` call returns non-200 → API error
- `composeStillOpen: true` after 5 seconds and no 200 from `send_now` → send did not fire

If send fails: do NOT retry blindly. Check the API response body for an error message. Common causes: Apollo session expired, contact owned by another rep (permission error), email address invalid. Stop and investigate before retrying.

**Step 9 — Log the send and move to next contact**

After each confirmed send:
- Note the emailer_message_id from the API call (for audit trail)
- The contact is sent; proceed to the next contact in the batch
- After all sends complete: update MASTER_SENT_LIST.csv, update batch tracker HTML

---

## Resuming a Mid-Batch Send Across Context Window Transitions

When a session runs out of context mid-batch, the next session must pick up exactly where it left off. Follow this recovery protocol:

### Recovery Steps

1. **Read session summary** — the compact summary at conversation start tells you exactly which contacts were sent and which are pending. Trust it.

2. **Read the sends JSON** — `batches/sends-json/[batch_file].json` for the full body/subject of each pending contact. This is the ground truth for draft content.

3. **Cross-check MASTER_SENT_LIST.csv** — grep for the batch name to see which contacts are already logged as sent. Compare against the JSON to identify the remaining queue.

4. **Get current tab context** — call `tabs_context_mcp` to see what tab is open. If an Apollo contact profile is already loaded, that contact may be mid-send. Check if composer is open via JS.

5. **Resume the queue** — work through remaining contacts sequentially using the JS-only workflow above. No need to re-verify From/Subject/Body logic — APPROVE SEND was already given for the batch.

6. **Log all sends in MASTER_SENT_LIST.csv** — append all sends at end of session (or after each send if the batch is large and you're worried about another context window cut).

### Handoff Data Structure for Send Batches

Before ending any session mid-send, the handoff.md must capture:
- Which contacts were sent (✅)
- Which contacts are still pending (⏳)
- The batch name and JSON file path
- APPROVE SEND status (so next session doesn't re-ask Rob)

---

## Inbound Lead Manual Sends (Added Apr 6, 2026)

The same manual send process applies to inbound leads. Additional notes:

- **Source:** Inbound leads are enrolled in the "Inbound Leads - Rob Gorham" sequence (`69b2ae589d6bd10017d4be89`), NOT the Factor-First Outbound sequence.
- **Formula:** Inbound T1s use a different email formula than TAM outbound. See `memory/playbooks/inbound-leads-sequence.md` Part 4 for the locked inbound formula, intent tiers, and examples.
- **Approval process:** Rob prefers one-by-one APPROVE CLICK for inbound — compose each email in Apollo, screenshot for Rob's review, Rob approves, then send. Repeat for each contact.
- **Write with AI panel:** Apollo auto-opens this panel every time the composer loads. It steals focus from the Quill editor. ALWAYS use JS injection (execCommand method) to enter body text — never type directly, as keystrokes may go to the AI panel instead.
- **From address default:** Apollo defaults to testsigma.in. MUST change to testsigma.ai via the From dropdown every time. Use `find` tool to locate the dropdown by reference.
- **Body injection (safe method):**
  ```javascript
  const e = document.querySelector('.ql-editor');
  e.focus();
  document.execCommand('selectAll', false, null);
  document.execCommand('insertText', false, bodyText);
  ```
- **JS readback verification:**
  ```javascript
  document.querySelector('.ql-editor').innerText
  ```
- **Send button:** Use `find` tool to locate "Send Now button" by reference and click by ref. Coordinate-based clicks may miss due to the Write with AI panel overlay.

---

## Session Keep-Alive Protocol (Added Apr 13, 2026 — INC-023)

Apollo sessions expire silently after extended inactivity on the SPA. When this happens mid-send, the tab crashes and `tabs_context_mcp` returns the login page. To prevent this:

### Every 10 Contacts — Session Health Check (MANDATORY)

After every 10th send (contacts 10, 20, 30, 40, etc.), run this lightweight check BEFORE navigating to the next contact:

```javascript
({
  title: document.title,
  loginPage: document.title.includes('Login'),
  apolloApp: document.title.includes('Apollo') || document.title.includes(' - Apollo'),
  url: window.location.href.substring(0, 60)
})
```

**If `loginPage: true` or URL shows login page:**
1. STOP all sends immediately
2. Do NOT attempt to navigate to the next contact (this will crash the tab)
3. Alert Rob: "Apollo session expired. Please re-authenticate in work Chrome, then tell me to resume."
4. Log which contact is next in the queue so the session can resume cleanly

**If `apolloApp: true` and `loginPage: false`:** Session is healthy, continue sends.

### Tab Health Check — Before Every Navigate

Before calling `mcp__Claude_in_Chrome__navigate` for each contact, verify the tab still exists:

```javascript
document.title
```

If this call fails or returns an error about the tab not existing, the tab has crashed. Recovery:
1. Call `tabs_context_mcp(createIfEmpty: true)` to get a fresh tab
2. Check if Apollo login page appears
3. If login page: STOP and alert Rob for re-authentication
4. If Apollo app loads: re-install the fetch interceptor and resume from the next unsent contact

### Why This Exists
INC-023 (Apr 13, 2026): After sending 48 T2 emails successfully, the Apollo tab crashed when attempting contact #49. The session had expired silently during the ~45-minute send loop. The tab ID became invalid, and the next navigate attempt failed with "Tab no longer exists." No data was lost (contact #49 had not been sent), but the entire remaining queue (35 contacts) was blocked until Rob could re-authenticate.

---

## Quick Reference: What NOT to Do
- ❌ Do NOT open Apollo task queue for email tasks — email steps are deactivated
- ❌ Do NOT inject into the Quill editor via JS API (dangerouslyPasteHTML, setText, setContents) — only execCommand is safe
- ❌ Do NOT type body text directly — Write with AI panel may steal focus
- ❌ Do NOT send from rgorham369@gmail.com — work account only
- ❌ Do NOT skip the pre-send verification (Step 7)
- ❌ Do NOT send if body shows any variation of "Placeholder"
- ❌ Do NOT assume From address is correct — always verify `testsigma.com` (effective Apr 29, 2026)
