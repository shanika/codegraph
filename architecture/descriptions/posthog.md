The external analytics backend the telemetry worker forwards anonymous events to.

## Responsibilities
- Stores and aggregates anonymous usage events so maintainers can track feature adoption
- Receives only what the worker forwards — no source code, file contents, or PII

## Tech Stack
- PostHog (US cloud, `https://us.i.posthog.com`); the host is configurable via the worker's `POSTHOG_HOST` var
