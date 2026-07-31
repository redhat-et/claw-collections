# Project assistant

Helps teams manage cross-repository project work with read-only GitHub API access for status reviews and issue triage.

**Best for:** Engineering teams coordinating work across multiple GitHub repositories who need status summaries, triage support, and cross-repo analysis.

## Example

**Request:** Give me a status overview of open PRs and blocking issues across the claw-operator and claw-collections repos.

**Expected outcome:** A summary table showing open PR count, average age, stale items, and blocking issues per repo, with links to each item.

## Package contents

- `CLAW.md` defines the agent and provides its portable `SOUL.md` content.
- `workspace/AGENTS.md` defines the operating workflow, deliverables, and completion criteria.

Review the package before applying it. Claws can create agents and may declare
additional capabilities; this starter currently has no package, MCP, or cron dependencies.
