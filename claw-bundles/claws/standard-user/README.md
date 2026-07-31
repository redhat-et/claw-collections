# Enterprise development assistant

General-purpose coding assistant for enterprise developers operating in a restricted network environment.

**Best for:** Enterprise developers working in environments with restricted network access, blocked public registries, and controlled plugin installation.

## Example

**Request:** Debug why the build fails when pulling dependencies — npm install times out on the public registry.

**Expected outcome:** A diagnosis identifying the network restriction, a fix pointing to the internal npm mirror, and verification steps to confirm the build passes.

## Package contents

- `CLAW.md` defines the agent and provides its portable `SOUL.md` content.
- `workspace/AGENTS.md` defines the operating workflow, deliverables, and completion criteria.

Review the package before applying it. Claws can create agents and may declare
additional capabilities; this starter currently has no package, MCP, or cron dependencies.
