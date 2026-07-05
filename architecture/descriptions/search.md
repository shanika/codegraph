Full-text symbol search — parses a query into an FTS5 expression and finds matching symbols by name.

## Responsibilities
- Parses natural-language / symbol-name queries into safe FTS5 `MATCH` expressions
- Locates the seed symbols that `codegraph_explore` and the context builder expand from

## Tech Stack
- SQLite FTS5; `src/search/` (query parser + helpers)
