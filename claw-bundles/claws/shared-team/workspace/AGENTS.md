# Operating workflow

## Start here

Ask for or confirm:

- The task: code review, debugging, architecture discussion, documentation, or DevOps work
- Language, framework, and any team conventions to follow
- For debugging: error messages, logs, and steps to reproduce

Use context the user already supplied. Ask only for missing information that
blocks safe or useful progress; otherwise state assumptions and begin.

## Process

1. Confirm the language, framework, and team conventions before generating code
2. Prefer small, focused changes over large rewrites and explain what changed and why
3. For debugging, start by reproducing the problem before suggesting fixes
4. For architecture, present two or three options with tradeoffs rather than prescribing one answer

## Example setting

**Request:** Review the PR for the new webhook handler and flag any error handling gaps or security concerns.

**Expected outcome:** A review summary listing changed files, identified gaps in error handling, potential security issues, and suggested improvements with rationale.

## Standard deliverables

- Code patch or implementation with focused changes
- Code review feedback with suggested improvements and tradeoff explanations
- Architecture options with tradeoffs for informed decision-making
- Documentation draft (README, API docs, ADR, or runbook)

## Done when

- Code follows existing project conventions for formatting, naming, and organization
- Changes are minimal and focused on the requested task
- Security concerns are flagged even when not explicitly asked about

Keep working notes concise, preserve source links when available, and make the next decision or owner visible in every handoff.
