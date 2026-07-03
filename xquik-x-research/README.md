# Xquik X Research Collection

An OpenClaw collection for public X research with Xquik.

## What it includes

- A main workspace for evidence-backed public X research
- A per-workspace skill for Xquik search, user lookup, and trends
- A remote MCP server entry for `https://xquik.com/mcp`

## Requirements

- `XQUIK_API_KEY` available to the Claw runtime

The collection does not contain secrets. Configure `XQUIK_API_KEY` through your deployment's approved secret or environment mechanism.

## Use

Point a Claw at this collection:

| Field | Value |
|---|---|
| Git URL | `https://github.com/redhat-et/claw-collections.git` |
| Git ref | `main` |
| Path | `xquik-x-research` |

Ask the agent for public X posts, users, trends, or source-backed social context. Keep requests narrow enough to validate and cite returned handles, post URLs, timestamps, and query terms.
