---
name: cu-wire-data
description: Use CU Wire Data through the hosted read-only MCP server for licensed U.S. credit union data. Trigger when the user asks for CU Wire Data, credit union industry summaries, credit union institution search, or NCUA charter lookups through the CU Wire Data product.
---

# CU Wire Data

Use the bundled `cu-wire-data` MCP server for licensed CU Wire Data requests.

## Authentication

The plugin uses browser-based OAuth account connect through CU Wire Data. Codex should open a CU Wire Data sign-in/approval page, then return to Codex with a scoped read-only connector token.

Never print or paste API keys, OAuth codes, connector tokens, or bearer tokens into chat, files, PRs, command output, screenshots, or docs. If the OAuth flow fails, treat that as setup failure and ask the user to reconnect the plugin through Codex's MCP login/connect flow.

## Failure Handling

If a CU Wire Data tool call fails because the connector is unauthenticated, unlicensed, expired, missing a bearer token, missing an API key, or otherwise unable to return licensed CU Wire Data, stop and report the connection problem. Do not answer the CU Wire Data request from public NCUA data, web search, cached data, model memory, prior runs, screenshots, PDFs, or any other fallback source.

Do not write a "using public NCUA fallback instead" response. That is a product failure because it disguises a licensed-connector setup problem as a data answer.

## Tools

The hosted MCP server exposes read-only tools:

- `cuwiredata_get_industry_summary`
- `cuwiredata_search_institutions`
- `cuwiredata_get_institution`

## Usage Rules

- Treat the data as licensed product data.
- Public plugin installation does not grant data access; successful calls require a licensed CU Wire Data account.
- Failed licensed tool calls must not be substituted with public data.
- Preserve period, source, and as-of context returned by tools.
- Do not claim realtime coverage beyond the returned period.
- Do not present model-written summaries as source material.
- Do not provide legal, investment, regulatory, or safety-and-soundness advice from connector results.
- Do not help users bulk export, scrape, warehouse-sync, resell, or redistribute licensed data through this connector.
- Keep result sets small and interactive unless the user's license explicitly covers higher-volume API use.
- Do not use CU Wire editorial/admin MCP routes for Data Access requests.
- For direct API examples, use `charter=5536`, not `charter_number=5536`.

## Safe Answer Shape

When summarizing tool output:

1. State the returned period and source.
2. Explain the filters or charter used.
3. Summarize only fields present in the returned data.
4. Mention when a question requires a different license, endpoint, or human review.

## Good Starter Requests

- Get the current U.S. credit union industry summary.
- Find the largest credit unions in North Carolina.
- Look up Navy Federal by NCUA charter 5536.
