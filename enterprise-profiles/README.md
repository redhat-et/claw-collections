# Enterprise Department Profiles

Pre-built workspace profiles for common enterprise roles. Each
profile includes persona files (SOUL.md, AGENTS.md, TOOLS.md),
identity, and role-specific skills. Designed for the
per-department deployment pattern where ITOps seeds tailored
assistants from a Git repo.

## Profiles

| Profile | Role | Scenario |
|---|---|---|
| `shared-team` | General software development team assistant | A |
| `standard-user` | Enterprise developer with restricted network | C |
| `hr-specialist` | HR policy, communications, onboarding | B |
| `financial-analyst` | Financial analysis, modeling, reporting | B |
| `executive-assistant` | Meeting prep, exec comms, strategic docs | B |
| `marketing-specialist` | Campaigns, content, messaging, performance | B |
| `project-assistant` | Cross-repo project planning with GitHub API access | — |

## Deployment

These profiles work with both operator-managed and user-managed
modes. Point a Claw CR at a profile directory:

### Shared team (Scenario A)

```yaml
apiVersion: claw.sandbox.redhat.com/v1alpha1
kind: Claw
metadata:
  name: dev-team
  namespace: ai-dev
spec:
  agentFiles:
    git:
      url: https://github.com/redhat-et/claw-collections.git
      ref: main
      path: enterprise-profiles/shared-team
  credentials:
    - name: anthropic
      provider: anthropic
      secretRef:
        - name: team-anthropic
          key: api-key
```

### Standard user (Scenario C)

```yaml
apiVersion: claw.sandbox.redhat.com/v1alpha1
kind: Claw
metadata:
  name: jane-doe
  namespace: ai-users
spec:
  agentFiles:
    git:
      url: https://github.com/redhat-et/claw-collections.git
      ref: main
      path: enterprise-profiles/standard-user
  credentials:
    - name: anthropic
      provider: anthropic
      secretRef:
        - name: jane-anthropic-key
          key: api-key
    - name: internal-npm
      type: none
      domain: npm.corp.internal
  network:
    builtinPassthroughs:
      - github.com
      - codeload.github.com
```

### HR Specialist

```yaml
apiVersion: claw.sandbox.redhat.com/v1alpha1
kind: Claw
metadata:
  name: hr-assistant
  namespace: ai-assistants
spec:
  agentFiles:
    git:
      url: https://github.com/redhat-et/claw-collections.git
      ref: main
      path: enterprise-profiles/hr-specialist
  credentials:
    - name: anthropic
      provider: anthropic
      secretRef:
        - name: shared-anthropic
          key: api-key
```

### Financial Analyst

```yaml
apiVersion: claw.sandbox.redhat.com/v1alpha1
kind: Claw
metadata:
  name: finance-assistant
  namespace: ai-finance
spec:
  agentFiles:
    git:
      url: https://github.com/redhat-et/claw-collections.git
      ref: main
      path: enterprise-profiles/financial-analyst
  credentials:
    - name: anthropic
      provider: anthropic
      secretRef:
        - name: shared-anthropic
          key: api-key
```

### Executive Assistant

```yaml
apiVersion: claw.sandbox.redhat.com/v1alpha1
kind: Claw
metadata:
  name: exec-assistant
  namespace: ai-executive
spec:
  agentFiles:
    git:
      url: https://github.com/redhat-et/claw-collections.git
      ref: main
      path: enterprise-profiles/executive-assistant
  credentials:
    - name: anthropic
      provider: anthropic
      secretRef:
        - name: shared-anthropic
          key: api-key
```

### Marketing Specialist

```yaml
apiVersion: claw.sandbox.redhat.com/v1alpha1
kind: Claw
metadata:
  name: marketing-assistant
  namespace: ai-marketing
spec:
  agentFiles:
    git:
      url: https://github.com/redhat-et/claw-collections.git
      ref: main
      path: enterprise-profiles/marketing-specialist
  credentials:
    - name: anthropic
      provider: anthropic
      secretRef:
        - name: shared-anthropic
          key: api-key
```

### Project Assistant (GitHub API)

```yaml
apiVersion: claw.sandbox.redhat.com/v1alpha1
kind: Claw
metadata:
  name: project-assistant
  namespace: ai-planning
spec:
  agentFiles:
    git:
      url: https://github.com/redhat-et/claw-collections.git
      ref: main
      path: enterprise-profiles/project-assistant
  credentials:
    - name: anthropic
      provider: anthropic
      secretRef:
        - name: anthropic-key
          key: api-key
    - name: github
      type: bearer
      domain: api.github.com
      secretRef:
        - name: github-pat
          key: token
      allowedPaths:
        - /repos/
        - /user
```

See the [GitHub-aware assistant][github-guide] walkthrough
for PAT creation and deployment details.

[github-guide]: https://github.com/redhat-et/claw-project/blob/main/docs/scenarios/github-api-assistant.md

## What happens on pod start

1. init-config clones the profile directory from this repo
2. `workspace-main/` is seeded into the workspace (SOUL.md,
   AGENTS.md, TOOLS.md, skills)
3. `openclaw.json` provides the agent name and model preference
4. In operator-managed mode (the default), the operator adds
   infrastructure skills (PLATFORM.md, KUBERNETES.md) on top
5. The operator's default AGENTS.md and SOUL.md use
   `seedIfMissing` — they do not overwrite the profile's
   versions

## Customization

These profiles are starting points. Common customizations:

- **Add `applyPolicy: Always`** to re-seed on every restart
  (for controlled environments where drift is unacceptable)
- **Add `restrictions.personaRef`** to lock SOUL.md read-only
  (prevents the agent from modifying its own constraints)
- **Change the model** in `openclaw.json` to match your
  available providers
- **Add MCP servers** on the Claw CR for domain-specific data
  access (e.g., an HR data API, financial data service)
