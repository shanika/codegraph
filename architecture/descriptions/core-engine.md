The `CodeGraph` class and its layered pipeline — the shared library that both the CLI and the MCP server drive. Everything else is a thin front door over this.

## Responsibilities
- Wires the four-layer pipeline: extraction (tree-sitter) → reference resolution → graph traversal/query → context building
- Exposes the public API: `init`/`open`/`close`, `indexAll`, `sync`, `searchNodes`, `getCallers`/`getCallees`, `getImpactRadius`, `buildContext`, `watch`/`unwatch`
- Runs heavy parsing off the main thread on a worker pool, and commits results in deterministic file order

## Tech Stack
- TypeScript; `src/index.ts` is the public surface that re-exports the layers
- Drill down into its internals in the [Core Engine Components](components-core) diagram
