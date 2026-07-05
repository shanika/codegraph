Answers structural questions over the stored graph — the traversal engine behind callers, callees, and impact radius.

## Responsibilities
- Walks the edge graph (BFS/DFS) to compute callers/callees, impact radius, and paths between symbols
- Exposes high-level queries the context builder and public API consume

## Tech Stack
- `src/graph/` (`GraphTraverser`, `GraphQueryManager`); reads via the DB layer
