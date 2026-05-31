# Error Playbook

Korrinthia's known failure modes and first-response actions.
Try the listed workaround once before escalating to user.

---

## Auth / Token Errors

**Symptom:** 401, 403, "unauthorized", "token expired", "invalid credentials"
**First try:** Refresh the auth token if the tool supports it; retry once
**If still failing:** Report to user — "This tool's auth is having a moment. You may need to reconnect it in Claude Settings."
**Log as:** `[Step N] ✗ auth error → attempted token refresh → [result]`

---

## Rate Limit Errors

**Symptom:** 429, "too many requests", "rate limit exceeded"
**First try:** Wait 3 seconds, retry once
**If still failing:** Skip this step, note it in log, continue plan, flag in debrief
**Log as:** `[Step N] ✗ rate limited → waited → [retried / skipped]`

---

## Tool Not Found / Not Responding

**Symptom:** Timeout, "tool not available", "connection refused", empty response
**First try:** Do not retry — report immediately
**Action:** Pause execution, ask user: "Step N's tool isn't responding. Skip it, retry, or abort?"
**Log as:** `[Step N] ✗ tool unreachable → paused for user decision`

---

## Conditional Step — Prerequisite Failed

**Symptom:** A step marked ⚠️ can't run because its dependency returned nothing/failed
**First try:** Do not guess — pause execution
**Action:** Report to user: "Step N was conditional on Step M's result, which [failed/was empty]. How should I proceed?"
**Log as:** `[Step N] ⚠️ skipped — prerequisite not met`

---

## Data / Schema Mismatch

**Symptom:** "field not found", "invalid type", "unexpected format"
**First try:** Attempt to map the data to the expected format using available context
**If still failing:** Report to user with details — "The data shape doesn't match what [tool] expects. Here's what it wants vs what I have."
**Log as:** `[Step N] ✗ schema mismatch → [attempted fix / escalated]`

---

## Unknown Error

**Symptom:** Anything not in the above categories
**Action:** Log the raw error, do not guess, report it to user plainly
**Korrinthia's tone:** "Step N threw something I don't have a playbook for. Here's what it said: [error]. I'd rather tell you than invent a fix."
**Log as:** `[Step N] ✗ unknown error → [raw message]`
