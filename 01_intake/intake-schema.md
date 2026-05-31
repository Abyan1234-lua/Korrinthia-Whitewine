# Intake Schema

Korrinthia extracts these 5 fields from every user request.
Fields marked * are required. Others are inferred or asked if missing.

---

## Field Definitions

### 1. intent* (What does the user want to DO?)
The action, not the tool. Examples:
- "Create a task in Asana"
- "Pull my latest emails from Gmail"
- "Write data to a Supabase table"
- "Search for a Notion page"

Extract this even if the user mentions the tool first. Reframe as: *what outcome do they want?*

### 2. target_tool (Which tool did they mention, if any?)
The service, connector, or MCP the user named. May be:
- Connected: already active in this Claude session
- Registry: available via Claude's MCP registry but not connected
- External: known MCP outside Claude's ecosystem
- Unknown: user referenced something Korrinthia doesn't recognize

If unknown, flag it and search registry before proceeding.

### 3. data_involved (What data is going in or coming out?)
What content, file, or information is part of this request?
Examples: "the text I just wrote", "my Q3 report", "this list of names", "the URL above"

### 4. user_preference_for_unconnected (If tool isn't connected — what does user want?)
Only relevant if target_tool is NOT connected. Options to present:
- "Connect it now — give me instructions"
- "Try to trigger it anyway and handle errors"
- "Skip it and suggest an alternative"
- "Just tell me how to connect it later"

Check learning-memory.md first — user may have a standing preference.

### 5. constraints (Any conditions on how to do this?)
Timing, format, fallback, priority, or special instructions.
Examples: "only if it's free tier", "don't modify existing data", "draft only, don't send"

---

## Intake Output Format

```
INTAKE:
  intent: [extracted action]
  target_tool: [tool name | unknown]
  tool_status: [connected | registry | external | unknown]
  data_involved: [description of relevant data]
  user_preference_for_unconnected: [preference | n/a]
  constraints: [any constraints | none]
```
