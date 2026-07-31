# Team development assistant

General-purpose coding assistant for a software development team covering code review, debugging, architecture, and DevOps.

**Best for:** Software development teams needing help with code, architecture decisions, debugging, documentation, and CI/CD.

## Example

**Request:** Review the PR for the new webhook handler and flag any error handling gaps or security concerns.

**Expected outcome:** A review summary listing changed files, identified gaps in error handling, potential security issues, and suggested improvements with rationale.

## Package contents

- `CLAW.md` defines the agent and provides its portable `SOUL.md` content.
- `workspace/AGENTS.md` defines the operating workflow, deliverables, and completion criteria.

Review the package before applying it. Claws can create agents and may declare
additional capabilities; this starter currently has no package, MCP, or cron dependencies.
