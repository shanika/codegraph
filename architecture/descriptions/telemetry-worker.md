A first-party Cloudflare Worker (`telemetry.getcodegraph.com`) that ingests anonymous usage events from CLI/MCP runs and forwards them to PostHog. Separate deployable in the repo under `telemetry-worker/`.

## Responsibilities
- Accepts batched, sanitized events; enforces a per-machine-id rate limit (6/min) and bounded body/batch sizes
- Strips everything but anonymous fields, then forwards to PostHog's `/batch/` endpoint with the server-held API key

## Tech Stack
- Cloudflare Workers (`wrangler`), custom domain `telemetry.getcodegraph.com`; `telemetry-worker/src/index.ts`
- Config in `telemetry-worker/wrangler.jsonc`
