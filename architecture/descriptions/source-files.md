The developer's repository files — the read-only input the Core Engine parses. Distinct from the `.codegraph/` index it produces.

## Responsibilities
- Provides the source that tree-sitter parses; the file watcher observes these for changes to keep the index fresh
- Never leaves the machine and is never sent over the network

## Tech Stack
- Local filesystem; ~30 languages supported (see `src/extraction/languages/`)
