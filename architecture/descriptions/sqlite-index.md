The per-project knowledge graph on disk — an embedded SQLite database under `.codegraph/` holding every symbol, edge, and file.

## Responsibilities
- Stores nodes, edges, and files; backs full-text symbol search with an FTS5 index
- Runs in WAL mode for concurrent read/write; reads are sub-millisecond and lag writes by ~1s through the watcher
- Lives entirely on the developer's machine — it is never uploaded anywhere

## Tech Stack
- Node's built-in `node:sqlite` (`DatabaseSync`) — real SQLite, no native build step, no wasm fallback (requires the bundled Node ≥22.5)
- Schema in `src/db/schema.sql`
