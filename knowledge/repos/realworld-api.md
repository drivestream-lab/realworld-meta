# repos/realworld-api

## Entrypoints
- No confirmed entrypoint recorded yet; next review should identify the API bootstrap, route registration, and server startup surface.

## Pattern pointers
- Expected to implement the RealWorld API contract with clear separation between transport, application, and persistence concerns.
- Auth, validation, error mapping, and domain rules should remain outside raw HTTP handlers where possible.

## ADR index
- No ADRs recorded yet for `realworld-api`.

## Watchlist
- Confirm the actual server entrypoint and module layout.
- Verify authentication, authorization, validation, and error handling boundaries.
- Check that API behaviour is covered by contract or integration tests.

## Sources
- INIT-REALWORLD-001 (footnote only — not an initiative folder)
