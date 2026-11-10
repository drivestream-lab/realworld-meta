# repos/realworld-api

## Entrypoints
- HTTP API bootstrap for the RealWorld backend service.
- Route registration for auth, profiles, articles, comments, tags, and favorites.
- Middleware chain for authentication, request validation, and error handling.

## Pattern pointers
- Implements the RealWorld API contract, including JWT bearer authentication and the standard error envelope.
- Uses slug-based article access, pagination via `limit` / `offset`, and feed/filter query conventions.
- Expected separation between transport handlers, application/service layer, and persistence adapters.
- Password handling and token issuance should remain aligned with RealWorld security expectations.

## ADR index
- No repo-local ADRs recorded yet.
- Track cross-cutting decisions in the surrounding RealWorld programme memory rather than inventing repo-specific ADRs prematurely.

## Watchlist
- Contract drift against the RealWorld API specification.
- Authentication details: JWT secret handling, token expiry, and authorization boundaries.
- Error shape stability, especially the `{ "errors": { "body": [...] } }` convention.
- Query correctness for feeds, filters, pagination, and relationship counts.
- Avoid accidental coupling to one database or framework before the repo’s actual structure is confirmed.

## Sources
- INIT-REALWORLD-002 (footnote only — not an initiative folder)
