# INIT-REALWORLD-005: Deferred-attention / saved-for-later triage queue

| Field | Value |
|-------|-------|
| Initiative | INIT-REALWORLD-005 |
| Status | promoted |
| Brief | Lead conversation (INIT-REALWORLD-005 human rewind verify / retry — bookmark-article outline) |
| Promoted from | `prd/reports/INIT-REALWORLD-005-prd-think-4.md` (C4 via `/prd-quality` + Hermes promote brief `recommend: C4`) |
| Score | `/prd-quality` — C4 recommended; promote authorized |
| Series | think 4 of 4 — C4; prior `prd/reports/INIT-REALWORLD-005-prd-think.md` (C1 reading-list pins), `prd/reports/INIT-REALWORLD-005-prd-think-2.md` (C2 directed bookmark-edge + anti-reciprocity), and `prd/reports/INIT-REALWORLD-005-prd-think-3.md` (C3 reading-resume roster) exist and are **not** overwritten; deliberately does **not** clone any prior CAP/REQ table — packages **deferred-attention / saved-for-later triage queue** stewardship (defer → inspect queue → release), not C1 collection pins, not C2 edge-graph anti-reciprocity, not C3 resume/mid-read markers, not INIT-001 favorites affinity shelf, not author subscription, not parked search memory, not tag-follow edges |
| Product context | Sibling `prd/INIT-REALWORLD-001.md` (promoted; bulletin + seat + **favorites private shelf** — noun collision confronted); sibling `prd/INIT-REALWORLD-002.md` (promoted; author subscription — not reopened); sibling `prd/INIT-REALWORLD-003.md` (promoted; parked search memory — not reopened); sibling `prd/INIT-REALWORLD-004.md` (promoted; membership→tag follow edges — not reopened); `config/service-catalog-drivestream-lab.yaml` (realworld-api, realworld-web, realworld-local, realworld-meta); `planning/` skipped (README only); `.harness/profile.yaml` absent — `reports_dir` default `prd/reports/` |
| Companions | `/grilling`, `/domain-modeling`, `/opportunity-solution-tree`, `/strategy-red-team` not installed — inline Challenge / Model / Stress |
| Host mode | Non-interactive Hermes — T1 locks applied from Lead-approved brief; no AskQuestion; recommendations applied by host |

## 1. Job and outcome

- **Job:** Give a **signed-in reader** a durable, **owner-private deferred-attention queue of articles saved for later** — each **deferral** parks an article for later attention triage — so they can **defer (bookmark) an article, inspect their own triage queue, and release (unbookmark) a deferral** without other actors harvesting that queue, without claiming unfinished reading, without rewriting discovery ranking, and without collapsing this object into favorites, resume markers, reading-list pins, or directed bookmark edges.
- **Why now:** Human rewind verify (retry) needs a tiny, proveable RealWorld slice that exercises ownership-scoped bookmark defer/list/release on `realworld-api` while product truth lands in `realworld-meta`. C1 packaged collection pin stewardship; C2 packaged directed-edge anti-reciprocity; C3 packaged reading-resume / re-entry continuity; this INIT reframes the same Lead kill bar as **attention triage** — the reader’s private “deal with this later” queue, not a mid-read claim and not a curated shelf.
- **If we do nothing:** Readers still lack a durable personal **deferred-attention** object separate from favorites, resume/re-entry framing, and pin collections; floor/rewind verify has no small bookmark-shaped feature to prove under an attention-triage noun; later clients have no stewarded triage queue that is clearly isolated from affinity shelf, author subscription, search parks, tag-follow edges, C1 pins, C2 edges, and C3 resume markers.
- **Solution vs job:** “Bookmark/unbookmark by slug under a small REST surface, persisted in Postgres” remains the **delivery vehicle**. The job in this cut is **deferred-attention continuity + intentional release + idempotent defer/release + flag-gated availability** — not a settings screen, not feed ranking, not reading-progress tracking, not a second name for favorites, not author follow, not search memory, not tag follow, not C1 “pin collection” UX, not C2 edge-graph packaging as the primary noun, not C3 “come back mid-read” packaging as the primary noun, and not new infra services.
- **OST fork (T2):** (A) owner-private article reading-list pin stewardship (chosen by C1 — not re-chosen), (B) durable membership→article bookmark-edge packaging (chosen by C2 — not re-chosen), (C) reading-resume / re-entry roster packaging (chosen by C3 — not re-chosen), (D) alias/extend INIT-001 favorites under a “bookmark” noun (rejected — would reopen favorites and erase the brief’s separate feature ask), (E) **deferred-attention / saved-for-later triage queue packaging** (chosen / C4). Outcome **E** is the C4 cut so defer/list/release + idempotent toggle + owner-only queue still match the Lead kill bar while packaging **attention triage** rather than collection stewardship, edge-graph framing, or resume-intent framing.
- **Kill assumption:** Fails if a seated owner cannot defer (bookmark) an article for later attention, list own triage queue, and release (unbookmark) a deferral by durable article identity for their own membership with **idempotent** defer/release outcomes, or if an unauthorized actor (guest, post-logout, or peer member) can observe or mutate another member’s triage queue, or if deferral stewardship rewrites public/subscription discovery membership this INIT, or if deferral silently becomes unfinished-reading / progress state, or if a disabled feature gate still exposes queue contents or accepts mutations as if the feature were available.

## 2. Locked decisions

Lead-approved brief treated as T1 locks (applied; not re-asked), plus grill consequences required for a coherent deferred-attention / triage-queue product:

1. **(Programme note)** Human rewind verify (retry) guinea-pig INIT; product changes stay inside **`realworld-api` + `realworld-meta`**; reuse existing auth/seat; **no new microservices**.
2. A seated reader may **defer (bookmark)** a published article for later attention, identified by its durable article identity (brief delivery vehicle names slug; product lock is published-article identity — encoding is engineering).
3. A seated reader may **list only their own** deferred-attention triage queue (bookmarked / saved-for-later articles).
4. A seated reader may **release (unbookmark)** a deferral they currently hold (same article identity as defer).
5. Deferrals **persist durably** across sessions for the owning membership (brief delivery vehicle names Postgres; product lock is durable retention — storage engine is engineering).
6. **Feed ranking / personalized discovery** changes driven by deferrals are **out of scope** for this INIT — deferrals are retained, not applied to ranking this INIT.
7. **Web UI** for this feature is **out of scope** for this INIT; stewardship is proven on the **machine-consumable API surface** of `realworld-api` (brief may name example route shapes; routes/payloads stay out of REQ text).
8. Success bar named by Lead: **bookmark toggles idempotently**; **list returns bookmarked articles for the current user**.
9. **(This grill)** “Signed-in reader” means a **seated member** under INIT-REALWORLD-001 seat rules; guests and post-logout actors are unseated; auth is reused, not reinvented.
10. **(This grill)** A **deferred-attention save** is a **distinct product object** from INIT-001 **favorites**, INIT-002 author subscription, INIT-003 parked search memory, INIT-004 tag-follow edges, C1 reading-list pins, C2 bookmark edges, and C3 resume markers — not a rename of favorites, not unfinished-reading state, and not a query park with an article target.
11. **(This grill)** Ownership isolation is load-bearing: peer members must not list, inspect, defer-on-behalf-of, or release another member’s deferrals; unseated defer/list/release fail closed.
12. **(This grill)** Deferrals **persist across unseat/reseat** for the same membership (logout drops the seat, not the deferrals); after reseat, owner queue reflects deferrals that existed before logout unless changed while seated.
13. **(This grill)** Empty own triage queue is a valid outcome (including after releasing the last deferral).
14. **(This grill)** Defer / release are **idempotent** for prove expectations: deferring an already-deferred article leaves exactly one deferral for that article; releasing an article that is not deferred leaves the queue unchanged without creating a deferral (OQ-02/OQ-03 defaults).
15. **(This grill)** Deferring for later attention does **not** change public bulletin membership, public tag-lane membership, INIT-002 subscription-stream membership, favorites shelf membership, search parks, or tag-follow edges this INIT.
16. **(This grill)** Owner queue must expose each deferral’s **article identity** (and enough article presentation to recognize the work) so triage fidelity is observable without a UI this INIT.
17. **(This grill)** Missing / unknown article identity is **not** a valid deferral target (reject defer; no deferral created) — OQ-01 default.
18. **(This grill)** Unlike INIT-001 favorites, a seated member **may defer their own** published articles (self-deferral allowed — attention triage ≠ affinity-shelf “others only”) — OQ-04 default locked for C4.
19. **(This grill)** A deferral must **not resurrect** a deleted article’s public readability; owner queue must not expose deleted body content as if still published.
20. **(This grill)** Concurrent independence: when Member A and Member B both defer the same article, each holds a **distinct** private deferral; releasing A’s deferral must not release B’s.
21. **(This grill)** Optional **feature flag** may gate availability in environments (brief constraint); when the feature is enabled for prove, kill-bar paths must still pass — flag mechanics are engineering (OQ-08).
22. **(This grill)** Route paths, payload layouts, frameworks, and module names stay out of product REQ text; engineering consumes the WHAT + CTR absence + OQs.
23. **(This grill — C4 divergence)** Primary product noun is **deferred-attention save** / **triage queue**, not “reading-list pin collection” (C1), not “directed bookmark edge / outgoing inventory” (C2), and not “resume marker / re-entry roster” (C3). Collection folders, edge-graph anti-reciprocity packaging, and mid-read resume packaging as the primary framing stay deferred (OST forks A/B/C already drafted).
24. **(This grill — C4 divergence)** A deferral encodes **attention deferral only** — it does **not** claim the owner has started reading, left reading unfinished, or owes a resume. No unread/in-progress/finished product states this INIT.
25. **(This grill — C4 divergence)** **Release is triage completion** (owner decides attention is no longer deferred), not “finished reading” and not auto-release on open/consume. Opening a deferred article does **not** auto-release the deferral this INIT (OQ-09 default).
26. **(This grill — C4 divergence)** **Feature-flag availability is product-visible:** when the bookmark/deferral feature is **disabled** for the environment (or actor), defer / list / release must **fail closed** — no successful queue disclosure, no mutations accepted as if available (OQ-08 default for disabled path). When enabled for prove, Lead kill-bar paths must pass.
27. **(This grill — C4 divergence)** **Orthogonal coexistence with favorites:** a seated member may hold both an INIT-001 favorite and a deferred-attention save on the **same** article; defer/release must not rewrite favorites; favorite/unfavorite must not rewrite the triage queue this INIT.

## 3. In scope / non-goals

### In scope

**Sibling scope boundary (INIT-REALWORLD-001 / 002 / 003 / 004):** This INIT owns **deferred-attention / saved-for-later triage queue** only (CAP-01–CAP-03 / REQ-01–REQ-22). It does **not** re-own INIT-001 favorites / seat / publish requirement ids, INIT-002 author-subscription / subscription-stream requirement ids, INIT-003 parked-search requirement ids, or INIT-004 tag-follow requirement ids. Favorites, subscriptions, parks, and tag-follow edges remain baseline and are not reopened here.

- Seated deferral of an article onto an owner-private triage queue by durable article identity.
- Seated inspection of **own** triage queue (populated or empty) with article-identity fidelity.
- Seated intentional release of an **own** deferral.
- Idempotent defer and release outcomes for the owning membership.
- Durable retention of deferrals across unseat/reseat for the owning membership.
- Fail-closed denial for unseated defer / list / release.
- Fail-closed isolation so peers cannot observe or mutate another’s queue.
- Explicit **attention-only** semantics: no unfinished-reading / progress product state; no auto-release on open.
- Explicit **feature-unavailable** fail-closed when the feature gate is off.
- Explicit **favorites coexistence** without cross-write.
- Explicit non-application: deferrals must not rewrite public or subscription discovery membership this INIT.
- Explicit noun separation from INIT-001 favorites (including allowing own-article deferrals), INIT-003 search parks, INIT-004 tag-follow, and prior C1/C2/C3 packaging nouns.
- Product write-up in `realworld-meta`; implementation ownership on `realworld-api` only for this feature surface.

### Non-goals (load-bearing)

- **Feed ranking / personalization**, or any “articles for you because you deferred X” timeline membership as a required success path this INIT.
- Settings (or any) **web UI** for triage-queue management, “saved for later”, or “continue reading” screens this INIT (`realworld-web` feature work deferred).
- New microservices / infra services beyond existing catalog services.
- Reopening INIT-REALWORLD-001 publish / seat / **favorites** / nameplate / public tag-lane requirement sets (favorites stay the affinity shelf; this INIT does not rename or merge them).
- Reopening INIT-REALWORLD-002 author subscription / subscription-stream rules.
- Reopening INIT-REALWORLD-003 parked search memory rules (query parks ≠ article deferrals).
- Reopening INIT-REALWORLD-004 membership→tag follow edge rules.
- **Reading-progress / unfinished-reading** product state (scroll %, last position, unread flags, percent-read) this INIT.
- **Auto-release on open / finish / consume** as a required success path this INIT.
- Public **who-saved / who-deferred** social proof (counts, actor lists, or reverse-index queries).
- Treating deferred-attention save as favorite, author-follow, search-park, tag-follow, C1 pin, C2 edge, or C3 resume marker.
- Comments, OAuth, email verification, mobile/native clients.
- Admin/moderation tooling over other members’ triage queues.
- Cross-member transfer or export programmes.
- C1-style **reading-list pin collection** packaging as the primary product noun (parked as OST fork A — already drafted in think 1).
- C2-style **directed bookmark-edge / anti-reciprocity** packaging as the primary product noun (parked as OST fork B — already drafted in think 2).
- C3-style **reading-resume / re-entry roster** packaging as the primary product noun (parked as OST fork C — already drafted in think 3).
- Folders, notes, multi-queue organization, priority ranking inside the queue, or “finished archive” beyond binary defer/release.

## 4. Actors

| Actor | Can actually | Cannot / OQ |
|-------|----------------|-------------|
| Guest (unseated) | Continue INIT-001 ungated bulletin / public tag-lane browse unchanged by this INIT | Defer/list/release triage items; observe any member’s triage queue; query inbound savers of an article |
| Seated member (owner) | Defer, inspect queue, release **own** deferrals (including own articles per lock 18); see own queue after reseat with article identities intact; hold favorite + deferral on the same article without cross-write (lock 27); open a deferred article without auto-release (lock 25) | Observe or mutate a peer’s queue; keep stewardship after logout; force personalized feed this INIT; require UI this INIT; discover who else deferred an article; store unfinished-reading fields this INIT; mutate/list when feature gate is disabled |
| Peer member | Steward only their own triage queue (including independently deferring the same article as another member) | Inspect, defer-as, or release another member’s deferrals; harvest another’s triage queue via list, direct access, or reverse-index |
| Programme UAT / API prove observer | Drive owner vs peer vs unseated vs concurrent-same-article vs idempotent toggle vs flag-off fail-closed vs favorites-coexistence paths against `realworld-api` to judge the kill assumption | Not an in-product role; must not require web UI this INIT |

## 5. Capabilities

| ID | Capability | Journeys covered | Notes |
|----|------------|------------------|-------|
| CAP-01 | Defer a published article into an owner-private triage queue | J-01, J-02, J-08, J-11, J-13, J-17, J-19, J-20 | Seated defer by article identity; missing article refused; own-article allowed; idempotent re-defer; attention-only (no unfinished-reading claim); favorites coexistence defer half |
| CAP-02 | Inspect and intentionally release own triage queue | J-01, J-03, J-04, J-08, J-10, J-13, J-15, J-17, J-19, J-21, J-22 | Queue with article-identity fidelity; intentional release removes; empty set valid; persist across reseat; re-defer after release; open does not release; distinct from favorites / parks / tag-follow / C1–C3 nouns; deleted-article queue inspection |
| CAP-03 | Triage privacy, flag-gated availability, non-application, non-composition, and attention-only semantics | J-05, J-06, J-07, J-09, J-12, J-14, J-16, J-17, J-18, J-20, J-21, J-22, J-23 | Peer opacity; unseated fail-closed; absent release denied/idempotent; no inbound who-saved; concurrent same-article independence; feature-off fail-closed; favorites orthogonality; deleted-article non-resurrection; deferrals do not rewrite public lanes, bulletin, subscription stream, favorites, parks, tag-follow, or peer queues; no unfinished-reading product state |

Divergence note (C4 of 4): this INIT packages **deferred-attention / saved-for-later triage queue** stewardship with **attention-only semantics**, **intentional release (not finished-reading)**, **feature-unavailable fail-closed**, and **favorites orthogonal coexistence** — not C1’s reading-list pin collection, not C2’s directed-edge anti-reciprocity framing, and not C3’s resume/mid-read roster.

## 6. Requirements

| ID | CAP | Requirement (WHAT) | Condition / event | Observable result | Evidence |
|----|-----|--------------------|-------------------|-------------------|----------|
| REQ-01 | CAP-01 | Defer a published article onto the owner’s private triage queue | Seated member defers a published article using a valid article identity while the feature is available | An owner-private deferral exists for that article; owner triage queue includes that article identity exactly once | live (CAP-01, J-01) |
| REQ-02 | CAP-03 | Refuse defer while unseated | Guest or post-logout actor attempts to defer an article | No new deferral is created for any membership | live (CAP-03, J-07) |
| REQ-03 | CAP-02 | Inspect only the owner’s triage queue with article-identity fidelity | Seated member requests their triage queue when they own zero or more deferrals and the feature is available | Queue contains exactly that member’s deferred article identities (or empty); no other member’s deferrals appear; each article identity appears at most once | live (CAP-02, J-03) |
| REQ-04 | CAP-02 | Intentionally release an owned deferral | Seated member releases a deferral they currently hold | That article identity no longer appears on the owner’s triage queue | live (CAP-02, J-04) |
| REQ-05 | CAP-02 | Persist deferrals across unseat and reseat | Seated member defers an article, logs out, then logs in again without changing deferrals while unseated | After reseat, owner queue still includes that article identity | live (CAP-02, J-08) |
| REQ-06 | CAP-02 | Allow empty own queue after the last release | Seated member releases their last remaining deferral | Owner triage queue is empty and valid (not an error wall) | live (CAP-02, J-10) |
| REQ-07 | CAP-03 | Keep one member’s triage queue invisible to another seated member | Member A owns ≥1 deferral; Member B is seated and is not A | B cannot obtain A’s queue via list or direct access | live (CAP-03, J-06) |
| REQ-08 | CAP-03 | Refuse release of another member’s deferral | Seated peer attempts to release an article on Member A’s queue (or otherwise remove A’s deferral) | A’s queue unchanged; peer’s own queue unchanged by that attempt | live (CAP-03, J-09) |
| REQ-09 | CAP-03 | Deny list / release while unseated | Guest or post-logout actor attempts list or release | No queue contents of any member are disclosed as a successful list result; no release side effects | live (CAP-03, J-07) |
| REQ-10 | CAP-03 | Keep release idempotent when deferral is absent | Seated member attempts release against an article they do not currently defer | Own queue unchanged; no new deferral created; fail-closed or no-op success per OQ-03 default without disclosing peer queues | unit / live (CAP-03, J-12) |
| REQ-11 | CAP-01 | Refuse defer of missing / unknown article identity | Seated member attempts to defer an article identity that does not resolve to a published article | No deferral is created; owner queue unchanged by that attempt | live (CAP-01, J-11) |
| REQ-12 | CAP-03 | Keep public discovery membership independent of own deferrals | Seated member defers ≥1 article then uses public bulletin / tag-lane discovery | Public discovery membership remains unpersonalized by this INIT’s deferrals; guest browse unchanged | live (CAP-03, J-05) |
| REQ-13 | CAP-01 | Keep defer idempotent when already deferred | Seated member defers an article they already defer | Owner queue still includes that article identity exactly once; no duplicate deferrals for prove expectations | live (CAP-01, J-01) |
| REQ-14 | CAP-03 | Keep subscription-stream membership independent of deferrals | Seated member who holds INIT-002 author subscriptions also defers ≥1 article | Subscription-stream membership remains driven by author subscriptions only; deferrals do not add/remove stream articles this INIT | live (CAP-03, J-14) |
| REQ-15 | CAP-02 | Keep deferrals distinct from favorites and parked search memory | Seated member who owns ≥1 INIT-001 favorite and/or ≥1 INIT-003 parked search also defers ≥1 article | Owner queue lists deferred articles only; favorites shelf and parked-search recall remain separate objects and are not rewritten by defer/release this INIT | live (CAP-02, J-15) |
| REQ-16 | CAP-03 | Keep peers’ public browse unaffected by owner deferrals | Member A defers ≥1 article; Member B (or a guest) browses public bulletin / tag lanes | Public membership for B/guest stays ungated and unpersonalized; A’s private deferral does not gate, hide, or personalize discovery for others | live (CAP-03, J-16) |
| REQ-17 | CAP-03 | Keep concurrent same-article deferrals independent across members | Member A and Member B both defer the same article; then A releases that deferral | B’s queue still includes that article identity; A’s no longer does; no shared/merged deferral | live (CAP-03, J-17) |
| REQ-18 | CAP-03 | Refuse inbound who-saved disclosure for an article | Any actor attempts to obtain which members deferred a given article (counts or actor list) via a product surface of this INIT | No successful disclosure of deferral membership for that article; owner-only triage queue remains the sole deferral-inspection path | live (CAP-03, J-18) |
| REQ-19 | CAP-02 | Keep deferral present after owner opens the deferred article | Seated member who holds a deferral for article X opens / re-reads X without performing release | Owner queue still includes article X after the open; deferral was not auto-released | live (CAP-02, J-19) |
| REQ-20 | CAP-03 | Keep favorites and triage-queue states orthogonal on the same article | Seated member holds (or creates) both an INIT-001 favorite and a deferred-attention save on the same article X; then releases X from the triage queue (or unfavorites X) | After release of X, favorite on X remains if it existed; after unfavorite of X, deferral on X remains if it existed; neither surface rewrites the other this INIT | live (CAP-03, J-20, J-21) |
| REQ-21 | CAP-03 | Fail closed when the deferred-attention feature is unavailable | Seated member attempts defer, list, or release while the feature gate is disabled for the environment/actor | No successful queue disclosure; no deferral mutations accepted; behavior is unavailable/fail-closed rather than silently operating | live (CAP-03, J-23) |
| REQ-22 | CAP-03 | Keep a triage-queue deferral from resurrecting a deleted article’s public readability | Author deletes a published article that still has (or previously had) an owner deferral | Owner triage queue must not expose the deleted article’s published body to any actor; Guest open-by-reference remains not-found (OQ-05 default — eng may choose drop vs unavailable marker for the queue row) | live (CAP-03, J-22) |

## 7. Negative and failure paths

| REQ | Condition | Required behavior | Why it matters |
|-----|-----------|-------------------|----------------|
| REQ-03 / J-03 | Owner has zero deferrals | Empty queue, still seated-only | Empty ≠ error; matches success “list works” |
| REQ-03 | Owner has deferrals | Listed identities match deferred articles; at most once each | Triage fidelity observable without UI |
| REQ-02 / REQ-09 | Unseated defer/list/release | Fail closed; no disclosure; no mutations | Kill assumption — seat gate |
| REQ-07 / J-06 | Peer tries to read owner’s queue | Isolation holds; no triage-queue harvest | Kill assumption — unauthorized cannot see others’ deferrals |
| REQ-08 / J-09 | Peer tries to remove owner’s deferral | Target unchanged | Isolation beyond read opacity |
| REQ-06 / J-10 | Last deferral released | Empty own queue allowed | Prevents “must always defer one article” false rule |
| REQ-10 / J-12 | Release when deferral absent | Idempotent / fail closed; own queue unchanged | Lead idempotent toggle bar; prevents cross-owner leakage |
| REQ-11 / J-11 | Missing article identity | Defer refused; no record | Deferral targets must be real published articles |
| REQ-12 / J-05 | Owner defers then browses public discovery | Public discovery not rewritten by deferrals | Load-bearing non-goal: no ranking this INIT |
| REQ-13 / J-01 | Re-defer already deferred | Still one deferral | Lead idempotent toggle bar |
| REQ-14 / J-14 | Owner has author subscriptions + deferrals | Subscription stream unchanged by deferrals | Noun / graph separation from INIT-002 |
| REQ-15 / J-15 | Owner has favorites / parks + deferrals | Objects stay separate | Noun / surface separation from INIT-001 / INIT-003 |
| REQ-16 / J-16 | Owner defers; peer/guest browses public surfaces | Public browse stays ungated and unpersonalized for others | Private deferral is not a discovery ACL |
| REQ-17 / J-17 | Two members defer same article; one releases | Only the actor’s deferral dissolves | Deferrals are membership-scoped, not shared |
| REQ-18 / J-18 | Actor seeks inbound savers-of-article | No disclosure this INIT | Anti-harvest — kills social-proof side door |
| REQ-19 / J-19 | Owner opens deferred article without release | Deferral remains | C4 divergence — attention ≠ auto-consume |
| REQ-20 / J-20 | Favorite + deferral on same article | Both may coexist | Orthogonality vs favorites affinity |
| REQ-20 / J-21 | Release deferral while favorite remains (or reverse) | Other object unchanged | No cross-write between shelves |
| REQ-21 / J-23 | Feature gate disabled | Fail closed; no disclosure; no mutations | Brief “ship behind feature flag” made product-visible |
| J-02 | Owner defers own published article | Defer succeeds; queue includes own article | Distinguishes triage from favorites “others only” |
| REQ-22 / J-22 | Author deletes a deferred article | Deleted body not publicly readable via queue; no resurrection | Aligns with INIT-001 non-resurrection spirit (OQ-05); lock 19 |

## 8. Contract seeds (semantic)

None — no cross-repo product seam in this INIT. Deferred-attention / triage-queue stewardship is owned and proven on `realworld-api`; `realworld-web` UI is an explicit non-goal; `realworld-meta` carries product truth only.

## 9. NFR applicability

| Area | Requirement or N/A rationale |
|------|------------------------------|
| Security | Seat-bound stewardship; unseated and peer access fail closed (REQ-02, REQ-07–REQ-10). No inbound who-saved surface (REQ-18). Deferrals are not discovery ACLs (REQ-16). Feature-unavailable path fails closed (REQ-21). Deleted-article deferrals must not resurrect published body via the queue (REQ-22). Existing auth/seat reused (lock 9). |
| Reliability | N/A beyond fail-closed defer/list/release behavior — not a multi-region SLA INIT. |
| Performance / capacity | N/A for guinea-pig scale; no concurrent-load target locked (per-member count limits → OQ-06). |
| Observability | N/A as product REQ — operational logging is engineering choice. |
| Privacy / data handling | Deferrals are private to the owning membership; peers and guests must not observe the set (REQ-07, REQ-09) or reverse-index it (REQ-18). No unfinished-reading telemetry is productized this INIT (locks 24–25). |
| Migration / compatibility | Additive private triage state for existing members; default empty own triage queue. Does not migrate or rewrite INIT-001 favorites, INIT-002 author-follow edges, INIT-003 parks, or INIT-004 tag-follow edges. Does not rewrite public discovery membership this INIT. Favorites coexistence is additive orthogonality (REQ-20). |
| Rollback / recovery | Feature-unavailable fail-closed is the product-visible rollback posture when the gate is off (REQ-21); delivery rollback mechanics remain engineering (OQ-08). |
| Operations / support | No new microservices; prove against existing `realworld-api` (local compose may host prove without expanding product scope to web UI). Feature flag optional per brief but product-visible when off (REQ-21 / OQ-08). |

## 10. Assumptions

| ID | Assumption | Status | Dependent REQs | Default if false |
|----|------------|--------|----------------|------------------|
| A-01 | INIT-REALWORLD-001 contribution-seat semantics (login seats, logout unseats) remain the gate for “signed-in reader”; existing auth is reused | accepted-for-draft | REQ-02, REQ-05, REQ-09 | If seat meaning changed, reopen with Lead before drafting alternate REQs |
| A-02 | Deferred-attention save is a distinct product object from INIT-001 favorites; “bookmark” in this INIT means triage-queue stewardship, not favorite rename | accepted-for-draft | REQ-01–REQ-22, REQ-15, REQ-20 | If Lead intended favorites reuse under a new route name, kill this INIT’s noun and reopen |
| A-03 | Durable retention means membership-scoped persistence across logout/login, not merely in-process memory | accepted-for-draft | REQ-05 | Session-only memory fails the brief’s persist intent |
| A-04 | Two distinct gates apply: (a) **unseated fail-closed** for defer/list/release, and (b) **peer / inbound opacity** so seated peers cannot observe or reverse-index another member’s triage queue | accepted-for-draft | REQ-02, REQ-07, REQ-08, REQ-09, REQ-18 | If peer visibility or inbound saver lists were allowed, or if unseated mutate were soft-open, kill assumption would be incoherent — reopen with Lead |
| A-05 | Owner queue exposing article identities is sufficient triage-fidelity proof without web UI, feed ranking, or unfinished-reading fields this INIT | accepted-for-draft | REQ-03, REQ-12, REQ-16, REQ-19 | If UI navigation, ranking, or progress tracking becomes kill-path, reopen scope with Lead |
| A-06 | Public bulletin / tag-lane discovery and INIT-002 subscription-stream rules remain baseline and are not rewritten by this INIT’s deferrals | accepted-for-draft | REQ-12, REQ-14, REQ-16 | If deferrals must alter discovery membership, that is a different INIT |
| A-07 | Deferred-attention save is a different product object from INIT-003 parked search memory and INIT-004 tag-follow edges (attention deferral ≠ query park ≠ tag follow) | accepted-for-draft | REQ-15 | If Lead intended park or tag-follow reuse, kill this INIT’s noun and reopen |
| A-08 | Idempotent defer/release is a product kill-bar property (Lead acceptance), not merely an engineering nicety | accepted-for-draft | REQ-10, REQ-13 | If duplicate deferrals or hard errors on re-defer were required, reopen kill bar with Lead |
| A-09 | Concurrent same-article deferrals by different members are independent deferrals, not a shared multiset row | accepted-for-draft | REQ-17 | If shared deferrals were intended, ownership isolation REQs would need redesign |
| A-10 | Own-article deferral is allowed this INIT (attention triage ≠ favorites “others only”) | accepted-for-draft | REQ-01, J-02 | If Lead wants favorites-like own-article refusal, flip OQ-04 and add a refuse-own REQ |
| A-11 | Opening a deferred article must not auto-release the deferral this INIT; release is intentional triage completion | accepted-for-draft | REQ-19 | If auto-release-on-open/finish is required, replace REQ-19 and reopen kill bar with Lead |
| A-12 | Attention-only semantics (no unfinished-reading / progress fields) are sufficient for this guinea-pig cut and distinguish C4 from C3 resume framing | accepted-for-draft | REQ-19, locks 24–25 | If resume/progress becomes the primary noun, prefer C3 packaging or reopen |
| A-13 | When the feature gate is disabled, fail-closed unavailable behavior is required product posture (not soft-open, not empty-success list that hides existence rules inconsistently) | accepted-for-draft | REQ-21 | If flag-off must still allow list of historical deferrals, reopen OQ-08 with Lead |
| A-14 | Favorites and triage-queue states are orthogonal and may coexist on the same article without cross-write | accepted-for-draft | REQ-20 | If mutual exclusion were required, add refuse-when-favorited REQs and reopen |

## 11. Open questions

| ID | Question | Owner | Blocking | Required-by | Default if deferred |
|----|----------|-------|----------|-------------|---------------------|
| OQ-01 | Exact article-identity rules for deferral target (must currently be published; soft-deleted / missing handling) | PM | no | spec-draft | Defer only resolves to a currently published article; missing identity → refuse create; no deferral created |
| OQ-02 | Is defer of an already-deferred article idempotent success (still one deferral), or a distinct conflict outcome? | PM | no | spec-draft | Idempotent success — queue still shows the article once (matches Lead acceptance) |
| OQ-03 | Exact shape for release when deferral absent (no-op success vs indistinguishable not-found vs explicit conflict) | PM | no | spec-draft | Idempotent no-op success for owner; no deferral created; no peer-queue contents disclosed |
| OQ-04 | May a seated member defer their own published articles? | PM | no | spec-draft | Yes — allowed (self-deferral), distinguishing from INIT-001 favorites own-article refusal |
| OQ-05 | Owner-visible behavior when a deferred article is later deleted by its author | PM | no | spec-draft | Non-resurrection floor locked by REQ-22 / lock 19; owner queue drops or marks unavailable without exposing body (eng may choose drop vs unavailable marker); Guest open-by-reference stays not-found |
| OQ-06 | Per-member maximum number of deferrals and article-identity length / normalization | PM | no | spec-draft | Eng reasonableness limits acceptable |
| OQ-07 | Owner triage-queue ordering rule for prove expectations | PM | no | spec-draft | Newest-deferred-first (attention recency); exact timestamp source left to eng — not urgency/resume ranking |
| OQ-08 | Whether a feature flag must gate the surface in all environments, and exact unavailable semantics when off | PM | no | feasibility / later | Optional gate; when off → fail-closed unavailable (REQ-21); when enabled for prove, REQ kill paths must pass |
| OQ-09 | Whether opening or finishing a deferred article should auto-release the deferral this INIT | PM | no | later | No — intentional release only (REQ-19); auto-release deferred |
| OQ-10 | Whether favorites (INIT-001) and deferrals must stay mutually invisible in each other’s recall surfaces beyond orthogonal coexistence | PM | no | later | Yes for cross-write — surfaces remain separate; coexistence allowed (REQ-20); no merge into one shelf |
| OQ-11 | Whether any viewer-relative “saved for later” chrome on public article presentation is required this INIT | PM | no | later | No — queue defer/list/release is enough; public article CTA state deferred |
| OQ-12 | Whether unavailable (flag-off) responses must be distinguishable from unseated denial for prove | PM | no | spec-draft | Eng may distinguish; product requires both fail closed without queue disclosure |
| OQ-13 | Whether historical deferrals created while the feature was on remain readable after the gate turns off | PM | no | later | No — while gate is off, list/mutate unavailable (REQ-21); durability resumes when gate returns on |

## 12. Journeys

| ID | Actor | Trigger | Main flow | Primary edge | Abandon | Caps exercised |
|----|-------|---------|-----------|--------------|---------|----------------|
| J-01 | Seated member | Wants to park an article for later attention | Defers article → lists queue → sees that article identity once | Already-deferred → idempotent (OQ-02 / REQ-13) | Abandons before defer → no deferral | CAP-01, CAP-02 |
| J-02 | Seated member | Wants to defer their own published article | Defers own article → lists → sees own article identity | Favorites would refuse; triage allows | — | CAP-01 |
| J-03 | Seated member | Wants to see which articles they deferred | Opens own triage queue | Empty queue when none deferred | Leaves without changes | CAP-02 |
| J-04 | Seated member | Decides attention is no longer deferred | Releases deferral → lists → identity absent | — | — | CAP-02 |
| J-05 | Seated member | Continues public discovery after deferring | Defers ≥1 article → browses public bulletin / tag lanes | Discovery stays unpersonalized | Stops browsing | CAP-03 |
| J-06 | Peer member | Tries to harvest another’s triage queue | Attempts to list/access Member A’s deferrals | Denied / no disclosure | — | CAP-03 |
| J-07 | Guest / post-logout | Tries stewardship without a seat | Attempts defer, list, or release | Fail closed; no side effects; no disclosure | — | CAP-03 |
| J-08 | Seated member | Relies on continuity across sessions | Defers article → logs out → logs in → lists | Same article identity still present | — | CAP-01, CAP-02 |
| J-09 | Peer member | Tries to alter another’s deferrals | Attempts release of A’s deferred article | A unchanged | — | CAP-03 |
| J-10 | Seated member | Clears the last deferral | Releases final article → lists empty | Empty is valid | — | CAP-02 |
| J-11 | Seated member | Tries to defer a missing article | Attempts defer with unknown identity | Refused; queue unchanged | — | CAP-01 |
| J-12 | Seated member | Uses a no-op release target | Attempts release on an article they do not defer | Idempotent / fail closed; own queue unchanged | — | CAP-03 |
| J-13 | Seated member | Returns to a previously released deferral | Releases article → defers same identity again → lists | Identity present once after re-defer | Abandons after release → stays empty for that identity | CAP-01, CAP-02 |
| J-14 | Seated member | Holds author subscriptions and deferrals together | Has ≥1 author subscription; defers ≥1 article; opens subscription stream | Stream membership ignores deferrals | — | CAP-03 |
| J-15 | Seated member | Holds favorites / parks and deferrals together | Owns ≥1 favorite and/or ≥1 INIT-003 park; defers ≥1 article; opens each surface | Objects remain separate; release does not clear favorites/parks | — | CAP-02 |
| J-16 | Peer / guest | Browses public surfaces while owner has deferrals | A defers article X; B or guest opens public bulletin / lanes | Surfaces stay ungated and unpersonalized for B/guest | — | CAP-03 |
| J-17 | Two seated members | Independently defer the same article, then one leaves | A and B both defer article X; A releases X; both list | A’s queue lacks X; B’s queue still has X | — | CAP-01, CAP-02, CAP-03 |
| J-18 | Any actor | Tries to learn who deferred an article | Attempts inbound savers-of-article disclosure for article X | No successful deferral-membership disclosure this INIT | — | CAP-03 |
| J-19 | Seated member | Opens a deferred article without releasing | Defers X → opens X → lists queue | X still present (no auto-release) | — | CAP-01, CAP-02 |
| J-20 | Seated member | Holds favorite and deferral on the same article | Favorites X and defers X (either order); inspects both surfaces | Both states present; neither surface merges the other | — | CAP-01, CAP-03 |
| J-21 | Seated member | Releases deferral while favorite remains (or unfavorites while deferral remains) | Releases X from queue (favorite remains) **or** unfavorites X (deferral remains) | Cross-object state unchanged | — | CAP-02, CAP-03 |
| J-22 | Seated member / guest | Author deletes an article that was deferred | Author deletes X; owner queue / guest open checked | No published-body resurrection via queue; guest open stays not-found | — | CAP-02, CAP-03 |
| J-23 | Seated member | Tries stewardship while feature gate is off | Attempts defer, list, or release with feature unavailable | Fail closed unavailable; no queue disclosure; no mutations | — | CAP-03 |

Brief already listed bookmark / unbookmark / list and idempotent toggle; **J-02** (own-article self-deferral), **J-05** (discovery stays unpersonalized), **J-08** (persist across reseat), **J-10** (empty after last release), **J-11** (refuse missing article), **J-12** (idempotent absent release), **J-13** (re-defer after release), **J-14** (subscription stream independent), **J-15** (favorites/park separation), **J-16** (peer/guest browse unaffected), **J-17** (concurrent same-article independence), **J-18** (no inbound who-saved), **J-19** (open without auto-release — attention ≠ consume), **J-20** / **J-21** (favorites orthogonal coexistence — C4 divergence), **J-22** (delete non-resurrection), and **J-23** (feature-unavailable fail-closed — C4 divergence) are whole-product paths the outline did not spell out — and they distinguish deferred-attention triage packaging from C1 reading-list pins, C2 directed bookmark edges, C3 resume rosters, favorites affinity shelf, author subscription, parked search memory, and tag-follow edges.

## 13. Domain terms

| Term | Meaning in this INIT | Collision with existing product? |
|------|----------------------|----------------------------------|
| Deferred-attention save / bookmark | Durable owner-private membership→article park for later attention triage; primary product noun this cut | New object; do **not** call this INIT-001 favorite, INIT-002 author subscription, INIT-003 parked search, INIT-004 tag-follow, C1 reading-list pin, C2 bookmark edge, or C3 resume marker |
| Defer (bookmark) | Seated action that creates an owner-private deferred-attention save for a published article identity | Collides with everyday “bookmark” / Conduit “favorite” language — always say **deferral** / **saved for later** when contrasting |
| Release (unbookmark) | Seated intentional action that removes an owner-private deferral (triage completion) | Same noun collision risk as defer; not auto-release on open; not “finished reading” |
| Triage queue / own-list | The set of article identities the owning membership currently defers | Distinct from favorites shelf, subscription stream, parked search recall, tag-follow outgoing list, C1 “pin list”, C2 “outgoing inventory”, and C3 “re-entry roster” packaging |
| Attention-only semantics | Deferral means “deal with later” only — no unread/in-progress/finished or scroll/percent product state | Distinguishes this cut from C3 resume/mid-read framing and from progress products |
| Intentional release | Deferral persists until the owner releases it; opening the article does not release | Load-bearing C4 product rule (shared *shape* with C3 intentional clear, different noun/job) |
| Feature-unavailable | Feature gate off → defer/list/release fail closed without queue disclosure | Makes brief “ship behind feature flag” product-visible (REQ-21) |
| Favorites orthogonality | Favorite and deferral may coexist on the same article without cross-write | Distinguishes affinity shelf from attention triage |
| Article identity | Durable locator for a published article (brief may say slug); must re-present on owner queue | Aligns with INIT-001 published articles; encoding is engineering |
| Idempotent toggle | Re-defer of an already-deferred article leaves one deferral; release of an absent deferral leaves queue unchanged without creating a deferral | Lead acceptance language; product property this INIT |
| Concurrent independence | Two members deferring the same article hold distinct private deferrals | Distinguishes per-membership deferrals from a shared multiset |
| Non-composition / non-application | Deferrals must not merge with favorites / parks / tag-follow / author-follow, and must not rewrite discovery ranking this INIT | Explicit product rule for this cut |
| Owner | Seated membership that holds the deferrals; sole steward | Aligns with seat-bound ownership patterns; object is new |
| Unseated | Guest or post-logout actor under INIT-001 seat rules | Same seat vocabulary; no new auth product |
| Feed ranking / personalization | Using deferrals to change which articles appear in a feed | Explicit **non-goal** this INIT |

---

## Discovery notes (not scored)

**Promote complete.** Think-4 content is the promoted PRD at `prd/INIT-REALWORLD-005.md` per Hermes promote brief (`recommend: C4`). Inline Challenge / Model / Stress provenance remains in locks and §1 OST fork; not open pipeline stops. Next: `/validate-requirements` (incremental after document updates) → `/prd-impact-map`.
