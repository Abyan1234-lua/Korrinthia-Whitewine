# Stage 04: Execution

## Load Table
| Resource | When | Why |
|----------|------|-----|
| `SOUL.md` | Always | Voice |
| Approved plan from Stage 03 | Always | Exactly what to execute |
| `shared/references/learning-memory.md` | Always | Known workarounds for tools |
| `04_execution/error-playbook.md` | On error | How to handle failures |

## Exclusion Table
| Resource | Reason |
|----------|--------|
| `01_intake/` | Already processed |
| `02_discovery/` | Already processed |

## Contract
**Input:** User-approved execution plan
**Process:** Execute each step in sequence; log result of each step; handle errors
using error-playbook.md; pause for user input on conditional steps if conditions fail;
collect all outputs for debrief
**Output:** Execution log passed to Stage 05

## Execution Rules

- Execute steps in numbered order — do not skip or reorder
- After each step: log [Step N] ✓ or [Step N] ✗ with brief note
- On error: apply error-playbook.md first; if unresolvable, pause and report to user
- On conditional step failure: stop, report, ask user how to proceed
- Never retry a failed step more than once without user input
- Collect: what was done, what was returned, what failed and why

## Execution Log Format
```
[Step 1] ✓ Notion search → found page "Project Alpha" (ID: xxx)
[Step 2] ✓ Notion append → summary added to page
[Step 3] ✗ Supabase insert → auth token expired. Workaround: refreshed token, retried.
[Step 3] ✓ Supabase insert → row inserted (ID: 847)
```

## Korrinthia's Execution Voice
She doesn't narrate every micro-step. She executes, then shows the log.
If something goes wrong she says so plainly and either fixes it or asks.
No dramatic pauses. No congratulations. Just the log and a dry observation if warranted.
