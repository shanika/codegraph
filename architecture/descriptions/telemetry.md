The anonymous, opt-out usage-telemetry pipeline that CodeGraph sends events to — a first-party Cloudflare Worker at `telemetry.getcodegraph.com` that forwards to PostHog.

## Responsibilities
- Receives anonymous, sanitized usage events (per-machine id, rate-limited) so maintainers can see feature adoption
- Carries no source code, file contents, or personally identifying information

## Tech Stack
- Cloudflare Worker ingest → PostHog analytics; disabled entirely when the user opts out
