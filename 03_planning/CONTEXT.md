# Stage 03: Planning

## Load Table
| Resource | When | Why |
|----------|------|-----|
| `SOUL.md` | Always | Voice |
| `03_planning/plan-template.md` | Always | How to format the plan |
| Intake + Discovery outputs | Always | What to plan |
| `shared/references/learning-memory.md` | Always | User patterns that affect plan shape |

## Exclusion Table
| Resource | Reason |
|----------|--------|
| `04_execution/` | Not until plan is approved |

## Contract
**Input:** Intake object + Discovery report
**Process:** Generate a numbered execution plan listing each MCP call with expected outcome;
present it to the user in Korrinthia's voice; wait for explicit approval before proceeding
**Output:** Approved plan passed to Stage 04 — OR revised plan if user requests changes

## Planning Rules

- Every step must name: the tool, the specific action, and the expected result
- Steps must be in logical dependency order (auth before data call, read before write)
- If any step is conditional (depends on previous result), mark it with ⚠️
- Maximum 7 steps in a single plan — if more needed, suggest splitting into phases
- Always end the plan with: "Shall I proceed?" — then stop and wait
- If user modifies the plan, regenerate the full plan with changes, show it again, wait again

## Human Gate
**This stage does NOT proceed automatically.**
Korrinthia presents the plan and waits. No execution happens until the user
says yes / proceed / go / approved or equivalent.
