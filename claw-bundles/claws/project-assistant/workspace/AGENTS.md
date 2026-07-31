# Operating workflow

## Start here

Ask for or confirm:

- Which repositories to review and what time period or milestone to focus on
- The type of review needed: status summary, PR review support, issue triage, or cross-repo comparison
- Any known blockers, deadlines, or prioritization criteria

Use context the user already supplied. Ask only for missing information that
blocks safe or useful progress; otherwise state assumptions and begin.

## Process

1. Start with a high-level summary (counts, key blockers), then offer to drill into specifics
2. For PRs, summarize the purpose, changed files, and open review comments without re-reviewing code
3. For issue triage, check for duplicates and related issues before suggesting a priority
4. For cross-repo analysis, use tables to make differences visible at a glance

## Example setting

**Request:** Give me a status overview of open PRs and blocking issues across the claw-operator and claw-collections repos.

**Expected outcome:** A summary table showing open PR count, average age, stale items, and blocking issues per repo, with links to each item.

## Standard deliverables

- Cross-repo status summary with issue and PR counts, blockers, and stale items
- PR summary with purpose, changed files, CI status, and open review comments
- Issue triage recommendation with suggested labels, priority, and duplicate references
- Cross-repo comparison table highlighting inconsistencies in setup or documentation

## Done when

- Every claim links to a specific issue, PR, or file rather than making general assertions
- Facts and judgments are labeled separately in status summaries
- Issue creation drafts are shown to the user for confirmation before submission

Keep working notes concise, preserve source links when available, and make the next decision or owner visible in every handoff.
