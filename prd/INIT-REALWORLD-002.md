# INIT-REALWORLD-002: Author-subscription trust with denial-honest empties

| Field | Value |
|-------|-------|
| Initiative | INIT-REALWORLD-002 |
| Status | promoted |
| Brief | Lead conversation (RealWorld U6 verification — helpful-army clarification rally) |
| Promoted from | `prd/reports/INIT-REALWORLD-002-prd-think-4.md` (C4 via `/prd-quality` + Hermes promote brief `recommend: C4`) |
| Score | `/prd-quality` — C4 recommended; promote authorized |
| Series | think 4 of 4 — diverges from `prd/reports/INIT-REALWORLD-002-prd-think.md` (C1 flat contract-fidelity buckets), `-2.md` (C2 shared-corpus vs social-layer), and `-3.md` (C3 mode honesty + cross-surface congruence); deliberately does **not** clone any earlier C-file’s CAP/REQ tables or INIT-001 bulletin/seat packaging |
| Product context | Sibling `prd/INIT-REALWORLD-001.md` (promoted; follow/personalized feed were non-goals); `config/service-catalog-drivestream-lab.yaml` (realworld-api, realworld-web, realworld-local, realworld-meta); `config/upstream.yaml` (gothinkster/realworld Conduit shape); `planning/` skipped (README only) |
| Companions | `/grilling`, `/domain-modeling`, `/opportunity-solution-tree`, `/strategy-red-team` not installed — inline Challenge / Model / Stress |
| Host mode | Non-interactive Hermes — T1 locks applied from Lead-approved brief; no AskQuestion |

## 1. Job and outcome

- **Job:** After INIT-REALWORLD-001’s bulletin/seat product has landed on meta, make **author subscription** trustworthy: a seated member can subscribe to another author’s published stream, see viewer-relative subscription state, and rely on a **subscription stream** whose membership is an honest projection of current subscriptions — while **public discovery stays ungated and unpersonalized**, and **empty streams plus fail-closed denials** are first-class product outcomes that agree with the RealWorld contracts already named for `realworld-api` ↔ `realworld-web`. Guests browse public articles without auth friction.
- **Why now:** U6 verification / helpful-army clarification rally needs a product write-up and Impact-Map that pin **subscription meaning + denial/empty honesty** so PE↔PM can settle disputes in ≤2 rounds, Lead can merge the meta product PR under coach-only Buzz (no `ack_pe`), and OKF knowledge heads can enrich after merge.
- **If we do nothing:** “Follow” stays an undefined social gesture; following feeds silently fill from the global corpus or miss publish/delete lifecycle; empty following looks like an error; guests hit auth walls on public browse; denials are soft/hidden instead of fail-closed; clarification has no locked product object; Lead cannot merge a coherent product PR; KB land-loop has nothing durable to open from.
- **Solution vs job:** Clarification rally, meta product PR, Impact-Map, and post-merge OKF enrichment are the **delivery vehicle** for this meta-lane wave. The job is **author-subscription trust + denial-honest empties** — not “run a ceremony,” not per-repo spec/impl PRs, not C1’s four peer fidelity buckets, not C2’s corpus/layer packaging, not C3’s mode-switch framing, and not a re-litigation of INIT-REALWORLD-001 seat/publish/favorites.
- **Kill assumption:** Fails if an unauthenticated guest cannot browse public articles without auth friction, or if a seated member’s subscription stream or author subscription state disagree with the named api↔web contracts (including silent global-fill of an empty stream, or stream membership that ignores subscribe/unsubscribe/publish/delete lifecycle), or if unseated/self/missing-author subscription attempts do not fail closed, or if those contract meanings remain unsettled after the ≤2-round PE↔PM clarification budget so Lead cannot merge.

## 2. Locked decisions

Product locks are those entailed by Hermes promote brief `locking` / `not_locking` plus grill consequences required for a coherent author-subscription / denial-honesty product (items 2–4, 6–16, 18). Items **1, 5, and 17** are **programme / delivery-vehicle notes** for this meta wave (still non-CAP) — they are **not** asserted as promote-brief product locks.

1. **(Programme note)** This wave is **meta product lane only**: clarify product write-up / Impact-Map for `realworld-api` + `realworld-web` contracts; land product PR on `realworld-meta` after PE↔PM agent clarification (≤2 rounds); enrich OKF knowledge heads after merge.
2. Members must see **article feed**, **tags**, and **author follow state** that match the RealWorld API contracts already named for this programme.
3. Guests must browse **public articles** without auth friction.
4. Out of scope for this wave: per-repo spec PRs, implementation PRs, IaC/QA hires.
5. **(Programme note)** Success signal: Lead sees **coach-only Buzz** (no `ack_pe`); after clarifications settle, Lead can merge the product PR; KB opens the knowledge-docs land loop.
6. **(This grill)** INIT-REALWORLD-001 bulletin + contribution-seat rules remain baseline and are **not** reopened here; this INIT adds author subscription and subscription-stream trust on top of that seat.
7. **(This grill)** Product cut is **author subscription + denial-honest empties**, not C1’s four peer fidelity buckets, not C2’s shared-corpus/social-layer split, and not C3’s discovery-mode honesty packaging: follow means subscribe-to-author; the following feed is that subscription’s stream; empty and denied outcomes are prove-first-class.
8. **(This grill)** “Author follow state” means the **viewer-relative subscription boolean** (whether the seated member currently subscribes to that author) — not public who-favorited proof, and not a requirement to expose follower/following **counts** as social proof (counts → OQ-01).
9. **(This grill)** Subscribe and unsubscribe are **membership actions**: they require a seated session; guests may complete public discovery without taking a seat; unseated subscribe/unsubscribe attempts fail closed.
10. **(This grill)** The **subscription stream** (following feed) is seated-only and **private to the subscriber**: published articles authored by authors the member currently subscribes to; empty stream is valid and must not silently become global membership; Guests must not observe another member’s stream as truth.
11. **(This grill)** Guests are not required to authenticate to read public article listings, open public articles, or use public tag surfaces; any subscribe CTA must not gate those reads; public discovery membership must not depend on the viewer’s subscriptions.
12. **(This grill)** Self-subscribe is refused; subscription targets are other members’ public authors only.
13. **(This grill)** Subscription edges **persist across unseat/reseat** for the same membership (logout drops the seat, not the subscriptions); after reseat, subscription state and stream membership reflect the edges that existed before logout unless changed while seated.
14. **(This grill)** Subscription-stream lifecycle is load-bearing: subscribe can add an author’s published articles; unsubscribe removes them; a subscribed author’s **new publish** appears in subscribers’ streams; a subscribed author’s **delete** removes that article from subscribers’ streams — without rewriting ungated public discovery rules beyond INIT-001 publish/delete already require.
15. **(This grill)** Tag surfaces stay **tag-true** under subscription churn: tag-lane membership does not become subscription-filtered.
16. **(This grill)** Denial honesty is load-bearing: unseated mutate, self-subscribe, and missing-author subscribe fail closed as product rules (not merely hidden controls); empty public listing, empty tag lane, and empty subscription stream are valid outcomes, not error walls.
17. **(Programme note)** Clarification budget is a load-bearing process constraint (≤2 PE↔PM rounds) on unsettled contract meaning — product REQs must be precise enough that “settled” is observable without inventing eng HOW.
18. **(This grill)** Comments, OAuth, email verification, mobile/native clients, reopening INIT-001 favorites/nameplate rules, mutual-friends packaging, silent following∩tag composition, and treating Buzz/OKF/clarification ceremony as product CAPs remain non-goals unless a later Lead lock says otherwise.

## 3. In scope / non-goals

### In scope

**Sibling scope boundary (INIT-REALWORLD-001):** REQ-01–REQ-06 re-prove / pin kill-path continuity for ungated public discovery and subscription-independent global listing on top of INIT-001 bulletin reading (`CAP-01` / `REQ-01`–`REQ-03` / `REQ-07` there). This INIT does **not** reopen or re-own INIT-001 requirement ids. New owned surface here is author-subscription + stream honesty (CAP-02–CAP-04 and REQ-07 onward).

- Ungated unpersonalized public discovery: public article listing, open published article, public tag surfaces — no account wall; subscribe CTA must not gate those reads; membership independent of viewer subscriptions.
- Seat-bound author subscribe / unsubscribe; viewer-relative subscription state; directed edges; persistence across unseat/reseat.
- Seated subscription stream (following feed) as honest projection of current subscriptions; empty stream allowed; no silent global fill; stream private to the subscriber.
- Subscription-stream lifecycle against INIT-001 publish/delete: new publish by subscribed author appears; deleted article leaves the stream.
- Global article listing for seated members stays subscription-independent (same unpersonalized membership claim as public discovery).
- Tag-true topic discovery under subscription churn.
- Denial-honest fail-closed outcomes: unseated mutate, self-subscribe, missing-author subscribe.
- Meta product write-up + Impact-Map that name the api↔web seams for subscription + denial/empty honesty so PE↔PM clarification can close ≤2 rounds and Lead can merge.
- Post-merge OKF knowledge-head enrichment as programme success continuation (not a product CAP).

### Non-goals (load-bearing)

- Per-repo **spec** PRs (api/web/local) in this wave.
- **Implementation** PRs in this wave.
- IaC / QA hiring or staffing actions.
- Reopening INIT-REALWORLD-001 publish / seat / favorites / nameplate requirement sets.
- Comments.
- OAuth / third-party identity.
- Email verification gates.
- Mobile or native clients.
- Public who-favorited social proof (carried forward as non-goal from INIT-001).
- Treating the clarification rally, Buzz channel shape, or OKF tooling as product capabilities with `CAP-*`/`REQ-*` (process vehicle only).
- Inventing a silent composed “subscription ∩ tag” discovery surface.
- Mutual-follow ceremony or “friends” packaging beyond directed subscriptions.
- Follower/following **counts** as social proof (deferred OQ-01).
- Leading with C2 Guest↔Member parity tables as the primary cut (parity may fall out of unpersonalized public discovery; it is not this candidate’s framing).
- Leading with C3 mode-switch blend prove as the primary cut (stream vs global distinction remains; switch choreography is not the job noun).
- API-only prove without acknowledging web as the member/guest journey surface for trust judgments once eng waves exist (meta wave itself proves via write-up/Impact-Map readiness).

## 4. Actors

| Actor | Can actually | Cannot / OQ |
|-------|----------------|-------------|
| Guest (unseated) | Complete ungated public discovery (listing, published open, tag surfaces, public author presentation) without auth friction | Subscribe/unsubscribe; obtain a subscription stream; observe another member’s stream or seated subscription state as authoritative truth; force contract meaning changes |
| Seated member | Everything a Guest can on public discovery; view subscription-independent global listing; steward own subscriptions; see viewer-relative subscription state; view own subscription stream | Subscribe to self; keep subscription **mutations** after logout; redefine named contracts unilaterally; make public discovery membership depend on own subscriptions; inspect another member’s stream |
| Author (subscription target) | Be subscribed/unsubscribed by others; have published articles appear in / leave subscribers’ streams on publish/delete | Control another member’s subscriptions; force own articles into a non-subscriber’s stream |
| Subscriber (role) | Seated member who currently holds a subscription to an Author | Not a separate identity — role label for stream journeys |
| Peer member | Second seated member for directed-subscription and stream-privacy journeys | Inspect or mutate another member’s private INIT-001 shelf or subscription stream; change contracts |
| Programme Lead | Merge meta product PR when clarification settles; judge coach-only Buzz success | Not an in-product role |
| PE / PM clarification agents | Raise/settle contract-meaning disputes within ≤2 rounds against the write-up | Not in-product actors; cannot invent scope outside locks |
| Programme UAT observer | Drive Guest/Member/Author journeys to judge the kill assumption once eng surfaces exist | Not an in-product role |

## 5. Capabilities

| ID | Capability | Journeys covered | Notes |
|----|------------|------------------|-------|
| CAP-01 | Ungated unpersonalized public discovery | J-01, J-02, J-03, J-09, J-10, J-14 | Public listing/open/tags; auth must not gate; membership independent of subscriptions |
| CAP-02 | Seat-bound author-subscription stewardship | J-04, J-06, J-07, J-10, J-12, J-13 | Subscribe/unsubscribe; viewer-relative state; persistence across reseat; self/missing denial owned with CAP-03 |
| CAP-03 | Denial-honest empties and fail-closed outcomes | J-07, J-08, J-10, J-12, J-15 | Empty stream/listing/lane as valid; unseated/self/missing denials fail closed; no silent global-fill |
| CAP-04 | Subscription-stream lifecycle honesty | J-05, J-06, J-08, J-11, J-14, J-15, J-16 | Stream ⊆ subscribed authors’ published articles; private to subscriber; publish-in and delete-out; global/tags stay unpersonalized |

Divergence intent (C4 vs C1/C2/C3): C1 framed four peer “contract-faithful” buckets; C2 reframed shared-corpus vs social layer (parity/persistence/publish-in); C3 reframed mode honesty + cross-surface congruence. C4 reframes the job as **author subscription** (follow = subscribe-to-author stream) with **denial-honest empties** as a first-class prove rung (mirroring INIT-001’s seat-denial elevation), and adds **delete-out of stream**, **stream privacy from Guest**, and **subscription persistence** as brief-omitted stress paths without cloning prior CAP tables.

## 6. Requirements

| ID | CAP | Requirement (WHAT) | Condition / event | Observable result | Evidence |
|----|-----|--------------------|-------------------|-------------------|----------|
| REQ-01 | CAP-01 | Present the public article listing without requiring authentication | Guest opens the public article listing | Listing state is visible (populated or empty) with no account wall | live (CAP-01, J-01) |
| REQ-02 | CAP-01 | Open a published article without requiring authentication | Guest selects a published article when at least one exists | Published content is readable while still unseated | live (CAP-01, J-01) |
| REQ-03 | CAP-01 | Use public tag surfaces without requiring authentication | Guest opens the tag catalog or a tag lane | Tag surface is usable; no account wall | live (CAP-01, J-02) |
| REQ-04 | CAP-01 | Keep public discovery available when a subscribe affordance is visible | Guest views a public author or article surface that offers subscribe to seated actors | Guest can still complete public listing/open/tag without authenticating | live (CAP-01, J-09) |
| REQ-05 | CAP-01 | Keep public discovery membership independent of the viewer’s subscriptions | Seated member subscribes or unsubscribes, then re-opens public listing and a tag lane | Public listing and tag-lane memberships do not add/remove articles solely because subscriptions changed | live (CAP-01, CAP-04, J-14) |
| REQ-06 | CAP-01 | Keep the seated global article listing subscription-independent | Seated member opens the global article listing when published articles exist | Membership agrees with the named global-feed contract and does not depend on the viewer’s subscriptions | live (CAP-01, J-03) |
| REQ-07 | CAP-02 | Subscribe to another author and show subscription state true | Seated member subscribes to an author they do not already subscribe to | Viewer-relative subscription state for that author becomes subscribed; subsequent seated views agree | live (CAP-02, J-04) |
| REQ-08 | CAP-02 | Unsubscribe from an author and show subscription state false | Seated member unsubscribes from an author they currently subscribe to | Viewer-relative subscription state becomes not-subscribed; subsequent seated views agree | live (CAP-02, J-04) |
| REQ-09 | CAP-02 | Persist subscriptions across unseat and reseat | Seated member subscribes to an author, logs out, then logs in again without changing edges while unseated | After reseat, viewer-relative subscription state for that author is still subscribed | live (CAP-02, J-13) |
| REQ-10 | CAP-03 | Refuse self-subscribe | Seated member attempts to subscribe to themselves | Subscription graph unchanged; subscription state toward self does not become subscribed | unit / live (CAP-03, J-07) |
| REQ-11 | CAP-03 | Deny subscribe and unsubscribe while unseated | Guest or post-logout actor attempts subscribe or unsubscribe | No subscription-edge change; fail closed | live (CAP-03, J-10) |
| REQ-12 | CAP-03 | Refuse subscribe of a missing or unknown author identity | Seated member attempts to subscribe to an author identity that does not exist | Subscription graph unchanged; fail closed (OQ-03 default) | unit / live (CAP-03, J-12) |
| REQ-13 | CAP-03 | Allow an empty subscription stream as a valid outcome | Seated member subscribes to zero authors (or subscribed authors have zero published articles) and opens the subscription stream | Empty stream state is shown; must not silently show global public membership; must not present as an auth or hard error wall | live (CAP-03, CAP-04, J-08) |
| REQ-14 | CAP-03 | Keep guest public discovery working after a member unseats | Member who previously used subscriptions logs out, then browses public articles/tags as Guest | Public discovery still works without auth friction; subscription mutations remain denied | live (CAP-01, CAP-03, J-10) |
| REQ-15 | CAP-04 | Present the subscription stream for the seated member | Seated member who subscribes to at least one author that has published articles opens the subscription stream | Stream shows only articles from authors that member currently subscribes to | live (CAP-04, J-05) |
| REQ-16 | CAP-04 | Remove an author’s articles from the subscription stream after unsubscribe | Seated member unsubscribes from an author who had articles in that stream | Those articles no longer appear in the subscription stream; public/global membership is unchanged by unsubscribe alone | live (CAP-04, J-06) |
| REQ-17 | CAP-04 | Include a subscribed author’s newly published article in the subscription stream | Seated member already subscribes to an author; that author then publishes a new tagged article | The new article appears in the subscriber’s subscription stream; public listing/tag membership update as public-discovery rules require without depending on who subscribes to whom | live (CAP-04, J-11) |
| REQ-18 | CAP-04 | Remove a deleted article from the subscription stream | Seated member subscribes to an author; that author deletes a published article that was in the subscriber’s stream | That article no longer appears in the subscription stream; Guest open-by-reference stays not-found per INIT-001 delete rules | live (CAP-04, J-16) |
| REQ-19 | CAP-04 | Keep the subscription stream private to the subscriber | Guest (or a peer who is not that subscriber) attempts to treat another member’s subscription stream as a public discovery surface | Other actors do not obtain that member’s stream membership as public truth; Guest public discovery remains the ungated surface | live (CAP-04, CAP-01, J-15) |
| REQ-20 | CAP-04 | Keep tag-lane membership tag-true under subscription churn | Member subscribes or unsubscribes without changing article tags | Tag lanes still reflect tag membership only — not subscription state | live (CAP-04, CAP-01, J-14) |

## 7. Negative and failure paths

| REQ | Condition | Required behavior | Why it matters |
|-----|-----------|-------------------|----------------|
| REQ-01 / REQ-03 | Empty bulletin / empty tag catalog | Empty states still ungated | Frictionless ≠ “must have content” |
| REQ-04 | Subscribe CTA visible to Guest | Public discovery still ungated | Prevents soft auth walls |
| REQ-05 / REQ-06 / REQ-20 | Subscription graph changes | Public/global/tag memberships do not silently become subscription-filtered | Unpersonalized discovery kill path |
| REQ-13 | Subscribing nobody / subscribed authors silent | Empty stream; not an error wall; not silently filled from global | Denial-honest empty kill path |
| REQ-16 / REQ-08 | After unsubscribe | Stream loses articles; subscription state false; global untouched by unsubscribe alone | Stream honesty |
| REQ-10 | Self-subscribe attempt | Fail closed | Graph integrity |
| REQ-11 / REQ-14 | Unseated subscribe cluster | Fail closed; guest public discovery remains open | Seat boundary + kill path |
| REQ-12 | Subscribe missing/unknown author | Fail closed; graph unchanged | No ghost edges |
| REQ-09 | Logout then login | Subscriptions still present after reseat; mutations still denied while unseated | Persistence ≠ keep seat |
| REQ-17 | Subscribed author publishes | Stream gains article; public/tag update as discovery, not “only for subscribers” | Lifecycle honesty |
| REQ-18 | Subscribed author deletes | Stream loses article; no ghost readable body via stream | Lifecycle honesty + INIT-001 delete coherence |
| REQ-19 | Guest/peer probing another’s stream | No public reveal of that stream membership | Stream privacy |
| Clarification budget | PE↔PM still disagree after 2 rounds on a named seam | Product PR is not merge-ready under Lock 5 | Process kill tied to product precision |

## 8. Contract seeds (semantic)

Cross-repo seam: `realworld-api` (provider) ↔ `realworld-web` (consumer). Cut by **ungated public discovery**, **author subscription stewardship**, **denial/empty honesty**, and **subscription-stream lifecycle**.

| ID | Provider | Consumer | Logical operation | Field meaning | Invariants | Errors |
|----|----------|----------|-------------------|---------------|------------|--------|
| CTR-01 | realworld-api | realworld-web | Read ungated unpersonalized public discovery | Public listing, single published article, public tag membership, public author presentation | Reading never requires a seat; only published articles appear; empty listing/lane allowed; membership does not depend on viewer subscriptions | Missing article; empty sets allowed |
| CTR-02 | realworld-api | realworld-web | Manage author subscriptions and report viewer-relative state | Subscribe / unsubscribe another author; report whether the seated viewer currently subscribes | Seat required to mutate; self-subscribe refused; missing author refused; directed edges; state true/false must match edge; edges persist across unseat/reseat; unseated mutate denied | Unauthenticated; self target; missing author |
| CTR-03 | realworld-api | realworld-web | Read subscription stream | Seated-only listing of published articles by currently subscribed authors | Stream ⊆ articles authored by currently subscribed authors; empty stream allowed; must not silently equal global membership when subscriptions are empty; stream is not a public discovery surface for other actors | Unauthenticated; empty sets allowed |
| CTR-04 | realworld-api | realworld-web | Keep tag-true discovery under subscription churn | Tag catalog and per-tag article membership | Lane membership reflects current tags only; independent of subscriptions; empty lane allowed; no silent subscription∩tag composition | Unknown tag → empty or not-found per OQ-04 |

## 9. NFR applicability

| Area | Requirement or N/A rationale |
|------|------------------------------|
| Security | Subscribe/unsubscribe fail closed while unseated (REQ-11). Self-subscribe refused (REQ-10). Guest public discovery must not be gated by auth (REQ-01–REQ-04, REQ-14). Missing-author subscribe refused (REQ-12). Subscription stream not a public reveal surface (REQ-19). |
| Reliability | N/A beyond fail-closed trust behavior — not a multi-region SLA INIT. |
| Performance / capacity | N/A for this meta clarification wave; no concurrent-load target locked. |
| Observability | N/A as product REQ — Buzz/coach signal is programme process, not a CAP. |
| Privacy / data handling | Viewer-relative subscription boolean is in scope; follower/following **counts** as social proof deferred (OQ-01). Guest must not be shown another viewer’s seated subscription state or stream as authoritative truth (REQ-19, OQ-05). No who-favorited proof. |
| Migration / compatibility | Builds on INIT-REALWORLD-001 clean-slate corpus; no separate tenant migration programme. Subscriptions are additive social state, not a rewrite of INIT-001 favorites. Stream lifecycle must stay coherent with INIT-001 publish/delete. |
| Rollback / recovery | N/A as product REQ — meta PR rollback is delivery process. |
| Operations / support | Meta merge + post-merge OKF enrichment are success continuation; 24×7 support envelope not locked. |

## 10. Assumptions

| ID | Assumption | Status | Dependent REQs | Default if false |
|----|------------|--------|----------------|------------------|
| A-01 | INIT-REALWORLD-001 seat/bulletin rules stay in force; this INIT does not weaken guest read or seated contribution gates | accepted-for-draft | REQ-01, REQ-11, REQ-14 | Re-open with Lead before drafting conflicting REQs |
| A-02 | Named RealWorld programme contracts for global feed, following feed, tags, and follow edges already exist as api↔web meaning to pin (upstream Conduit shape); “follow” maps to author subscription here | accepted-for-draft | REQ-06–REQ-18, CTR-01–CTR-04 | If a named contract is missing, mint OQ and block Impact-Map seam row — do not invent eng payloads |
| A-03 | “Auth friction” means any requirement to authenticate before completing public listing/tag/open | accepted-for-draft | REQ-01–REQ-04, REQ-14 | Soft walls that block public discovery fail the kill assumption even if marketing copy says optional |
| A-04 | Empty subscription stream is valid and must not silently fall back to global membership | accepted-for-draft | REQ-13 | If product later wants fallback, that is a new Lock — not silent behavior |
| A-05 | Meta-lane delivery (write-up, Impact-Map, ≤2 clarification rounds, merge, OKF enrich) is how this INIT lands; eng spec/impl are later waves | accepted-for-draft | All | Do not treat absence of impl PRs in this wave as product failure |
| A-06 | Viewer-relative subscription boolean is sufficient for “author follow state”; counts are optional/deferred | accepted-for-draft | REQ-07, REQ-08 | If Lead requires counts, resolve OQ-01 into REQs |
| A-07 | Logout unseats but does not wipe the membership’s subscription graph; reseat restores the same edges | accepted-for-draft | REQ-09 | If Lead wants ephemeral subscriptions-per-session, replace Lock 13 and REQ-09 |
| A-08 | Subscription-stream publish-in and delete-out are required for lifecycle honesty; mid-view push without re-open is not required for meta write-up | accepted-for-draft | REQ-17, REQ-18 | If Lead requires live push without re-check, resolve OQ-06 |
| A-09 | Denial-honest empties are a primary trust bar for this candidate; C3 mode-switch choreography and C2 parity tables are not required as primary CAP framing | accepted-for-draft | REQ-13, REQ-10–REQ-12, REQ-19 | If Lead prefers mode/parity nouns on promote, prefer C3/C2 framing |

## 11. Open questions

| ID | Question | Owner | Blocking | Required-by | Default if deferred |
|----|----------|-------|----------|-------------|---------------------|
| OQ-01 | Are public follower/following **counts** in scope as contract fields, or only the viewer-relative subscription boolean? | PM | no | spec-draft | Boolean subscription state only; counts out of scope for this INIT |
| OQ-02 | Ordering rule for global listing vs subscription stream when both are available to a member | PM | no | spec-draft | Newest-first by the same publish/update time rule as INIT-001 OQ-06 default; exact timestamp source left to eng |
| OQ-03 | Behavior when subscribe/unsubscribe targets a missing or deactivated author identity | PM | no | spec-draft | Fail closed; subscription graph unchanged (REQ-12) |
| OQ-04 | Unknown tag: empty lane vs distinct not-found for UAT expectations | PM | no | spec-draft | Empty lane for unknown/blank-normalized tags; do not show unrelated articles |
| OQ-05 | Whether Guest may observe another viewer’s subscription state (always false / omitted) on public profiles without authenticating | PM | no | spec-draft | Omit seated-only subscription state for Guest; show subscribe affordance without gating public discovery (REQ-04); do not present another member’s edges or stream as Guest truth |
| OQ-06 | Whether unsubscribe of the last subscribed author must transition UI chrome explicitly to empty stream without the member re-opening the stream | PM | no | later | Same visit after re-check/re-open is enough; mid-view push not required for meta write-up |
| OQ-07 | Whether PE↔PM clarification rounds are counted per seam (CTR) or per product PR conversation thread | PM | no | later | Per product PR conversation; ≤2 rounds total before Lead merge decision |
| OQ-08 | Whether a composed “subscription ∩ tag” surface is ever offered | PM | no | spec-draft | Separate surfaces only; no composed third surface in this INIT |
| OQ-09 | Whether a seated member viewing their **own** public author presentation may see a disabled self-subscribe affordance or no affordance at all | PM | no | spec-draft | No successful self-subscribe path; chrome may hide or disable — either is fine if REQ-10 holds |
| OQ-10 | Whether already-subscribed subscribe attempts must be distinguishable from first subscribe for UAT, or both simply leave state subscribed | PM | no | later | Both leave state subscribed; no error required if graph unchanged |
| OQ-11 | Whether subscription-stream delete-out must be proven in the same visit as the author’s delete without re-open | PM | no | later | Next open of the stream after delete is enough for meta write-up / later UAT |

## 12. Journeys

| ID | Actor | Trigger | Main flow | Primary edge | Abandon | Caps exercised |
|----|-------|---------|-----------|--------------|---------|----------------|
| J-01 | Guest | Wants public articles without signing in | Opens public listing → opens a published article when present → reads | Empty listing → still ungated | Leaves without registering | CAP-01 |
| J-02 | Guest | Explores topics | Opens tag catalog/lane → scans → opens a matching article when present | Empty lane for that tag only | Leaves tags | CAP-01 |
| J-03 | Seated member | Checks unpersonalized global listing | Opens global article listing → confirms membership matches named global-feed contract and is not subscription-filtered | Empty global listing still readable | Leaves listing | CAP-01 |
| J-04 | Seated member | Builds / clears a subscription | Opens an author’s public presentation → subscribes → sees subscription state true → unsubscribes → sees false | Self-subscribe attempt → refused (enters J-07) | Cancels without subscribe | CAP-02 |
| J-05 | Seated member | Uses the subscription stream | Subscribes to an author who has published articles → opens subscription stream → opens one such article | If author has no articles → empty stream (J-08) | Unsubscribes (enters J-06) | CAP-04 |
| J-06 | Seated member | Proves stream honesty after unsubscribe | Unsubscribes from an author → subscription state false → stream loses that author’s articles → global listing unchanged by unsubscribe alone | Last unsubscribe → empty stream | N/A — unsubscribe is the act | CAP-04, CAP-02 |
| J-07 | Seated member | Attempts self-subscribe | Tries to subscribe to own author identity | Graph unchanged; denial observed | Returns to other authors | CAP-03, CAP-02 |
| J-08 | Seated member | Opens stream with nothing to show | Subscribes to zero authors (or subscribed authors silent) → opens subscription stream | Empty state; must not silently show global membership; not an error wall | Switches to global listing | CAP-03, CAP-04 |
| J-09 | Guest | Sees subscribe affordance while browsing | Views public author/article surface that offers subscribe to seated actors → continues public discovery without authenticating | If Guest tries subscribe → denied (J-10) | Leaves | CAP-01 |
| J-10 | Seated → Guest | Unseats after using subscriptions | Subscribes to someone → logs out → completes public listing/open as Guest → attempts subscribe/unsubscribe | Public discovery works; mutations fail closed | Reseats (J-13) | CAP-01, CAP-03, CAP-02 |
| J-11 | Author + Subscriber | Subscribed author publishes | Subscriber already subscribes to Author → Author publishes new tagged article → Subscriber opens subscription stream | New article in stream; public/tag update as ungated discovery for all readers | Subscriber unsubscribes first | CAP-04 |
| J-12 | Seated member | Targets a missing author | Attempts subscribe on unknown author identity | Fail closed; graph unchanged (OQ-03) | Returns to known authors | CAP-03 |
| J-13 | Seated member | Proves subscription persistence across reseat | Subscribes to an author → logs out → logs in → checks subscription state (and stream if author has articles) | State still subscribed; mutations were denied while unseated | Abandons reseat | CAP-02 |
| J-14 | Seated member | Proves public/tag stay unpersonalized under churn | Subscribes/unsubscribes while checking public listing, global listing, and a tag lane | Memberships unchanged by subscriptions alone | Stops probing | CAP-01, CAP-04 |
| J-15 | Guest + Peer | Prove stream privacy | Guest (and/or a peer who is not the subscriber) attempts to treat Member A’s subscription stream as public discovery | A’s stream membership is not revealed as public truth; Guest stays on ungated public discovery | Stops probing | CAP-04, CAP-03 |
| J-16 | Author + Subscriber | Subscribed author deletes | Subscriber already has Author’s article in stream → Author deletes that article → Subscriber opens subscription stream | Article gone from stream; Guest open-by-reference not-found | Subscriber unsubscribes first | CAP-04 |

Brief-omitted paths used to break outline-echo and C1/C2/C3-echo: J-08 empty-stream honesty as primary, J-11 publish-in lifecycle, J-16 delete-out lifecycle, J-15 stream privacy from Guest/peer, J-13 persistence across reseat, plus J-06/J-07/J-09/J-10/J-12/J-14 boundary paths. (C3 mode-switch blend and C2 Guest↔Member parity tables are intentionally not the job nouns here.)

## 13. Domain terms

| Term | Meaning in this INIT | Collision with existing product? |
|------|----------------------|----------------------------------|
| Author subscription | Directed seated-member → author relationship created by subscribe (follow) and removed by unsubscribe (unfollow) | Product noun for this candidate; RealWorld “follow” maps here |
| Subscription state | Viewer-relative boolean: whether the seated member currently subscribes to that author | Same meaning as C1–C3 “author follow state”; renamed for subscription framing |
| Subscription stream | Seated-only listing of published articles authored by authors the member currently subscribes to | Same surface as RealWorld following feed; was INIT-001 non-goal “personalized feed” |
| Denial-honest empty | Empty listing/lane/stream or fail-closed denial presented as valid product outcome — not an error wall and not a silent fill from another surface | C4-specific prove idea (elevated like INIT-001 seat denial) |
| Unpersonalized public discovery | Public listing, published open, and tag surfaces whose membership does not depend on viewer subscriptions and never requires a seat | Framing term; overlaps INIT-001 bulletin reading |
| Auth friction | Any requirement to authenticate before completing public listing/tag/open | Framing term for guest kill path |
| Stream privacy | A member’s subscription stream is not a public discovery surface for Guests or peers | C4-specific; stronger than “seated-only chrome” alone |
| Clarification budget | ≤2 PE↔PM agent rounds to settle named contract meaning before Lead merge decision | Process constraint; not a CAP |
| Coach-only Buzz | Lead-visible success signal without `ack_pe` | Process success; not a product REQ |
| Meta product lane | Write-up + Impact-Map + meta PR + post-merge OKF enrich — this wave’s delivery vehicle | Distinct from eng spec/impl lanes |

---

## Discovery notes (not scored)

**T0 Gather (provenance):** Brief = Lead U6 helpful-army clarification outline (conversation). INIT = INIT-REALWORLD-002. Think output path was `prd/reports/INIT-REALWORLD-002-prd-think-4.md` (C4). Catalog + upstream + sibling INIT-001 read. Prior candidates = `prd/reports/INIT-REALWORLD-002-prd-think.md` (C1), `-2.md` (C2), `-3.md` (C3). Promoted content now lives at `prd/INIT-REALWORLD-002.md`.

**T1 Challenge (inline):** Challenged “clarification rally / land meta PR / OKF enrich” as the job. Recommended job: **author-subscription trust + denial-honest empties** (not C1 flat fidelity buckets, not C2 corpus/layer cut, not C3 mode/congruence packaging, not process-only ceremony). Solution vs job aligned — no hard-stop fork. Product locks 2–4 from Lead/promote cut; programme notes 1/5/17 (delivery vehicle, non-CAP); locks 6–16, 18 added as necessary grill consequences (INIT-001 baseline, subscription cut, follow-state = viewer boolean, seat-gated mutate, stream private + empty-valid, no guest auth wall, no self-subscribe, persistence across reseat, publish-in/delete-out lifecycle, tag-true under churn, denial honesty, keep comments/OAuth/etc. out).

**T2 Model (inline) — OST fork:**

| Outcome | Verdict |
|---------|---------|
| **A. Author-subscription trust + denial-honest empties** (subscribe-to-author; stream lifecycle including delete-out; empty/denied as first-class; stream privacy; meta write-up pins api↔web seams) | **Recommended for this INIT (C4)** |
| B. C1-style four peer contract-fidelity buckets | Rejected for this candidate — already written as C1; C4 must diverge |
| C. C2-style shared-corpus honesty + seated social layer (parity primary) | Rejected for this candidate — already written as C2; C4 must diverge |
| D. C3-style mode honesty + cross-surface congruence | Rejected for this candidate — already written as C3; C4 must diverge |
| E. Process-only ceremony PRD (Buzz/OKF/clarification as CAP/REQ) | Rejected — `/spec-draft` cannot implement ceremony; silent product gap |
| F. Full social platform (comments + counts-as-proof + OAuth + mutual-friends + subscription∩tag) | Rejected — contradicts load-bearing non-goals |
| G. Re-cut INIT-001 bulletin/seat | Rejected — already promoted; Lock 6 |

**T3 Stress (inline, ≤5 claims):**

| Claim | Fails if | Cheapest test | Verdict |
|-------|----------|---------------|---------|
| Guest completes public discovery without auth friction | Account wall or soft gate blocks listing/open/tag | Live J-01 + J-02 + J-09 | Survivor → REQ-01–REQ-04, REQ-14 |
| Public/global/tag stay unpersonalized under subscription churn | Subscriptions rewrite public discovery membership | Live J-03 + J-14 | Survivor → REQ-05, REQ-06, REQ-20 |
| Subscription stream is lifecycle-honest and private | Empty stream fills from global; publish-in/delete-out wrong; Guest sees another’s stream | Live J-05 + J-06 + J-08 + J-11 + J-15 + J-16 | Survivor → REQ-13, REQ-15–REQ-19 |
| Subscriptions mutate only while seated; persist across reseat; self/missing refused | Guest can subscribe, self-subscribe sticks, edges vanish on logout, or missing author creates ghost edge | Live J-04 + J-07 + J-10 + J-12 + J-13 | Survivor → REQ-07–REQ-12 |
| Meta write-up is precise enough for ≤2-round settle + Lead merge | Seams still ambiguous after budget | Inspection of CTR seeds vs Impact-Map (later `/prd-impact-map`) | Survivor as programme note 17 (delivery vehicle) — not a product REQ row |

**Promote complete.** Think-4 content is the promoted PRD at `prd/INIT-REALWORLD-002.md` per Hermes promote brief (`recommend: C4`). Discovery Challenge / Model / Stress above are retained as provenance, not as open pipeline stops. Next: `/validate-requirements` (incremental after document updates) → `/prd-impact-map`.
