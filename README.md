# CU Wire Data Plugins

Public plugin marketplace for CU Wire Data.

## Customer Flow

Customers should not need this Git marketplace directly. The intended customer
experience is: open the Claude or Codex connector/plugin library, search for
`CU Wire Data`, click **Connect**, sign in to CU Wire Data, approve read-only
access, and return to the assistant.

This Git marketplace is the tester/developer install path until CU Wire Data is
accepted into the built-in public catalog.

## Codex Tester Install

```bash
codex plugin marketplace add CUWireDatav2/cu-wire-data-plugins
codex plugin add cu-wire-data@cu-wire-data
codex mcp login cu-wire-data
```

After approving the browser connection, start a new Codex task before testing.
Already-open tasks can keep a stale MCP tool list.

If the CU Wire Data skill appears but the `cuwiredata_*` tools do not, re-run
`codex mcp login cu-wire-data`, approve the browser connection, then start a new
task or restart the desktop app. Do not use `CUWIREDATA_API_KEY` for the public
plugin path.

## Claude Code Tester Install

```bash
claude plugin marketplace add CUWireDatav2/cu-wire-data-plugins
claude plugin install cu-wire-data@cu-wire-data
```

If tools do not appear immediately after installation or approval, restart
Claude Code or open a new session.
