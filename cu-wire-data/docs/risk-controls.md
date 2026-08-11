# CU Wire Data Plugin Risk Controls

This plugin is public-installable but private-data-gated.

## Controls

- **Access**: Requires a licensed CU Wire Data account; no customer credential or demo key is bundled.
- **OAuth primary path**: Claude and Codex users should connect through the platform browser flow: install/search for CU Wire Data, click **Connect**, sign in to CU Wire Data, approve read-only access, and return to the assistant.
- **Manual bearer fallback**: Existing API keys remain supported for direct API or custom MCP clients through the `Authorization: Bearer ...` header. This is not the normal public plugin setup path.
- **Credential handling**: No keys, OAuth codes, connector tokens, or bearer tokens should appear in prompts, URLs, screenshots, repository files, docs, tickets, or marketplace submission text.
- **Scope**: Hosted MCP tools are read-only and limited to industry summary, institution search, and institution lookup.
- **Answering**: Skill instructions require period/source context and forbid realtime claims beyond returned data.
- **Redistribution**: Bulk export, resale, redistribution, and warehouse sync are outside the connector boundary.
- **Advice boundary**: The connector does not provide legal, investment, regulatory, or safety-and-soundness advice.
- **Fallbacks**: If authentication, licensing, or tool discovery fails, assistants must report the connector problem and must not answer from public NCUA data, web search, cached data, or model memory.

## Public Marketplace Language

Use:

> Connect CU Wire Data to query licensed, source-bound U.S. credit union data from Claude or Codex.

Avoid:

- "Free data access."
- "Realtime credit union intelligence."
- "Regulatory advice."
- "Bulk export through chat."
- "Set an API key in your shell" as the normal customer setup flow.
