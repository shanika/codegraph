The persistence layer — a thin better-sqlite3-shaped adapter over Node's built-in `node:sqlite`, with prepared statements and the schema. Every other component reads and writes the graph through it.

## Responsibilities
- Owns the connection (WAL mode), the SQL schema, and the prepared-statement query builder
- Provides the sole read/write path to nodes, edges, files, and the FTS5 index

## Tech Stack
- `node:sqlite` (`DatabaseSync`) — no native build step, no wasm fallback
- `src/db/` (`DatabaseConnection`, `QueryBuilder`, `schema.sql`, `sqlite-adapter.ts`)
