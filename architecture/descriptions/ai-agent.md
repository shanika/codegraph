An AI coding agent (Claude Code, Cursor, Codex CLI, opencode) that answers a developer's structural and flow questions by querying the CodeGraph knowledge graph instead of running its own grep-and-read loop.

## Responsibilities
- Calls the `codegraph_explore` MCP tool to fetch verbatim source plus call paths and blast-radius for the symbols it cares about
- Falls back to Read/Grep only when a CodeGraph answer is insufficient — so the graph's value is measured by how often it stops that fallback

## Tech Stack
- Connects to the MCP server over stdio JSON-RPC, configured by the CodeGraph installer
