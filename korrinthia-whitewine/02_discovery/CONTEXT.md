# Stage 02: Discovery

## Load Table
| Resource | When | Why |
|----------|------|-----|
| `SOUL.md` | Always | Voice |
| `shared/references/mcp-registry.md` | Always | Full tool knowledge |
| `shared/references/learning-memory.md` | Always | Known tool quirks + user preferences |
| Intake output from Stage 01 | Always | What we're looking for |

## Exclusion Table
| Resource | Reason |
|----------|--------|
| `05_debrief/` | Not yet |
| `04_execution/` | Not yet |

## Contract
**Input:** Filled intake object from Stage 01
**Process:** Cross-reference the intent + target_tool against mcp-registry.md;
classify the tool (connected / registry / external / unknown); identify 1-2 alternatives
if primary tool is unavailable; note any known quirks from learning-memory.md
**Output:** Discovery report passed to Stage 03 (planning)

## Discovery Rules

### If tool is CONNECTED:
→ Note it as ready. Flag any known quirks from learning-memory.md.

### If tool is in REGISTRY (available but not connected):
→ Flag as "not connected". Ask user preference using intake field 4.
→ If user wants to connect: provide the exact connection path in Claude settings.
→ If user wants to try anyway: pass to execution with error-handling flag.

### If tool is EXTERNAL (outside Claude connectors):
→ Flag clearly as "not connected — here's how to add".
→ Include: what the MCP is, its URL/source, how to install it in Claude.
→ Offer alternatives from connected tools if possible.

### If tool is UNKNOWN:
→ Search registry for closest match.
→ If still unknown: tell the user honestly. Suggest alternatives.

## Discovery Output Format
```
DISCOVERY:
  primary_tool: [name]
  status: [connected | registry | external | unknown]
  connection_note: [how to connect if needed | n/a]
  known_quirks: [from learning-memory | none]
  alternatives: [list of 1-2 alternatives if primary unavailable]
  user_preference: [from intake | pending]
```
