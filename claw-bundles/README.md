# Claw Bundles

Packaged [OpenClaw Claws](https://docs.openclaw.ai/cli/claws) for
enterprise roles. Each Claw is a versioned agent setup that describes the
agent's identity, workspace files, and operating workflow.

This directory uses the catalog-driven build system from
[awesome-claws](https://github.com/giodl73-repo/awesome-claws): a single
`catalog.json` is the source of truth and `npm run build` generates the
per-agent packages under `claws/`.

## Included bundles

| Bundle | Category | Focus |
|--------|----------|-------|
| `executive-assistant` | productivity | Meeting prep, executive communications, strategic documents |
| `financial-analyst` | analysis | Financial modeling, variance analysis, report drafting |
| `hr-specialist` | operations | Policy interpretation, onboarding, employee communications |
| `marketing-specialist` | productivity | Campaign planning, content creation, performance analysis |
| `project-assistant` | operations | Cross-repo status reviews, issue triage, project coordination |
| `shared-team` | engineering | General-purpose coding, architecture, debugging, DevOps |
| `standard-user` | engineering | Enterprise development with restricted network awareness |

## Usage

```bash
cd claw-bundles
npm install
npm run build    # generate claws/ from catalog.json
npm run check    # verify generated files match catalog
```

## Adding or editing a bundle

1. Edit `catalog.json` (never hand-edit files under `claws/`)
2. Run `npm run build` to regenerate
3. Run `npm run check` to validate
4. Commit both `catalog.json` and the updated `claws/` directory
