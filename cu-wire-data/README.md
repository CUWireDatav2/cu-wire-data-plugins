# CU Wire Data Codex Plugin

Read-only Codex plugin for licensed CU Wire Data access.

Installing this plugin does not grant CU Wire Data access. Users need a licensed CU Wire Data account.

## Setup

Install from the CU Wire Data marketplace:

```bash
codex plugin marketplace add CUWireDatav2/cu-wire-data-plugins
codex plugin add cu-wire-data@cu-wire-data
codex mcp login cu-wire-data
```

Connect the plugin through Codex's MCP OAuth flow. Codex opens a browser window
to CU Wire Data, the user signs in, approves read-only connector access, and
returns to Codex. No API key is pasted into Codex, chat, URLs, screenshots, or
repository files.

After approval, start a new Codex task before testing. Already-open tasks can
keep a stale MCP tool list and may not expose `cuwiredata_get_industry_summary`
until the task/session refreshes.

If the skill is visible but the `cuwiredata_*` tools are missing, do not set
`CUWIREDATA_API_KEY`. Re-run `codex mcp login cu-wire-data`, approve the browser
connection, then start a new task or restart the desktop app.

The plugin connects to:

```text
https://cu-wire-mcp.vercel.app/data-mcp
```

## Tools

- `cuwiredata_get_industry_summary`
- `cuwiredata_search_institutions`
- `cuwiredata_get_institution`

The plugin does not include customer credentials.

## Boundaries

- Read-only.
- No admin/editorial tools.
- No public/free default key.
- No keys in prompts, URLs, docs, tickets, screenshots, or repositories.
- No public NCUA, web, cached, model-memory, or other fallback answer when the licensed CU Wire Data connector is unauthenticated or fails.
- No bulk export, resale, redistribution, or warehouse sync through the connector.
- Assistant answers should preserve the returned period, as-of date, and source.
