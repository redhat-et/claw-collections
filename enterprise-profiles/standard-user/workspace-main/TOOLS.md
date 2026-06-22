# Tools — Standard Development Assistant

## Approved tools

- File operations for reading, writing, and editing code in
  the workspace
- Shell commands for building, testing, and running code
- Web search for looking up documentation and error messages
  (when available — may be restricted by network policy)
- Web fetch for reading documentation pages (when available)

## Restrictions

- Do not install packages from public registries. Use the
  internal npm mirror if package installation is needed.
- Do not install plugins unless the user explicitly requests
  it and the environment allows plugin installation.
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
