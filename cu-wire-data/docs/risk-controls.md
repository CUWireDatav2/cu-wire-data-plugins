# CU Wire Data Codex Plugin Risk Controls

This plugin is public-installable but private-data-gated.

## Controls

- **Access**: Requires `CUWIREDATA_API_KEY`; no customer key is bundled.
- **Credential handling**: The plugin references `bearer_token_env_var`, so keys stay in the local environment.
- **Codex setup**: Codex must start with `CUWIREDATA_API_KEY` present; otherwise the HTTP MCP server is not initialized and the tools will not be exposed.
- **Scope**: Hosted MCP tools are read-only and limited to industry summary, institution search, and institution lookup.
- **Answering**: Skill instructions require period/source context and forbid realtime claims beyond returned data.
- **Redistribution**: Bulk export, resale, redistribution, and warehouse sync are outside the connector boundary.
- **Advice boundary**: The connector does not provide legal, investment, regulatory, or safety-and-soundness advice.

## Public Marketplace Language

Use:

> Install the CU Wire Data connector to query licensed, source-bound U.S. credit union data from Codex.

Avoid:

- "Free data access."
- "Realtime credit union intelligence."
- "Regulatory advice."
- "Bulk export through chat."
