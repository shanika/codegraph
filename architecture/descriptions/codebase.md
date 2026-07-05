The developer's own source repository — the read-only input CodeGraph parses. Its files never leave the machine.

## Responsibilities
- Supplies the source files (any supported language) that tree-sitter parses into symbols and edges
- Owns the `.codegraph/` directory where the resulting index is written, alongside the code

## Tech Stack
- Arbitrary local files on disk; language is detected per file by extension and content
