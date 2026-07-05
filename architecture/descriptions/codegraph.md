The local-first code intelligence system: it parses a codebase into a deterministic knowledge graph of symbols and edges, stores it in embedded SQLite, and serves it to developers (via CLI) and AI agents (via MCP).

## Responsibilities
- Index any supported language with tree-sitter and resolve references (imports, name-matching, framework routes, dynamic-dispatch synthesizers) into a queryable graph
- Answer callers/callees/impact/flow queries and build markdown/JSON context for AI consumption
- Keep the index fresh via an optional file watcher, and install itself into the developer's agents

## Tech Stack
- TypeScript on Node.js (≥20, runtime bundles ≥22.5), distributed as `@colbymchenry/codegraph` on npm
- Embedded `node:sqlite` (WAL + FTS5) — no backend service, no native build step
