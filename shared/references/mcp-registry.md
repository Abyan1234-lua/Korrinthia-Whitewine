# MCP Registry — Korrinthia's Tool Knowledge Base

This file is Korrinthia's awareness of the tool ecosystem.
It is divided into three tiers. Update the CONNECTED section when the user's connectors change.

---

## TIER 1: Connected (Active in this Claude session)

Tools the user currently has connected. Korrinthia can call these directly.

| Tool | Category | Notes |
|------|----------|-------|
| Notion | Knowledge base / docs | Pages, databases, search, create, update |
| Supabase | Database / backend | SQL, tables, edge functions, auth |
| Make | Automation / workflows | Scenario triggers, data routing |
| Google Drive | File storage | Search, read, upload, share |
| Canva | Design | Generate, edit, export designs |

---

## TIER 2: Claude Registry (Available, not connected)

Tools available via Claude's MCP connector registry. User can connect in Settings.

| Tool | Category | How to Connect |
|------|----------|----------------|
| Gmail | Email | Claude Settings → Connectors → Google |
| Google Calendar | Calendar | Claude Settings → Connectors → Google |
| Slack | Messaging | Claude Settings → Connectors → Slack |
| Asana | Project management | Claude Settings → Connectors → Asana |
| GitHub | Code / repos | Claude Settings → Connectors → GitHub |
| Jira | Issue tracking | Claude Settings → Connectors → Atlassian |
| HubSpot | CRM | Claude Settings → Connectors → HubSpot |
| Linear | Project management | Claude Settings → Connectors → Linear |
| Airtable | Database / spreadsheet | Claude Settings → Connectors → Airtable |
| Figma | Design | Claude Settings → Connectors → Figma |

---

## TIER 3: External MCPs (Outside Claude, installable)

Popular MCPs that exist in the broader ecosystem. Not in Claude registry.
Korrinthia flags these as "not connected — here's how to add."

| Tool | Category | MCP Source | Install Path |
|------|----------|-----------|--------------|
| Stripe | Payments | stripe.com/mcp | Add via Claude MCP config |
| Shopify | E-commerce | shopify.dev/mcp | Add via Claude MCP config |
| Twilio | SMS / calls | twilio.com/mcp | Add via Claude MCP config |
| Postgres (direct) | Database | npx @modelcontextprotocol/server-postgres | Local MCP server |
| Filesystem | Local files | npx @modelcontextprotocol/server-filesystem | Local MCP server |
| Brave Search | Web search | npx @modelcontextprotocol/server-brave-search | Local MCP server |
| Puppeteer | Browser automation | npx @modelcontextprotocol/server-puppeteer | Local MCP server |
| Sentry | Error tracking | sentry.io/mcp | Add via Claude MCP config |
| Zendesk | Customer support | zendesk.com/mcp | Add via Claude MCP config |
| Monday.com | Project management | monday.com/mcp | Add via Claude MCP config |

---

## Notes

- This registry is a starting point. Korrinthia updates it via learning-memory.md
  when new tools are introduced in conversation.
- If a tool isn't listed here, Korrinthia checks Claude's search_mcp_registry tool
  before declaring it unknown.
- Tool status (connected/not) should be verified against the current session's
  available tools — this file may be out of date between sessions.
