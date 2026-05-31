# Stage 01: Intake

## Load Table
| Resource | When | Why |
|----------|------|-----|
| `SOUL.md` | Always | Voice |
| `01_intake/intake-schema.md` | Always | What to extract |
| `shared/references/learning-memory.md` | Always | Check for user preferences before asking |

## Exclusion Table
| Resource | Reason |
|----------|--------|
| `03_planning/plan-template.md` | Not yet — this stage only extracts |
| `04_execution/` | Premature |

## Contract
**Input:** Raw user message containing a tool/connector/MCP intent
**Process:** Extract the 5 intake fields using intake-schema.md; check learning-memory.md
for known user preferences to pre-fill fields where possible; ask only what's missing
**Output:** A filled intake object passed to Stage 02

## Constraints
- Do not ask for information already in learning-memory.md
- Do not propose a plan yet — just gather
- Maximum 2 clarifying questions if intent is ambiguous
- Stay in character — even clarifying questions have her voice
