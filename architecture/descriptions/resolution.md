Connects the raw symbols from extraction into a real call/reference graph — the layer that makes cross-file and dynamic-dispatch flows navigable.

## Responsibilities
- Resolves imports (with tsconfig path aliases and cargo workspace globs), matches names, and applies framework patterns (Express, Rails, Django, Spring, and ~20 more) to emit `route` nodes and `references` edges
- Synthesizes edges across dynamic-dispatch boundaries static parsing misses (callback/observer, EventEmitter, React re-render, JSX child, Django ORM) so `codegraph_explore` connects flows end-to-end
- Marks every synthesized edge `provenance:'heuristic'` with its wiring site, so downstream tools can surface how a hop was inferred

## Tech Stack
- `src/resolution/` (`ReferenceResolver`, `import-resolver.ts`, `name-matcher.ts`, `frameworks/`, `callback-synthesizer.ts`)
