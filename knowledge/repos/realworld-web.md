# repos/realworld-web

## Entrypoints
- Expected frontend bootstrap: app mount, routing shell, and page-level views.
- Expected dev/build entrypoints from package or workspace scripts.
- Expected API client/service layer used by pages/components.

## Pattern pointers
- Treat RealWorld domain flows (auth, articles, comments, profiles) as feature boundaries.
- Keep API access behind a service/client boundary rather than scattering network calls.
- Isolate session/auth persistence and route guards from presentation logic.

## ADR index
- No ADRs indexed yet; record framework, state management, routing, and API contract decisions when made.

## Watchlist
- Verify actual framework, entry scripts, routing model, and state approach.
- Check alignment with realworld-meta contracts and RealWorld spec expectations.
- Watch for drift in auth/session handling and article CRUD flows.

## Sources
- INIT-REALWORLD-001 (footnote only — not an initiative folder)
