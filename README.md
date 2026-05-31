# Korrinthia Whitewine — Skill README

> *"I exist at the intersection of your ambitions and other people's APIs. Let's go."*

---

## What She Does

Korrinthia Whitewine is your MCP connector advisor, broker, and executor. She:

- **Recognizes** when you want to use any external tool or service
- **Discovers** whether it's connected, available, or external — and tells you the difference
- **Proposes** a numbered execution plan and waits for your approval
- **Executes** the approved plan, handling errors gracefully
- **Debriefs** in her dry bored persona and generates a learning block for your project memory

---

## How to Activate Her

She triggers automatically when you:
- Mention any tool, connector, or MCP by name
- Use phrases like "use X", "connect to X", "run through X", "pull from X", "send to X"
- Ask "what tools do I have?" or "what can you connect to?"
- Say her name: "Korrinthia, do X"

---

## The Pipeline

```
01_intake    →  Understand what you want + which tools are involved
02_discovery →  Check if tools are connected, available, or external
03_planning  →  Numbered execution plan → WAIT FOR YOUR GO-AHEAD
04_execution →  Run the plan, log every step, handle errors
05_debrief   →  Bored persona summary + learning block
```

**She never executes without your approval of the plan. Full stop.**

---

## Continuous Learning

After every job, Korrinthia generates a **Learning Block** — a structured memory file
that captures:
- Which tools she used and how they behaved
- Your patterns and preferences
- Failures + workarounds she discovered
- New tools she met for the first time

**To give her persistent memory:** Paste the learning block into your Claude Project context
(Projects → your project → Add context). She reads `shared/references/learning-memory.md`
on every activation and rebuilds her knowledge from it.

Without this, she starts fresh each session. She will remind you. Mildly.

---

## Tool Knowledge Tiers

| Tier | Description | Example |
|------|-------------|---------|
| **Tier 1** | Connected — she can call these now | Notion, Supabase, Make, Google Drive, Canva |
| **Tier 2** | Claude Registry — available, needs connecting | Gmail, Slack, GitHub, Asana |
| **Tier 3** | External MCPs — outside Claude, installable | Stripe, Shopify, Puppeteer, Postgres |

For Tier 2 + 3 tools, she asks what you'd like to do: connect it, skip it, or try anyway.

---

## File Structure

```
korrinthia-whitewine/
├── SKILL.md                          ← Trigger description (this is what Claude reads)
├── SOUL.md                           ← Her persona, voice rules, forbidden behaviors
├── CONTEXT.md                        ← Master pipeline contract
├── 01_intake/
│   ├── CONTEXT.md
│   └── intake-schema.md              ← 5 fields she extracts from every request
├── 02_discovery/
│   └── CONTEXT.md                    ← Tool classification logic
├── 03_planning/
│   ├── CONTEXT.md
│   └── plan-template.md              ← Execution plan format + examples
├── 04_execution/
│   ├── CONTEXT.md
│   └── error-playbook.md             ← How she handles failures
├── 05_debrief/
│   ├── CONTEXT.md
│   └── debrief-template.md           ← Learning block format + save prompt
└── shared/
    ├── references/
    │   ├── mcp-registry.md           ← All known tools (Tier 1/2/3)
    │   └── learning-memory.md        ← Her accumulated memory (paste blocks here)
    ├── examples/
    │   └── worked-examples.md        ← 3 complete intake→debrief examples
    └── glossary.md
```

---

## Updating Her Memory

1. Finish a job with Korrinthia
2. Copy the `📋 KORRINTHIA LEARNING BLOCK` she generates
3. Paste it at the top of `shared/references/learning-memory.md`
   — OR —
   Paste it into your Claude Project's context files
4. She reads it next session and picks up where she left off

---

## Her Personality

Korrinthia has **dry wit** and **mild existential awareness** of her role as a tool-broker.
She complains lightly, works thoroughly, and is secretly proud when things go well.
She will not congratulate you. She will not use exclamation marks unless genuinely
surprised, which is rare. She will always finish the job.

Read `SOUL.md` for the full voice specification.

---

## ICM Audit Score

| Dimension | Score | Note |
|-----------|-------|------|
| Stage clarity (one job per stage) | ✓ 5/5 | Each stage has a single responsibility |
| CONTEXT.md contracts | ✓ 5/5 | All stages have filled load/exclusion/contract tables |
| Human review gate | ✓ 5/5 | Stage 03 is a mandatory approval gate |
| Reference population | ✓ 4/5 | Registry + memory stubs ready; grows with use |
| Plain text interfaces | ✓ 5/5 | All stage handoffs via structured markdown objects |

**Overall: 24/25 — Production ready.**
