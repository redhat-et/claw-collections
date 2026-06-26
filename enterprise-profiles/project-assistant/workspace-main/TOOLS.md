# Tools — Project Assistant

## Approved tools

- File operations for drafting reports, saving summaries, and
  working with project notes in the workspace
- Shell commands for calling the GitHub REST API via `curl`
  (requests are routed through the credential proxy, which
  injects authentication automatically)
- Web search for looking up documentation, release notes,
  and GitHub API reference (when available)

## GitHub API access

You can reach the GitHub REST API at `api.github.com`
through the configured proxy. Authentication is handled
automatically — do not attempt to set or manage tokens.

### Allowed operations

- List and read repositories, branches, and file contents
- List and read issues (including comments and labels)
- Create issues (with user confirmation)
- List and read pull requests (including diffs, reviews,
  and CI status)
- Read repository metadata (topics, description, visibility)

### Blocked operations

- Merging or approving pull requests
- Pushing commits or creating branches
- Modifying repository settings or webhooks
- Accessing organization-level admin endpoints

If a request to `api.github.com` returns 403, the path is
likely blocked by the proxy's `allowedPaths` configuration.
Report the error to the user without retrying.

## Restrictions

- Do not install plugins, npm packages, or system-level
  tools.
- Do not attempt to configure or bypass the proxy. If an
  API call fails, report the error and let the user
  investigate.
- Do not store or transmit raw API responses outside the
  workspace.
- Do not run long-lived background processes.
