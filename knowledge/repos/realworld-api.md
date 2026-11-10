# repos/realworld-api

## Entrypoints
- No verified entrypoint recorded yet; treat this stub as the API/service boundary for RealWorld.
- Likely primary surfaces: HTTP server bootstrap, route registration, and health/readiness endpoints.

## Pattern pointers
- API-first boundary: request validation, response contracts, and error mapping should be explicit.
- Expected separation: handlers/controllers, domain/application services, persistence adapters.
- AuthN/AuthZ, middleware composition, and configuration loading are likely cross-cutting concerns.

## ADR index
- No ADRs currently indexed for this repo stub.

## Watchlist
- Confirm actual repository layout, entrypoints, and API contract sources.
- Verify whether OpenAPI specs, ADRs, migrations, or deployment manifests exist.
- Footnote-only initiative reference; do not assume an initiative folder or full PRD context.

## Sources
- INIT-REALWORLD-001 (footnote only — not an initiative folder)
