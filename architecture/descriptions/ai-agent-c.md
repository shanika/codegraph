An AI coding agent that connects to the MCP server to query the graph. At the container level it enters the system through the MCP server, not the CLI.

## Responsibilities
- Opens a stdio MCP session and calls `codegraph_explore` to retrieve source, call paths, and blast-radius
- Treats returned source as already-Read to avoid redundant file reads

## Tech Stack
- MCP over stdio JSON-RPC
