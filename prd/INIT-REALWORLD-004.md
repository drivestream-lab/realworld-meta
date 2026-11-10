# INIT-REALWORLD-004: Private membership→tag follow edges

| Field | Value |
|-------|-------|
| Initiative | INIT-REALWORLD-004 |
| Status | promoted |
| Brief | Lead conversation (Floor wave guinea-pig INIT — god mode verify; follow-tags outline) |
| Promoted from | `prd/reports/INIT-REALWORLD-004-prd-think-4.md` (C4 via `/prd-quality` + Hermes promote brief `recommend: C4`) |
| Score | `/prd-quality` — C4 recommended; promote authorized |
| Series | think 4 of 4 — C4; prior C1 (`…-prd-think.md`, owner-private topic watchlist), C2 (`…-prd-think-2.md`, durable topic-interest signal ledger), and C3 (`…-prd-think-3.md`, private tag-lane re-entry bookmarks) deliberately **not** cloned — reframes job as **private membership→tag follow edges** (establish → inspect outgoing → dissolve), not collection stewardship, not ranking-oriented interest ledger, not lane re-entry roster, not author subscription, not favorites, not parked search memory |
| Product context | Sibling `prd/INIT-REALWORLD-001.md` (promoted; bulletin + seat + favorites; public tag lanes); sibling `prd/INIT-REALWORLD-002.md` (promoted; **author** subscription / follow edges — noun collision avoided by targeting **tags**, not authors); sibling `prd/INIT-REALWORLD-003.md` (promoted; parked search memory — not reopened); `config/service-catalog-drivestream-lab.yaml` (realworld-api, realworld-web, realworld-local, realworld-meta); `planning/` skipped (README only); `.harness/profile.yaml` absent — `reports_dir` default `prd/reports/` |
| Companions | `/grilling`, `/domain-modeling`, `/opportunity-solution-tree`, `/strategy-red-team` not installed — inline Challenge / Model / Stress |
| Host mode | Non-interactive Hermes — T1 locks applied from Lead-approved brief; no AskQuestion; `ADH_AUTONOMY_MODE=god` |

## 1. Job and outcome

- **Job:** Give a **signed-in reader** durable, **owner-private outgoing follow edges** from their membership to **tag names** they choose to follow — so they can **establish, inspect, and dissolve** those edges without other actors harvesting an inbound “who follows this tag” graph, without composing those edges into the INIT-002 author-follow graph, and without this INIT rewriting discovery into a personalized feed.
- **Why now:** Floor-wave guinea-pig INIT (god mode verify) needs a tiny, proveable RealWorld slice that exercises ownership-private create/list/delete on `realworld-api` while product truth lands in `realworld-meta`, adjacent to but distinct from author-subscription and search-memory INITs, and deliberately different from C1 watchlist-stewardship, C2 interest-signal packaging, and C3 lane-bookmark packaging.
- **If we do nothing:** Readers have no durable personal record of which tags they hold a follow relationship to; floor-wave has no small tag-follow feature to prove; later clients have no stewarded **membership→tag edge** object that is clearly isolated from author-follow edges and from public social proof.
- **Solution vs job:** “CRUD under a small tag-follows API, persisted in Postgres” is the **delivery vehicle**. The job is **owner-private directed follow-edge continuity + graph isolation** — not a settings screen, not feed personalization, not author follow (INIT-002), not favorites (INIT-001), not parked search memory (INIT-003), not C1’s collection-stewardship framing, not C2’s ranking-oriented signal ledger, not C3’s lane re-entry roster framing, and not new infra services.
- **OST fork (T2):** (A) C1-style owner-private topic watchlist stewardship, (B) C2-style durable topic-interest signal ledger, (C) C3-style private tag-lane re-entry bookmarks, (D) **private membership→tag follow edges** (chosen / C4). Outcome **D** is the C4 cut so establish/list/dissolve + fail-closed unauth match the Lead kill bar while packaging **directed-edge semantics**, **anti-reciprocity** (no inbound follower index this INIT), and **non-composition** with the author-follow graph rather than inventing ranking, lane-resume UX, or UI the brief did not lock.
- **Kill assumption:** Fails if a seated owner cannot follow (establish edge), list (inspect own outgoing edges), and unfollow (dissolve edge) tags by name for their own membership, or if an unauthorized actor (guest, post-logout, or peer member) can observe or mutate another member’s tag-follow edges — including via any inbound “followers of tag” harvest this INIT.

## 2. Locked decisions

Lead-approved brief treated as T1 locks (applied; not re-asked), plus grill consequences required for a coherent membership→tag follow-edge product:

1. **(Programme note)** Floor-wave guinea-pig INIT in god mode; product changes stay inside **`realworld-api` + `realworld-meta`**; no new infra services.
2. A seated reader may **follow** a tag **by name** (establish an outgoing membership→tag follow edge).
3. A seated reader may **list** **only their own** followed tags (inspect own outgoing edges).
4. A seated reader may **unfollow** a tag they currently follow (dissolve that outgoing edge; same tag-name identity as follow).
5. Followed tags **persist durably** across sessions for the owning membership (brief delivery vehicle names Postgres; product lock is durable retention — storage engine is engineering).
6. **Feed personalization** (personalized / “your feed” membership driven by followed tags) is **out of scope** for this INIT — edges are retained, not applied to discovery ranking this INIT.
7. **Web UI** for this feature is **out of scope** for this INIT; stewardship is proven on the **machine-consumable API surface** of `realworld-api` (API contract notes may appear in product write-up; routes/payloads stay out of REQ text).
8. Success bar named by Lead: **follow + list + unfollow** work for the owning user; unauthenticated calls **fail closed**.
9. **(This grill)** “Signed-in reader” means a **seated member** under INIT-REALWORLD-001 seat rules; guests and post-logout actors are unseated.
10. **(This grill)** A followed tag is a **directed private edge** from owning membership → tag name — not INIT-002 **author** follow/subscription, not INIT-001 favorites, not INIT-003 parked search memory, not a public social-graph edge.
11. **(This grill)** Ownership isolation is load-bearing: peer members must not list, inspect, establish-on-behalf-of, or dissolve another member’s tag-follow edges; unseated follow/list/unfollow fail closed.
12. **(This grill)** **Anti-reciprocity this INIT:** there is no product surface that discloses which members follow a given tag (no inbound follower index, counts, or actor lists).
13. **(This grill)** Follow edges **persist across unseat/reseat** for the same membership (logout drops the seat, not the edges); after reseat, owner list reflects edges that existed before logout unless changed while seated.
14. **(This grill)** Empty own outgoing-edge set is a valid outcome (including after dissolving the last edge).
15. **(This grill)** Establishing / dissolving a tag-follow edge does **not** change public tag-lane membership, global bulletin membership, or INIT-002 subscription-stream membership this INIT; public lanes remain tag-true and ungated for guests.
16. **(This grill)** Owner list must expose each outgoing edge’s **tag name** so edge fidelity is observable without a UI this INIT.
17. **(This grill)** Empty or whitespace-only tag name is **not** a valid edge target (reject follow; no edge created).
18. **(This grill)** At most **one outgoing edge per tag name** per membership for prove expectations (re-follow of an already-edged name does not create a second distinct edge — OQ-02 default).
19. **(This grill)** **Non-composition:** tag-follow edges and INIT-002 author-follow edges are separate graphs; holding both does not merge inventories or rewrite either stream/lane membership this INIT.
20. **(This grill)** Concurrent independence: when Member A and Member B both follow the same tag name, each holds a **distinct** private edge; dissolving A’s edge must not dissolve B’s.
21. **(This grill)** Route paths, payload layouts, frameworks, and module names stay out of product REQ text; engineering consumes the WHAT + CTR absence + OQs.

## 3. In scope / non-goals

### In scope

**Sibling scope boundary (INIT-REALWORLD-001 / 002 / 003):** This INIT owns **membership→tag follow edges** only (CAP-01–CAP-03 / REQ-01–REQ-18). It does **not** re-own INIT-001 favorites / public tag-lane requirement ids, INIT-002 author-subscription / subscription-stream requirement ids, or INIT-003 parked-search requirement ids. Public lanes, author subscriptions, and parks remain baseline and are not reopened here.

- Seated establishment of a private membership→tag follow edge by tag name.
- Seated inspection (list) of **own** outgoing tag-follow edges (populated or empty) with tag-name fidelity.
- Seated dissolution of an **own** outgoing tag-follow edge.
- Durable retention of edges across unseat/reseat for the owning membership.
- Fail-closed denial for unseated follow / list / unfollow.
- Fail-closed isolation so peers cannot observe or mutate another’s outgoing edges.
- Explicit anti-reciprocity: no inbound “who follows this tag” disclosure this INIT.
- Explicit non-composition with INIT-002 author-follow / subscription-stream surfaces.
- Explicit non-application: edges must not rewrite public discovery membership this INIT.
- Product write-up in `realworld-meta`; implementation ownership on `realworld-api` only for this feature surface.

### Non-goals (load-bearing)

- **Feed personalization**, ranking, or any “articles matching my followed tags” timeline membership as a required success path this INIT.
- Settings (or any) **web UI** for edge management or “topics I follow” screens this INIT (`realworld-web` feature work deferred).
- New infra services beyond existing catalog services.
- Reopening INIT-REALWORLD-001 publish / seat / favorites / nameplate / public tag-lane requirement sets.
- Reopening INIT-REALWORLD-002 author subscription / subscription-stream rules.
- Reopening INIT-REALWORLD-003 parked search memory rules.
- Public **who-follows-this-tag** social proof (counts, actor lists, or reverse-index queries).
- Treating tag-follow as author-follow, or composing silent “author-subscription ∩ tag-follow” discovery.
- Comments, OAuth, email verification, mobile/native clients.
- Admin/moderation tooling over other members’ tag-follow edges.
- Cross-member transfer or export programmes.
- C1-style **topic watchlist collection stewardship** as the primary product noun (parked as OST fork A / C1).
- C2-style **interest-signal ledger aimed at future ranking** as the primary product noun (parked as OST fork B / C2).
- C3-style **tag-lane re-entry bookmarks / resume roster** as the primary product noun (parked as OST fork C / C3).

## 4. Actors

| Actor | Can actually | Cannot / OQ |
|-------|----------------|-------------|
| Guest (unseated) | Continue INIT-001 ungated bulletin / public tag-lane browse unchanged by this INIT | Establish/list/dissolve tag-follow edges; observe any member’s outgoing edges; query inbound followers of a tag |
| Seated member (owner) | Establish, inspect, dissolve **own** membership→tag follow edges; see own outgoing set after reseat with tag names intact | Observe or mutate a peer’s edges; keep stewardship after logout; force personalized feed this INIT; require UI this INIT; discover who else follows a tag |
| Peer member | Steward only their own outgoing tag-follow edges (including independently following the same tag name as another member) | Inspect, establish-as, or dissolve another member’s edges; harvest another’s interests via list, direct access, or reverse-index |
| Programme UAT / API prove observer | Drive owner vs peer vs unseated vs concurrent-same-tag paths against `realworld-api` to judge the kill assumption | Not an in-product role; must not require web UI this INIT |

## 5. Capabilities

| ID | Capability | Journeys covered | Notes |
|----|------------|------------------|-------|
| CAP-01 | Establish a private membership→tag follow edge | J-01, J-02, J-08, J-11, J-13, J-17 | Seated follow by tag name; edge target = tag name; empty name refused; corpus-empty target allowed (OQ-01); idempotent re-establish (OQ-02) |
| CAP-02 | Inspect and dissolve own outgoing tag-follow edges | J-01, J-03, J-04, J-08, J-10, J-13, J-15, J-17 | List with name fidelity; unfollow dissolves; empty set valid; persist across reseat; re-establish after dissolve; distinct from search parks |
| CAP-03 | Follow-edge privacy, anti-reciprocity, and non-composition | J-05, J-06, J-07, J-09, J-12, J-14, J-16, J-17, J-18 | Peer opacity; unseated fail-closed; missing/non-owned dissolve denied; no inbound follower index; concurrent same-tag independence; edges do not rewrite public lanes, bulletin, subscription stream, or peer edges |

Divergence from C1/C2/C3: C1 packaged **owner-private topic watchlist** (follow → list → unfollow as interest-collection stewardship). C2 packaged **durable topic-interest signal ledger** (assert → recall → withdraw with ranking-oriented non-application). C3 packaged **private tag-lane re-entry bookmarks** (pin → recall roster → unpin with lane-resume intent). C4 packages **private membership→tag follow edges** — establish → inspect outgoing → dissolve with **directed-edge semantics**, **anti-reciprocity**, **concurrent edge independence**, and **non-composition** with the author-follow graph.

## 6. Requirements

| ID | CAP | Requirement (WHAT) | Condition / event | Observable result | Evidence |
|----|-----|--------------------|-------------------|-------------------|----------|
| REQ-01 | CAP-01 | Establish a private membership→tag follow edge by tag name | Seated member follows a tag using a non-empty tag name | An owner-private outgoing edge exists for that tag name; owner outgoing list includes that name exactly once | live (CAP-01, J-01) |
| REQ-02 | CAP-03 | Refuse establish while unseated | Guest or post-logout actor attempts to follow a tag | No new tag-follow edge is created for any membership | live (CAP-03, J-07) |
| REQ-03 | CAP-02 | Inspect only the owner’s outgoing tag-follow edges with name fidelity | Seated member requests their followed-tag list when they own zero or more outgoing edges | List contains exactly that member’s followed tag names (or empty); no other member’s edges appear; each name appears at most once | live (CAP-02, J-03) |
| REQ-04 | CAP-02 | Dissolve an owned outgoing tag-follow edge | Seated member unfollows a tag name they currently follow | That tag name no longer appears on the owner’s outgoing edge list | live (CAP-02, J-04) |
| REQ-05 | CAP-02 | Persist tag-follow edges across unseat and reseat | Seated member follows a tag, logs out, then logs in again without changing edges while unseated | After reseat, owner list still includes that tag name | live (CAP-02, J-08) |
| REQ-06 | CAP-02 | Allow empty own-list after the last dissolve | Seated member unfollows their last remaining followed tag | Owner outgoing edge list is empty and valid (not an error wall) | live (CAP-02, J-10) |
| REQ-07 | CAP-03 | Keep one member’s outgoing tag-follow edges invisible to another seated member | Member A owns ≥1 outgoing edge; Member B is seated and is not A | B cannot obtain A’s outgoing edge set via list or direct access | live (CAP-03, J-06) |
| REQ-08 | CAP-03 | Refuse dissolve of another member’s tag-follow edge | Seated peer attempts to unfollow a tag on Member A’s outgoing set (or otherwise remove A’s edge) | A’s outgoing edge set unchanged; peer’s own list unchanged by that attempt | live (CAP-03, J-09) |
| REQ-09 | CAP-03 | Deny list / unfollow while unseated | Guest or post-logout actor attempts list or unfollow | No outgoing edge contents of any member are disclosed as a successful list result; no unfollow side effects | live (CAP-03, J-07) |
| REQ-10 | CAP-03 | Refuse unfollow of a missing or non-owned edge | Seated member attempts unfollow against a tag they do not currently follow (or a non-owned edge identity) | Own list unchanged; fail closed (OQ-03 default) | unit / live (CAP-03, J-12) |
| REQ-11 | CAP-01 | Refuse establish of empty or whitespace-only tag name | Seated member attempts to follow empty or whitespace-only tag name | No edge is created; owner list unchanged by that attempt | live (CAP-01, J-11) |
| REQ-12 | CAP-03 | Keep public tag-lane membership independent of own tag-follow edges | Seated member follows ≥1 tag then uses public tag-lane / bulletin discovery | Public discovery membership remains tag-true and unpersonalized by this INIT’s edges; guest browse unchanged | live (CAP-03, J-05) |
| REQ-13 | CAP-02 | Allow re-establish after dissolve | Seated member unfollows a tag they followed, then follows that same tag name again | Owner list again includes that tag name exactly once | live (CAP-02, J-13) |
| REQ-14 | CAP-03 | Keep subscription-stream membership independent of tag-follow edges | Seated member who holds INIT-002 author subscriptions also follows ≥1 tag | Subscription-stream membership remains driven by author subscriptions only; tag-follow edges do not add/remove stream articles this INIT | live (CAP-03, J-14) |
| REQ-15 | CAP-02 | Keep tag-follow edges distinct from parked search memory | Seated member who owns ≥1 INIT-003 parked search also follows ≥1 tag | Owner outgoing list lists tag names only; parked search recall remains a separate object and is not rewritten by tag follow/unfollow this INIT | live (CAP-02, J-15) |
| REQ-16 | CAP-03 | Keep peers’ public lane browse unaffected by owner edges | Member A follows ≥1 tag; Member B (or a guest) browses the corresponding public tag lane | Public lane membership for B/guest stays tag-true; A’s private edge does not gate, hide, or personalize that lane for others | live (CAP-03, J-16) |
| REQ-17 | CAP-03 | Keep concurrent same-tag edges independent across members | Member A and Member B both follow the same tag name; then A unfollows that tag | B’s outgoing list still includes that tag name; A’s no longer does; no shared/merged edge | live (CAP-03, J-17) |
| REQ-18 | CAP-03 | Refuse inbound follower disclosure for a tag | Any actor attempts to obtain which members follow a given tag (counts or actor list) via a product surface of this INIT | No successful disclosure of follower membership for that tag; owner-only outgoing list remains the sole follow-inspection path | live (CAP-03, J-18) |

## 7. Negative and failure paths

| REQ | Condition | Required behavior | Why it matters |
|-----|-----------|-------------------|----------------|
| REQ-03 / J-03 | Owner has zero outgoing edges | Empty list, still seated-only | Empty ≠ error; matches success “list works” |
| REQ-03 | Owner has edges | Listed names match established tags; at most once each | Edge fidelity observable without UI |
| REQ-02 / REQ-09 | Unseated follow/list/unfollow | Fail closed; no disclosure; no mutations | Kill assumption — seat gate |
| REQ-07 / J-06 | Peer tries to read owner’s outgoing edges | Isolation holds; no interest harvest | Kill assumption — unauthorized cannot see others’ follows |
| REQ-08 / J-09 | Peer tries to remove owner’s edge | Target unchanged | Isolation beyond read opacity |
| REQ-06 / J-10 | Last edge dissolved | Empty own-list allowed | Prevents “must always follow one tag” false rule |
| REQ-10 / J-12 | Unfollow when not following / non-owned | Fail closed; own list unchanged | Prevents cross-owner leakage via guessed identities |
| REQ-11 / J-11 | Empty / whitespace tag name | Establish refused; no record | Edge targets must be real tag names |
| REQ-12 / J-05 | Owner follows then browses public lanes | Public discovery not rewritten by edges | Load-bearing non-goal: no personalization this INIT |
| REQ-13 / J-13 | Dissolve then re-establish same name | Edge returns once | Continuity of edge lifecycle beyond one-shot CRUD |
| REQ-14 / J-14 | Owner has author subscriptions + tag edges | Subscription stream unchanged by tag edges | Noun / graph separation from INIT-002 |
| REQ-15 / J-15 | Owner has parked searches + tag edges | Objects stay separate | Noun / surface separation from INIT-003 |
| REQ-16 / J-16 | Owner follows; peer/guest browses that lane | Public lane stays ungated and unpersonalized for others | Private edge is not a lane ACL |
| REQ-17 / J-17 | Two members follow same tag; one unfollows | Only the actor’s edge dissolves | Directed edges are membership-scoped, not shared |
| REQ-18 / J-18 | Actor seeks inbound followers-of-tag | No disclosure this INIT | Anti-reciprocity — kills social-harvest side door |

## 8. Contract seeds (semantic)

None — no cross-repo product seam in this INIT. Tag-follow edge stewardship is owned and proven on `realworld-api`; `realworld-web` UI is an explicit non-goal; `realworld-meta` carries product truth only.

## 9. NFR applicability

| Area | Requirement or N/A rationale |
|------|------------------------------|
| Security | Seat-bound stewardship; unseated and peer access fail closed (REQ-02, REQ-07–REQ-10). No inbound who-follows-tag surface (REQ-18). Edges are not lane ACLs (REQ-16). |
| Reliability | N/A beyond fail-closed follow/list/unfollow behavior — not a multi-region SLA INIT. |
| Performance / capacity | N/A for guinea-pig scale; no concurrent-load target locked (per-member count limits → OQ-04). |
| Observability | N/A as product REQ — operational logging is engineering choice. |
| Privacy / data handling | Outgoing tag-follow edges are private to the owning membership; peers and guests must not observe the set (REQ-07, REQ-09) or reverse-index it (REQ-18). |
| Migration / compatibility | Additive private state for existing members; default empty own outgoing set. Does not migrate or rewrite INIT-001 favorites, INIT-002 author-follow edges, or INIT-003 parks. Does not rewrite public lane membership this INIT. |
| Rollback / recovery | N/A as product REQ — delivery rollback is engineering. |
| Operations / support | No new infra services; prove against existing `realworld-api` (local compose may host prove without expanding product scope to web UI). |

## 10. Assumptions

| ID | Assumption | Status | Dependent REQs | Default if false |
|----|------------|--------|----------------|------------------|
| A-01 | INIT-REALWORLD-001 contribution-seat semantics (login seats, logout unseats) remain the gate for “signed-in reader” | accepted-for-draft | REQ-02, REQ-05, REQ-09 | If seat meaning changed, reopen with Lead before drafting alternate REQs |
| A-02 | Tag-follow is a distinct product object from INIT-002 author subscription; “follow” in this INIT means membership→tag edge only | accepted-for-draft | REQ-01–REQ-18 | If Lead intended author-follow reuse, kill this INIT’s noun and reopen |
| A-03 | Durable retention means membership-scoped persistence across logout/login, not merely in-process memory | accepted-for-draft | REQ-05 | Session-only memory fails the brief’s persist intent |
| A-04 | Two distinct gates apply: (a) **unseated fail-closed** for follow/list/unfollow (guests and post-logout actors), and (b) **peer / inbound opacity** so seated peers cannot observe or reverse-index another member’s outgoing edges | accepted-for-draft | REQ-02, REQ-07, REQ-08, REQ-09, REQ-18 | If peer visibility or inbound follower lists were allowed, or if unseated mutate were soft-open, kill assumption would be incoherent — reopen with Lead |
| A-05 | Owner list exposing tag names is sufficient edge-fidelity proof without web UI or personalized feed this INIT | accepted-for-draft | REQ-03, REQ-12, REQ-16 | If UI navigation or feed personalization becomes kill-path, reopen scope with Lead |
| A-06 | Public tag-lane / bulletin discovery and INIT-002 subscription-stream rules remain baseline and are not rewritten by this INIT’s edges | accepted-for-draft | REQ-12, REQ-14, REQ-16 | If edges must alter lane or stream membership, that is a different INIT |
| A-07 | Membership→tag follow edge is a different product object from INIT-003 parked search memory | accepted-for-draft | REQ-15 | If Lead intended search-park reuse, kill this INIT’s noun and reopen |
| A-08 | “Follow edge” this INIT means durable directed ownership-bound relationship continuity, not a bidirectional social graph or public follower index | accepted-for-draft | REQ-07, REQ-17, REQ-18 | If inbound social proof is required for kill, reopen with Lead (conflicts with privacy kill bar) |
| A-09 | Concurrent same-tag follows by different members are independent edges, not a shared multiset row | accepted-for-draft | REQ-17 | If shared edges were intended, ownership isolation REQs would need redesign |

## 11. Open questions

| ID | Question | Owner | Blocking | Required-by | Default if deferred |
|----|----------|-------|----------|-------------|---------------------|
| OQ-01 | May a seated member establish an edge to a tag name whose public lane currently has zero articles, or must the tag already exist in the corpus? | PM | no | spec-draft | Allow edge to any non-empty normalized tag name even if no article currently carries it |
| OQ-02 | Is follow of an already-edged tag name idempotent success (still one outgoing edge), or a distinct conflict outcome? | PM | no | spec-draft | Idempotent success — outgoing list still shows the tag once |
| OQ-03 | Exact fail-closed shape for unfollow when not following vs non-owned / missing identity (indistinguishable not-found vs explicit forbidden) | PM | no | spec-draft | Indistinguishable not-found to the requester; no outgoing-edge contents disclosed |
| OQ-04 | Per-member maximum number of outgoing tag-follow edges and max tag-name length | PM | no | spec-draft | Eng reasonableness limits acceptable |
| OQ-05 | Owner outgoing-list ordering rule for prove expectations | PM | no | spec-draft | Newest-established-first; exact timestamp source left to eng |
| OQ-06 | Tag-name normalization (case folding, whitespace trim, unicode) for identity equality of establish/dissolve/list | PM | no | spec-draft | Trim outer whitespace; case-sensitive match as stored after trim (eng may document storage form) |
| OQ-07 | Whether establishing a tag-follow edge must appear as viewer-relative “following” state on public tag surfaces this INIT | PM | no | later | No — list/establish/dissolve on the private outgoing-edge surface is enough; public tag CTA state deferred |
| OQ-08 | Whether dissolving an edge leaves any owner-visible history of former tag follows | PM | no | later | Fully removed from owner outgoing list — no history surface this INIT |
| OQ-09 | Whether favorites (INIT-001) and tag-follow edges must stay mutually invisible in each other’s recall surfaces beyond the already-locked non-reopen | PM | no | later | Yes — favorites shelf and tag-follow outgoing list remain separate; no cross-write this INIT |
| OQ-10 | Whether any future programme may reverse-index tag-follow edges without a new INIT | PM | no | later | No — inbound follower disclosure requires a later INIT; this INIT’s anti-reciprocity stands |

## 12. Journeys

| ID | Actor | Trigger | Main flow | Primary edge | Abandon | Caps exercised |
|----|-------|---------|-----------|--------------|---------|----------------|
| J-01 | Seated member | Wants a durable follow relationship to a topic tag | Follows tag by name → lists → sees that name once as outgoing edge target | Already-edged → idempotent (OQ-02 default) | Abandons before follow → no edge | CAP-01, CAP-02 |
| J-02 | Seated member | Establishes an edge to a tag with no current article hits | Follows tag name absent from corpus (OQ-01 default) → lists → sees name | Empty public lane still edged | — | CAP-01 |
| J-03 | Seated member | Wants to see which tags they hold outgoing edges to | Opens own followed-tag / outgoing-edge list | Empty list when none established | Leaves without changes | CAP-02 |
| J-04 | Seated member | No longer wants a tag edge | Unfollows tag → lists → name absent | — | — | CAP-02 |
| J-05 | Seated member | Continues public discovery after establishing edges | Follows ≥1 tag → browses public tag lanes / bulletin | Lanes stay unpersonalized | Stops browsing | CAP-03 |
| J-06 | Peer member | Tries to harvest another’s tag interests | Attempts to list/access Member A’s outgoing edges | Denied / no disclosure | — | CAP-03 |
| J-07 | Guest / post-logout | Tries stewardship without a seat | Attempts follow, list, or unfollow | Fail closed; no side effects; no disclosure | — | CAP-03 |
| J-08 | Seated member | Relies on continuity across sessions | Follows tag → logs out → logs in → lists | Same tag name still present | — | CAP-01, CAP-02 |
| J-09 | Peer member | Tries to alter another’s outgoing edges | Attempts unfollow of A’s followed tag | A unchanged | — | CAP-03 |
| J-10 | Seated member | Clears the last edge | Unfollows final tag → lists empty | Empty is valid | — | CAP-02 |
| J-11 | Seated member | Tries to establish empty name | Attempts follow with empty/whitespace name | Refused; list unchanged | — | CAP-01 |
| J-12 | Seated member | Uses a bad unfollow target | Attempts unfollow on a tag they do not follow | Fail closed; own list unchanged | — | CAP-03 |
| J-13 | Seated member | Returns to a previously dissolved edge | Unfollows tag → follows same name again → lists | Name present once after re-establish | Abandons after unfollow → stays empty for that name | CAP-01, CAP-02 |
| J-14 | Seated member | Holds author subscriptions and tag-follow edges together | Has ≥1 author subscription; follows ≥1 tag; opens subscription stream | Stream membership ignores tag-follow edges | — | CAP-03 |
| J-15 | Seated member | Holds parked searches and tag-follow edges together | Owns ≥1 INIT-003 park; follows ≥1 tag; recalls parks and outgoing list | Objects remain separate; unfollow does not clear parks | — | CAP-02 |
| J-16 | Peer / guest | Browses a public lane that the owner edged | A follows tag X; B or guest opens public lane X | Lane stays ungated and tag-true for B/guest | — | CAP-03 |
| J-17 | Two seated members | Independently follow the same tag, then one leaves | A and B both follow tag X; A unfollows X; both list | A’s list lacks X; B’s list still has X | — | CAP-01, CAP-02, CAP-03 |
| J-18 | Any actor | Tries to learn who follows a tag | Attempts inbound followers-of-tag disclosure for tag X | No successful follower membership disclosure this INIT | — | CAP-03 |

Brief already listed follow / list / unfollow and unauthenticated fail-closed; **J-05** (public discovery stays unpersonalized), **J-08** (persist across reseat), **J-10** (empty after last dissolve), **J-11** (refuse empty name), **J-12** (missing unfollow), **J-13** (re-establish after dissolve), **J-14** (subscription stream independent), **J-15** (search-park separation), **J-16** (peer/guest lane browse unaffected), **J-17** (concurrent same-tag edge independence), and **J-18** (anti-reciprocity / no inbound follower index) are whole-product paths the outline did not spell out — and they distinguish membership→tag follow-edge packaging from C1 watchlist stewardship, C2 interest-signal ledger, C3 lane-bookmark roster, author subscription, and parked search memory.

## 13. Domain terms

| Term | Meaning in this INIT | Collision with existing product? |
|------|----------------------|----------------------------------|
| Membership→tag follow edge | Durable owner-private directed relationship from a seated membership to a tag name | New object; do **not** call this INIT-002 author subscription/follow, INIT-001 favorites, INIT-003 parked search, C1 “watchlist”, C2 “interest signal”, or C3 “lane bookmark” |
| Establish (follow tag) | Seated action that creates an outgoing membership→tag edge | Collides with everyday “follow” language used for **authors** in INIT-002 — always say **tag-follow edge / establish** in product prose |
| Dissolve (unfollow tag) | Seated action that removes an outgoing membership→tag edge | Same noun collision risk as follow |
| Outgoing edge list / own-list | The set of tag names the owning membership currently holds edges to | Distinct from favorites shelf, subscription stream, parked search recall, C1 watchlist packaging, C2 interest ledger packaging, and C3 re-entry roster packaging |
| Tag name / edge target | Identity string for the tag end of the edge; must re-present on owner list | Aligns with INIT-001 article tags / tag lanes; edges do not rewrite lane membership this INIT |
| Anti-reciprocity | Product rule that inbound “who follows this tag” disclosure is out of scope / denied this INIT | Distinguishes C4 from a public social graph; authors and peers get no follower harvest |
| Concurrent independence | Two members following the same tag hold distinct private edges | Distinguishes directed per-membership edges from a shared multiset |
| Non-composition | Tag-follow edges must not merge with or rewrite INIT-002 author-follow / subscription-stream membership this INIT | Explicit product rule for this cut |
| Owner | Seated membership that holds the outgoing edges; sole steward | Aligns with seat-bound ownership patterns; object is new |
| Unseated | Guest or post-logout actor under INIT-001 seat rules | Same seat vocabulary; no new auth product |
| Feed personalization | Using tag-follow edges to change which articles appear in a feed | Explicit **non-goal** this INIT |

---

## Discovery notes (not scored)

**Promote complete.** Think-4 content is the promoted PRD at `prd/INIT-REALWORLD-004.md` per Hermes promote brief (`recommend: C4`). Inline Challenge / Model / Stress provenance remains in locks and §1 OST fork; not open pipeline stops. Next: `/validate-requirements` (incremental after document updates) → `/prd-impact-map`.
