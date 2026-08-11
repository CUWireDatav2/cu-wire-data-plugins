# CU Wire Data Plugins

Public plugin marketplace for CU Wire Data.

## Codex

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

## Claude Code

```bash
claude plugin marketplace add CUWireDatav2/cu-wire-data-plugins
claude plugin install cu-wire-data@cu-wire-data
```

If tools do not appear immediately after installation or approval, restart
Claude Code or open a new session.
