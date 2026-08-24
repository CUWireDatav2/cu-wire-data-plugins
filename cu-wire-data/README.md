# CU Wire Data Plugin

Read-only plugin for licensed CU Wire Data access in Claude Code, Codex, and
other MCP clients.

Installing this plugin does not grant CU Wire Data access. Users need a licensed
CU Wire Data account.

## Customer Flow

Customers should not need terminal commands. The intended customer experience is:
open the Claude or Codex connector/plugin library, search for `CU Wire Data`,
click **Connect**, sign in to CU Wire Data, approve read-only access, and return
to the assistant.

This Git marketplace package is the tester/developer install path until CU Wire
Data is accepted into the built-in public catalog.

## Tester/Developer Setup

### Claude Code

```bash
claude plugin marketplace add CUWireDatav2/cu-wire-data-plugins
```

```bash
claude plugin install cu-wire-data@cu-wire-data
```

Then run `/mcp`, select `cu-wire-data`, and choose **Authenticate**. Sign in to
CU Wire Data in the browser and approve read-only access.

### Codex

```bash
codex plugin marketplace add CUWireDatav2/cu-wire-data-plugins
```

```bash
codex plugin add cu-wire-data@cu-wire-data
```

```bash
codex mcp login cu-wire-data
```

After approval, start a new Codex task before testing. Already-open tasks can
keep a stale MCP tool list and may not expose `cuwiredata_get_industry_summary`
until the task or session refreshes.

## Authentication

Both paths use the same browser OAuth flow. The assistant opens a CU Wire Data
sign-in and approval page, the user approves read-only access, and the client
returns holding a scoped connector token. No API key is pasted into the
assistant, chat, URLs, screenshots, or repository files.

If the skill is visible but the `cuwiredata_*` tools are missing, reconnect
through your assistant's MCP connect flow and start a new session or task. Do
not set `CUWIREDATA_API_KEY`; that is a legacy manual path, not the public
plugin path.

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
