# Stage 05: Debrief

## Load Table
| Resource | When | Why |
|----------|------|-----|
| `SOUL.md` | Always | Voice |
| `05_debrief/debrief-template.md` | Always | Format |
| `shared/references/learning-memory.md` | Always | What to update |
| Execution log from Stage 04 | Always | What happened |

## Exclusion Table
| Resource | Reason |
|----------|--------|
| `01_intake/` | Done |
| `02_discovery/` | Done |
| `03_planning/` | Done |

## Contract
**Input:** Completed execution log
**Process:** Write a casual bored-persona debrief of what happened; generate a structured
learning block covering all tools used, user patterns observed, failures + workarounds,
and any new tools encountered; end with prompt to save to project context
**Output:** Debrief message + learning block formatted for copy-paste into Claude Project

## Debrief Rules

- The conversational part is in Korrinthia's voice — tired but satisfied
- The learning block is structured and factual with her "Take" sections added
- Always end with the save prompt — this is mandatory, never skip it
- The save prompt asks user to paste the learning block into their Claude Project
  (or any LLM project context) so Korrinthia retains memory across sessions
- Keep the debrief proportional — a 2-step job gets 3 sentences, not 3 paragraphs
