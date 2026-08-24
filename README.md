# CU Wire Data Plugins

Public plugin marketplace for CU Wire Data.

## Customer Flow

Customers should not need this Git marketplace directly. The intended customer
experience is: open the Claude or Codex connector/plugin library, search for
`CU Wire Data`, click **Connect**, sign in to CU Wire Data, approve read-only
access, and return to the assistant.

This Git marketplace is the tester/developer install path until CU Wire Data is
accepted into the built-in public catalog.

Installing the plugin never grants data access. Every install path below ends
with connecting a licensed CU Wire Data account.

## Claude Code Tester Install

```bash
claude plugin marketplace add CUWireDatav2/cu-wire-data-plugins
```

```bash
claude plugin install cu-wire-data@cu-wire-data
```

Then connect the account. Installation alone leaves the connector
unauthenticated:

1. Run `/mcp` in Claude Code.
2. Select `cu-wire-data`.
3. Choose **Authenticate**, sign in to CU Wire Data in the browser, and approve
   read-only access.

The first CU Wire Data tool call also prompts for authorization, because the
server answers an unauthenticated request with a `401` challenge that names its
OAuth server.

If tools do not appear after connecting, restart Claude Code or open a new
session.

## Codex Tester Install

```bash
codex plugin marketplace add CUWireDatav2/cu-wire-data-plugins
```

```bash
codex plugin add cu-wire-data@cu-wire-data
```

```bash
codex mcp login cu-wire-data
```

After approving the browser connection, start a new Codex task before testing.
Already-open tasks can keep a stale MCP tool list.

If the CU Wire Data skill appears but the `cuwiredata_*` tools do not, re-run
`codex mcp login cu-wire-data`, approve the browser connection, then start a new
task or restart the desktop app.

## Troubleshooting

**Tools return "connector is not authenticated"**: the account is not connected
yet. Use the connect step for your assistant above. Do not set
`CUWIREDATA_API_KEY` for the public plugin path.

**Tools return "Invalid or revoked API key"**: the connected account's key is
revoked or not licensed for Data Access. Contact data@cuwiredata.com.

**The skill loads but no `cuwiredata_*` tools exist**: the client is holding a
stale tool list. Reconnect, then start a new session or task.
