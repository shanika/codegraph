Turns source files into graph nodes and edges by parsing them with tree-sitter, one extractor per language.

## Responsibilities
- Detects language per file and parses it (heavy parsing runs on a worker-thread pool; recycled workers recover from WASM memory errors)
- Emits `NodeKind`/`EdgeKind` symbols via per-language extractors under `languages/`, plus standalone extractors for non-tree-sitter formats (Svelte, Vue, Liquid, Delphi DFM)
- Writes the extracted symbols to the DB layer in deterministic file order, and runs framework-specific passes (route nodes, etc.)

## Tech Stack
- `web-tree-sitter` + bundled grammar `.wasm`; `src/extraction/` (`ExtractionOrchestrator`, `parse-worker.ts`)
