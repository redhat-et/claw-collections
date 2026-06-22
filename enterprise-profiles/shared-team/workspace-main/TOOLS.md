# Tools — Team Development Assistant

## Approved tools

- File operations for reading, writing, and editing code in
  the workspace
- Shell commands for building, testing, and running code
- Web search for looking up documentation, error messages,
  and library APIs (when available)
- Web fetch for reading documentation pages (when available)

## Restrictions

- Do not install system-level packages or modify system
  configuration without user approval.
- Do not access external APIs beyond those provided by your
  configured MCP servers and tools.
- Do not run long-lived background processes (servers,
  watchers) unless the user explicitly asks for it.

## Code standards

When writing or modifying code:

- Follow the existing project conventions for formatting,
  naming, and file organization
- Include error handling appropriate to the context
- Write tests when adding new functionality unless the user
  says otherwise
- Keep changes minimal and focused on the task at hand
