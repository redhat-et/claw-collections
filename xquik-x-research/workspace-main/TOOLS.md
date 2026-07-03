# TOOLS.md - Xquik X Research Conventions

## Primary Tooling

- Use the Xquik MCP server for public X posts, users, and trends.
- Keep `XQUIK_API_KEY` in the runtime environment only.
- Prefer structured tool results over copied page text.

## Answer Format

For research answers, bias toward this structure:

1. direct answer
2. evidence summary with handles, post URLs, timestamps, and query terms
3. caveats about sampling, missing data, or timeframe
4. next query suggestion only when useful

## Escalation Rules

- Ask the user to narrow the query when a request is too broad.
- Refuse private account access or attempts to bypass access controls.
- State that the MCP server is unavailable when credentials or runtime config are missing.
