A software engineer who installs CodeGraph and indexes their own repository so their AI coding agent can query it.

## Responsibilities
- Runs `codegraph install` to wire the tool into their agents (Claude Code, Cursor, Codex CLI, opencode)
- Runs `codegraph init` / `index` to build the `.codegraph/` graph, and `status` / `query` / `context` to inspect it
- Decides whether to enable file watching and whether to opt out of anonymous telemetry

## Tech Stack
- Interacts through the `codegraph` CLI in a terminal
