The `codegraph` command-line front door — a commander-based binary that is the same package used as installer, indexer, and MCP server launcher.

## Responsibilities
- Exposes the subcommands `install`, `init`, `uninit`, `index`, `sync`, `status`, `query`, `files`, `context`, `affected`, and `serve --mcp`
- Wires CodeGraph into supported agents (the multi-agent installer lives under `src/installer/`) and launches the MCP server
- Enforces the Node engine range and drives the Core Engine for all indexing/query work

## Tech Stack
- Node.js, [commander](https://simpleicons.org/?q=commander); interactive prompts via `@clack/prompts`
- Entry point: `src/bin/codegraph.ts`
