Assembles the final answer an agent consumes — the verbatim source of the relevant symbols, the call path among them, and a blast-radius summary, formatted as markdown or JSON.

## Responsibilities
- Combines search hits with graph traversal (callers/callees/impact) into a single ranked, budgeted context
- Formats output for AI consumption, sizing what it returns to the repo so one call is usually sufficient to stop the agent from reading files

## Tech Stack
- `src/context/` (`ContextBuilder` + formatter); consumes the graph-query and search components
