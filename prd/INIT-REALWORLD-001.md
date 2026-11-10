# INIT-REALWORLD-001: Public bulletin with session-bound contribution seat

| Field | Value |
|-------|-------|
| Initiative | INIT-REALWORLD-001 |
| Status | promoted |
| Brief | Lead conversation (Wave0a UAT clean-slate RealWorld Conduit outline) |
| Promoted from | `prd/reports/INIT-REALWORLD-001-prd-think-4.md` (C4 via `/prd-quality` + Hermes promote brief `recommend: C4`) |
| Score | `/prd-quality` — C4 recommended; promote authorized |
| Series | think 4 of 4 — diverges from `prd/reports/INIT-REALWORLD-001-prd-think.md`, `-2.md`, and `-3.md` |
| Product context | `config/service-catalog-drivestream-lab.yaml` (realworld-api, realworld-web, realworld-local); `config/upstream.yaml` (gothinkster/realworld Conduit shape); `planning/` skipped (README only); no sibling INIT PRDs |
| Companions | `/grilling`, `/domain-modeling`, `/opportunity-solution-tree`, `/strategy-red-team` not installed — inline Challenge / Model / Stress |
| Host mode | Non-interactive Hermes — T1 locks applied from Lead-approved brief; no AskQuestion |

## 1. Job and outcome

- **Job:** Give Wave0a UAT a **public bulletin** anyone can read without an account, and a **contribution seat** that a person obtains only by registering and logging in — so they can place tagged markdown onto that bulletin, keep a private shelf of others’ writing, and revise their public nameplate — and that seat must drop the instant they log out while the bulletin stays open.
- **Why now:** Wave0a UAT needs a clean-slate Conduit-shaped object whose pass/fail is the three kill paths (guest bulletin read, seated auth+publish, post-logout seat denial), before social-graph RealWorld surfaces are added.
- **If we do nothing:** There is no UAT-demonstrable public bulletin with a hard contribution seat; guest browse and member publish cannot be shown together, and logout cannot be shown to drop the seat.
- **Solution vs job:** “RealWorld Conduit (API + web)” is the delivery vehicle (catalog: `realworld-api` + `realworld-web`, local prove via `realworld-local`). The job is bulletin openness + seat lifecycle + the three kill paths — not comments, follows, personalized feeds, OAuth, or who-favorited proof.
- **Kill assumption:** Fails if an unauthenticated guest cannot browse the global feed and open a published article, or a registered member cannot authenticate and publish a tagged article into that feed, or membership actions (publish, favorite, profile self-update) still work after logout.

## 2. Locked decisions

Lead-approved brief treated as T1 locks (applied; not re-asked), plus grill consequences required for a coherent bulletin/seat product:

1. Guests (no account) may browse the global feed, open published articles, use tag lanes, and view public profiles.
2. Membership means register and log in; log out ends the session and revokes membership privileges.
3. Members may publish, edit, and delete only their own tagged markdown articles.
4. Newly published articles are immediately visible (no draft queue, no moderation queue).
5. Members may favorite or unfavorite other people’s articles; the favorite list is private to the member.
6. Members may update their own profile.
7. After logout, publish / favorite / profile self-update are unavailable until login again; guest reading remains open.
8. Out of scope: mobile and native clients, comments, follow graphs, personalized feeds, email verification, OAuth, and public who-favorited social proof.
9. Wave0a live prove surface is the web client against the API in the local compose environment (`realworld-web`, `realworld-api`, `realworld-local`).
10. Favoriting targets only articles authored by someone else.
11. Publish requires at least one tag (kill path language: “tagged article”).
12. Password recovery, account deletion, and admin/moderation roles are out of scope for Wave0a.
13. **(This grill)** The contribution seat is the unit of privilege: register creates eligibility; log in seats the actor; log out unseats; re-login reseats. Reading the bulletin never requires a seat.
14. **(This grill)** Seat denial is a product rule, not merely hidden controls: unauthenticated or post-logout attempts at publish / favorite / profile self-update fail closed even if the actor reaches the action.
15. **(This grill)** After unseat, the actor may still read the bulletin as a Guest — including their own previously published articles and public profiles — without regaining contribution actions.
16. **(This grill)** Private shelf means isolation across members as well as from guests; Member B cannot inspect Member A’s favorites.
17. **(This grill)** Nameplate ownership: a seated member may change only their own public profile; attempts to change another member’s profile fail closed.
18. **(This grill)** No server-side draft: an unfinished compose that never successfully publishes leaves the bulletin unchanged; abandon or unseat mid-compose creates no published article.
19. **(This grill)** Empty bulletin is a valid start; first successful seated tagged publish is what makes guest article-open proveable on a clean slate.
20. **(This grill)** Returning authentication (log in) is required for the kill-path “authenticate and publish”; registration alone is eligibility, not the seated session.

## 3. In scope / non-goals

### In scope

- Public bulletin reading without a seat: global feed, article open, tag lanes, public profiles, empty-bulletin and empty-lane states.
- Contribution seat lifecycle: register (eligibility), log in (seat), log out (unseat), re-login (reseat); product-level denial while unseated.
- Seated bulletin contribution: publish tagged markdown with immediate visibility; bootstrap empty bulletin.
- Seated own-work revision: edit/delete own articles only; ownership denial across members; tag-set consistency with lanes; refuse zero-tag create/edit.
- Private shelf (favorites) with inter-member isolation; own-article favorite refused; shelf must not resurrect deleted articles’ public readability.
- Own nameplate self-update; peer nameplate mutation denied; updates visible on subsequent public reads.
- Continuous UAT stories that chain guest read → seat → publish → unseat → deny → reseat.
- Wave0a UAT prove of the three kill paths on web against API.

### Non-goals (load-bearing)

- Mobile or native clients.
- Comments.
- Follow / unfollow graphs or follower counts.
- Personalized / “your feed” timelines.
- Email verification as a gate on register or publish.
- OAuth / third-party identity.
- Public who-favorited social proof (counts or actor lists as social proof).
- Draft or moderation queues before visibility (including any durable server draft).
- Password reset / recovery.
- Account deletion or data-export programmes beyond ordinary profile self-update.
- Admin / moderator / staff tooling.
- Multi-device session cascade beyond “explicit logout unseats *this* session” (see OQ-05).
- API-only prove without the web UAT surface.
- Mid-action transport interruption / network-timeout recovery as a Wave0a UAT prove surface (seat/deny fail-closed rules still apply when an action never succeeds).

## 4. Actors

| Actor | Can actually | Cannot / OQ |
|-------|----------------|-------------|
| Guest (unseated) | Read global feed, open published articles, use tag lanes, view public profiles (empty states allowed) — including after a prior logout | Publish; favorite; change any profile; inspect any private shelf |
| Visitor (pre-member) | Attempt registration; remain Guest if refused or abandoned | Contribution seat until an authenticated session exists |
| Seated member | Everything a Guest can on public bulletin surfaces; publish/edit/delete own tagged articles; favorite/unfavorite others’ articles; update own nameplate; log out | Mutate others’ articles or nameplates; favorite own articles; keep the seat after logout; inspect another member’s shelf; use non-goal social features |
| Author | Seated member acting as owner of a specific article | Author rights on articles they do not own |
| Peer member | Second seated member in collision journeys (ownership, shelf privacy, nameplate ownership) | Rights over the first member’s articles, shelf, or nameplate |
| Programme UAT observer | Drive Guest / Seated / Peer paths to judge the kill assumption | Not an in-product role |

## 5. Capabilities

| ID | Capability | Journeys covered | Notes |
|----|------------|------------------|-------|
| CAP-01 | Public bulletin reading | J-01, J-02, J-03, J-04, J-12, J-14, J-17 | Feed, article open, tag lanes, public profiles — never requires a seat |
| CAP-02 | Contribution seat lifecycle | J-05, J-06, J-07, J-08, J-11, J-14, J-17, J-18 | Register eligibility, seat via login, unseat via logout, reseat, product-level denial while unseated |
| CAP-03 | Seated bulletin contribution | J-06, J-08, J-12, J-14, J-18 | Tagged publish into the bulletin; immediate visibility; empty-bulletin bootstrap; refuse unseated / zero-tag publish |
| CAP-04 | Seated own-work revision | J-09, J-10, J-15 | Edit/delete own articles; tag-set lane moves; refuse zero-tag edit; peer ownership denial |
| CAP-05 | Private shelf | J-07, J-08, J-09, J-13, J-16 | Favorites on others’ articles; inter-member isolation; unseated denial; no public social proof; no resurrection of deleted articles |
| CAP-06 | Own nameplate | J-07, J-08, J-13, J-19 | Self-update only; peer nameplate mutation denied; public reads reflect updates; unseated denial |

Divergence from think-1/2/3: job framed as **bulletin + contribution seat** (not commons/fence/library-stewardship); **favorites (CAP-05) and profile (CAP-06) are separate prove rungs**; seat lifecycle (CAP-02) owns admission+exit+denial together; publish (CAP-03) stays separate from ongoing revision (CAP-04); post-unseat guest reading of own prior work and peer nameplate attack are first-class.

## 6. Requirements

| ID | CAP | Requirement (WHAT) | Condition / event | Observable result | Evidence |
|----|-----|--------------------|-------------------|-------------------|----------|
| REQ-01 | CAP-01 | Present the global feed without requiring a contribution seat | Guest opens the bulletin | Guest sees the published-article listing state (populated or empty) with no account wall | live (CAP-01, J-01) |
| REQ-02 | CAP-01 | Open a published article without a contribution seat | Guest selects a published article when at least one exists | Full published content is readable while still unseated | live (CAP-01, J-01) |
| REQ-03 | CAP-01 | Browse a tag lane without a contribution seat | Guest selects a tag | Guest sees only published articles that currently carry that tag (or an empty lane for that tag) | live (CAP-01, J-02) |
| REQ-04 | CAP-01 | View a public profile without a contribution seat | Guest opens an existing member’s public profile | Public presentation is visible; that member’s published articles are discoverable from it (list may be empty) | live (CAP-01, J-03) |
| REQ-05 | CAP-01 | Allow tag-hop discovery from a published article | Guest reading an article follows one of its tags into a tag lane | Guest lands on the lane for that tag and can open another matching article when one exists | live (CAP-01, J-04) |
| REQ-06 | CAP-01 | Show a multi-tagged article in every matching lane | A published article carries two or more tags; Guest opens each of those tag lanes | The same article appears in each lane for its current tags | live (CAP-01, J-04) |
| REQ-07 | CAP-01 | Keep bulletin reading available after the actor unseats | Member logs out then opens the global feed and a published article (including one they authored while seated) | Feed and article remain readable; no contribution seat is required | live (CAP-01, J-17) |
| REQ-08 | CAP-02 | Register a new membership (eligibility) | Visitor submits registration with identity+credentials accepted by product rules (field/uniqueness set deferred to OQ-01; Wave0a default: unique username + unique email + password) | A membership record exists; actor can obtain a seat via log in | live (CAP-02, J-05) |
| REQ-09 | CAP-02 | Refuse registration that collides with an existing membership identity | Visitor registers with a taken identity | No second membership is created; actor is told registration did not succeed; no seat granted from that attempt | unit / live (CAP-02, J-05) |
| REQ-10 | CAP-02 | Seat an existing member by authenticating | Registered member submits valid credentials | Authenticated session exists; contribution seat is active | live (CAP-02, J-06) |
| REQ-11 | CAP-02 | Refuse seating with invalid credentials | Actor submits credentials that do not match a membership | No authenticated session; contribution seat inactive | unit / live (CAP-02, J-11) |
| REQ-12 | CAP-02 | Unseat on logout and revoke contribution actions | Authenticated member logs out | Publish, favorite, and profile self-update are unavailable until a later successful login; bulletin reading remains available | live (CAP-02, J-07) |
| REQ-13 | CAP-02 | Reseat after re-login | Previously logged-out member authenticates again with valid credentials | Publish, favorite, and profile self-update are available again | live (CAP-02, J-07) |
| REQ-14 | CAP-02 | Deny contribution actions while unseated at the product rule layer | Guest or post-logout actor attempts publish, favorite/unfavorite, and profile self-update | Each attempt fails closed; no new article, no shelf change, no profile change | live (CAP-02, J-08) |
| REQ-15 | CAP-03 | Publish a tagged markdown article into the bulletin | Seated member publishes with markdown body and ≥1 tag | Article is immediately visible in the global feed and each of its tag lanes; Guests can open it; it appears among the author’s public-profile articles | live (CAP-03, J-06) |
| REQ-16 | CAP-03 | Refuse publish when zero tags are provided | Seated member attempts to publish with no tags | No new published article appears in the bulletin | unit / live (CAP-03, J-06) |
| REQ-17 | CAP-03 | Bootstrap an empty bulletin via first seated publish | Bulletin has zero published articles; a seated member then publishes a tagged article | Guest global feed becomes non-empty and Guest can open that article | live (CAP-03, J-12) |
| REQ-18 | CAP-03 | Refuse publish when the actor is unseated | Guest or post-logout actor attempts to publish | No new published article is created | live (CAP-03, J-08) |
| REQ-19 | CAP-03 | Leave the bulletin unchanged when compose is abandoned or interrupted by unseat | Seated member starts composing but logs out or abandons without a successful publish | No new published article appears | live (CAP-03, J-18) |
| REQ-20 | CAP-04 | Edit only own published articles | Author changes title, body, and/or tags on an article they own | Subsequent reads show the updated published content; visibility remains immediate | live (CAP-04, J-09) |
| REQ-21 | CAP-04 | Keep tag lanes consistent after tag-set edit | Author changes an article’s tags | Article appears in lanes for its new tags and no longer appears in lanes for removed tags | live (CAP-04, J-15) |
| REQ-22 | CAP-04 | Refuse an edit that would leave zero tags | Author attempts to save an update with an empty tag set | Article’s prior published content and tag lanes remain unchanged | unit / live (CAP-04, J-15) |
| REQ-23 | CAP-04 | Delete only own published articles | Author deletes an article they own | Article disappears from global feed, tag lanes, and author public-profile article list; Guest open-by-reference no longer shows published content | live (CAP-04, J-09) |
| REQ-24 | CAP-04 | Refuse edit or delete of another author’s article | Peer member attempts to change or remove an article they do not own | That article’s content and bulletin presence are unchanged | live (CAP-04, J-10) |
| REQ-25 | CAP-05 | Favorite another author’s article onto a private shelf | Seated member favorites an article they do not own | Article appears on that member’s private shelf; no public who-favorited social proof is shown | live (CAP-05, J-13) |
| REQ-26 | CAP-05 | Unfavorite a previously favorited article | Seated member removes a favorite | Article no longer appears on that member’s private shelf | live (CAP-05, J-13) |
| REQ-27 | CAP-05 | Keep one member’s private shelf invisible to another member | Member A has favorited an article; Member B is seated and is not A | Member B cannot inspect A’s private shelf | live (CAP-05, J-16) |
| REQ-28 | CAP-05 | Refuse favorite of own article | Seated member attempts to favorite an article they authored | Private shelf unchanged for that attempt | unit / live (CAP-05, J-13) |
| REQ-29 | CAP-05 | Deny favorite actions after unseat | Post-logout actor attempts favorite/unfavorite | Private shelf remains unchanged | live (CAP-05, J-07) |
| REQ-30 | CAP-06 | Update own nameplate so public readers see the change | Seated member changes allowed public profile fields (editable set deferred to OQ-03; Wave0a default: bio and image editable; username/email identity-locked) | Subsequent Guest (and Member) public-profile views show the updated editable public fields | live (CAP-06, J-13) |
| REQ-31 | CAP-06 | Refuse update of another member’s nameplate | Peer member attempts to change Member A’s profile | A’s public profile remains unchanged | live (CAP-06, J-19) |
| REQ-32 | CAP-06 | Deny nameplate self-update after unseat | Post-logout actor attempts profile self-update | Profile remains unchanged | live (CAP-06, J-07) |
| REQ-33 | CAP-05 | Keep a private-shelf pointer from resurrecting a deleted article’s public readability | Author deletes a published article that still has (or previously had) a favorite/shelf pointer | Private shelf must not expose the deleted article’s published body to any actor; Guest open-by-reference remains not-found (OQ-08 default) | live (CAP-05, J-09) |

## 7. Negative and failure paths

| REQ | Condition | Required behavior | Why it matters |
|-----|-----------|-------------------|----------------|
| REQ-01 | Bulletin has zero articles | Empty feed state; still no account wall | Open bulletin ≠ “must have content to be ungated” |
| REQ-03 | Tag with no articles | Empty lane for that tag only — not other tags’ articles | Prevents false discovery |
| REQ-07 | After logout, actor reads own prior article | Readable as Guest; contribution still denied | Separates bulletin openness from seat |
| REQ-09 | Duplicate registration identity | Fail closed; no second membership; no seat | Protects eligibility integrity |
| REQ-11 | Invalid credentials | No seat; contribution stays off | Protects seat gate |
| REQ-12 | After logout | Contribution unavailable; reading still works | Kill assumption — unseat |
| REQ-14 / REQ-18 | Unseated contribution cluster | Fail closed; no side effects | Kill assumption — gate; product rule not chrome |
| REQ-16 / REQ-22 | Zero-tag create or edit | No create; no destructive empty-tag save | Enforces tagged-article lock |
| REQ-19 | Abandon / unseat mid-compose | Bulletin unchanged; no draft artifact | Reinforces no-draft lock |
| REQ-24 | Cross-author mutate | Bulletin unchanged | Ownership integrity |
| REQ-27 | Peer tries to view another’s shelf | Isolation holds | Privacy beyond “no public social proof” |
| REQ-28 | Favorite own article | Refused; shelf unchanged | Lock 10 |
| REQ-29 / REQ-32 | Post-logout shelf/nameplate | No mutation | Kill assumption — unseat on personal surfaces |
| REQ-31 | Peer nameplate attack | Target profile unchanged | Nameplate ownership |
| REQ-33 / J-09 / A-03 | Shelf still pointing at a deleted article | Deleted article must not become publicly readable again via the private shelf; Guest open-by-reference stays not-found | Prevents ghost public content |
| J-05 abandon | Visitor abandons registration mid-flow | Remains Guest; no partial seat | Avoid half-open seat |
| J-14 | Guest mid-read then takes a seat | Reading remains open through conversion; publish only after seated | Proves bulletin stays open across seat change |

## 8. Contract seeds (semantic)

Cross-repo seam: `realworld-api` (provider) ↔ `realworld-web` (consumer). Cut by bulletin / seat / contribute / revise / shelf / nameplate.

| ID | Provider | Consumer | Logical operation | Field meaning | Invariants | Errors |
|----|----------|----------|-------------------|---------------|------------|--------|
| CTR-01 | realworld-api | realworld-web | Read the public bulletin | Global listing, tag-filtered listing, single published article, public profile (+ author’s published articles) | Only published articles appear; Guests may read; multi-tag articles belong to every listed tag’s set; no draft/moderation states; reading never requires a seat | Missing article; empty sets allowed |
| CTR-02 | realworld-api | realworld-web | Manage the contribution seat | Register unique identity+credentials (eligibility; field/uniqueness set per OQ-01 default); authenticate into a seated session; explicit logout unseats; later authenticate reseats | Contribution actions require a valid seat; bulletin reading never requires a seat; unseat and reseat both observable | Duplicate identity; invalid credentials; malformed required identity fields; session already absent → treat as unseated |
| CTR-03 | realworld-api | realworld-web | Contribute to the bulletin | Create own markdown articles with ≥1 tag; immediate visibility | Seat required; zero tags rejected; abandon/unseat without success creates nothing | Unauthenticated; zero tags |
| CTR-04 | realworld-api | realworld-web | Revise own bulletin work | Update/delete own articles; tag-set changes move lane membership; ≥1 tag on any update that supplies the tag set | Ownership required; zero tags rejected; peer mutate denied | Unauthenticated; not owner; zero tags; missing article |
| CTR-05 | realworld-api | realworld-web | Maintain private shelf | Favorite/unfavorite others’ articles on a private list | Shelf private and isolated across members; no who-favorited social proof; unseated denied; own-article favorite denied; shelf pointer must not resurrect a deleted article’s published body (REQ-33) | Unauthenticated; own article; missing article; peer inspection denied; deleted article |
| CTR-06 | realworld-api | realworld-web | Maintain own nameplate | Self-update allowed public profile fields (editable set per OQ-03 default: bio/image; username/email identity-locked); Guests may read public profile | Only owner may update; unseated denied; peer update denied; updates reflected on subsequent public reads | Unauthenticated; not owner |

## 9. NFR applicability

| Area | Requirement or N/A rationale |
|------|------------------------------|
| Security | Contribution seat must keep publish / favorite / profile self-update closed to Guests and post-logout actors as a product rule (REQ-12, REQ-14, REQ-18, REQ-29, REQ-32). Credential verification fail-closed (REQ-11). Peer nameplate mutation denied (REQ-31). No OAuth in this INIT. |
| Reliability | N/A beyond fail-closed UAT behavior — not a multi-region SLA INIT. Mid-action network/timeout interruption is out of Wave0a UAT scope; when an action does not complete, no partial publish / shelf / nameplate mutation is required to be proven beyond ordinary fail-closed absence of success. |
| Performance / capacity | N/A for Wave0a UAT scale; no concurrent-load target locked. |
| Observability | N/A as product REQ — operational logging is engineering choice, not a kill criterion. |
| Privacy / data handling | Private shelves isolated across members (REQ-25, REQ-27). No public who-favorited proof. Shelf must not resurrect deleted articles (REQ-33). Nameplate exposes only fields treated as public (OQ-03). |
| Migration / compatibility | Clean-slate — no prior tenant corpus migration required. |
| Rollback / recovery | N/A as product REQ — delivery rollback is engineering. |
| Operations / support | `realworld-local` compose is the intended live-prove environment; no 24×7 support envelope locked. |

## 10. Assumptions

| ID | Assumption | Status | Dependent REQs | Default if false |
|----|------------|--------|----------------|------------------|
| A-01 | Registration uniqueness covers the identifiers RealWorld-style memberships customarily treat as unique (username and email both unique) | accepted-for-draft | REQ-08, REQ-09 | If only one identifier is unique, fail closed on that one and record via OQ-01 |
| A-02 | Markdown is the authored body format; “readable published content” is the kill bar, not pixel-perfect renderer parity | accepted-for-draft | REQ-02, REQ-15 | Rich media beyond markdown stays non-goal |
| A-03 | Author delete removes public bulletin presence; private shelf entries must not resurrect public readability | accepted-for-draft | REQ-23, REQ-25, REQ-26, REQ-33 | Private tombstone-only retention may be specified later — public resurrection still forbidden |
| A-04 | Explicit logout defines unseat for Wave0a; idle-timeout is not required to pass the kill assumption | accepted-for-draft | REQ-12 | If idle timeout becomes required, add REQ after OQ — do not block draft |
| A-05 | Tags are author-chosen free-form labels, not a curated taxonomy | accepted-for-draft | REQ-03, REQ-06, REQ-15, REQ-16, REQ-21, REQ-22 | Curated taxonomy would replace A-05 via OQ-02 |
| A-06 | “Until login again” implies reseat on successful re-authentication is in scope (Lock 13) | accepted-for-draft | REQ-13 | If reseat were out of scope, kill-path language would be incoherent — reopen with Lead |
| A-07 | Inter-member shelf isolation is required by “private list” in the brief, not only absence of public social proof (Lock 16) | accepted-for-draft | REQ-27 | If privacy meant only “no public proof,” drop REQ-27 via CHG — still keep social proof non-goal |
| A-08 | Unfinished compose has no durable server-side draft artifact (Lock 18) | accepted-for-draft | REQ-19 | If client-only scratch is allowed, it must still vanish without publishing on abandon/unseat |

## 11. Open questions

| ID | Question | Owner | Blocking | Required-by | Default if deferred |
|----|----------|-------|----------|-------------|---------------------|
| OQ-01 | Exact required registration fields and uniqueness set (username, email, password; bio/image at register vs nameplate-only) | PM | no | spec-draft | Unique username + unique email + password at register; bio/image optional via nameplate self-update |
| OQ-02 | Tag normalization rules (case folding, max count/length, blank-token rejection beyond zero-tag rule) | PM | no | spec-draft | Free-form; reject blank tags; ≥1 non-blank tag required; other limits left to eng reasonableness |
| OQ-03 | Nameplate fields editable via self-update vs identity-locked (bio/image vs username/email) | PM | no | spec-draft | Bio and image editable; username/email identity-locked for Wave0a |
| OQ-04 | Whether successful registration may optionally seat immediately, in addition to the required log-in path for returning members | PM | no | spec-draft | Registration creates eligibility only; actor uses log in before first contribution (clearest kill-path “authenticate”) |
| OQ-05 | Whether a second concurrent session must also unseat when one client logs out | PM | no | later | Wave0a proves unseat on the logging-out session only; cross-session cascade out of scope |
| OQ-06 | Global feed ordering rule for UAT expectations | PM | no | spec-draft | Newest-first by publish/update time; exact timestamp source left to eng |
| OQ-07 | Behavior when favoriting a missing or already-deleted article | PM | no | spec-draft | Fail closed (not-found); private shelf unchanged |
| OQ-08 | Whether Guest open-by-reference after delete shows a stable not-found state vs generic empty | PM | no | spec-draft | Stable not-found; must not show prior published body |
| OQ-09 | Whether a Guest mid-read must refresh to observe an author’s delete, or next navigation is sufficient for UAT | PM | no | later | Next navigation / reopen is sufficient; live mid-read push not required for Wave0a |

## 12. Journeys

| ID | Actor | Trigger | Main flow | Primary edge | Abandon | Caps exercised |
|----|-------|---------|-----------|--------------|---------|----------------|
| J-01 | Guest | Wants to see what is published | Opens global feed → when content exists, opens an article → reads | Empty bulletin → empty feed, still ungated | Leaves without registering | CAP-01 |
| J-02 | Guest | Follows a topic | Opens a tag lane → scans → opens a matching article | Empty tag lane → empty state for that tag only | Leaves lane | CAP-01 |
| J-03 | Guest | Curious about an author | Opens public profile → sees public fields → opens one of that author’s articles when present | Profile with zero articles → profile visible, empty list | Leaves profile | CAP-01 |
| J-04 | Guest | Continues discovery across tags | Reads a multi-tagged article → follows each tag → confirms article in each lane → opens another matching article when present | Sole article in a lane → lane shows only that article | Stops after one hop | CAP-01 |
| J-05 | Visitor → eligible member | Decides to join | Registers with unique identity → membership exists → logs in per Lock 20 / OQ-04 | Duplicate identity → refused; remains Guest | Abandons form; remains Guest with no seat | CAP-02 |
| J-06 | Seated member | Puts writing onto the bulletin | Authenticates → composes tagged markdown → publishes → Guest can see it in feed, tag lanes, and author profile | Zero tags → publish refused | Logs out before publish; no article | CAP-02, CAP-03 |
| J-07 | Seated → Guest → Seated | Ends then resumes the seat | Logs out → contribution actions denied → bulletin reading still works → logs in again → contribution works again | Stale membership chrome must not succeed at contribution while unseated | N/A — logout/login are the acts | CAP-02, CAP-05, CAP-06 |
| J-08 | Guest | Probes the seat | Attempts publish, favorite, and profile self-update while unseated | Each attempt fails closed with no side effects | Registers (enters J-05) | CAP-02, CAP-03, CAP-05, CAP-06 |
| J-09 | Author | Fixes or removes own writing | Edits and/or deletes own article → bulletin reflects update or removal | After delete, Guest cannot read it as published content; any private-shelf pointer must not resurrect public readability (REQ-33) | Cancels edit; prior published version remains | CAP-04, CAP-05 |
| J-10 | Peer member | Attacks ownership | Attempts edit/delete on another author’s article | Bulletin unchanged; denial observed | Returns to own articles | CAP-04 |
| J-11 | Member | Uses valid vs invalid seating | Login succeeds with good credentials; separately, bad credentials refused | Invalid login leaves seat inactive | Stops trying | CAP-02 |
| J-12 | Seated member + Guest | Bootstraps the bulletin | Starting from zero articles, seated member publishes first tagged article → Guest feed shows it → Guest opens it | If publish fails, bulletin stays empty and Guest still sees empty ungated feed | Member abandons compose; bulletin stays empty | CAP-01, CAP-03 |
| J-13 | Seated member | Uses private shelf and own nameplate | Favorites another author’s article → sees private shelf → unfavorites; updates own nameplate → Guest sees updated public fields | Attempt to favorite own article → refused | Leaves shelf unused; cancels nameplate edit | CAP-05, CAP-06 |
| J-14 | Guest → Seated | Converts mid-read | Guest reads a published article → registers → logs in → publishes own tagged article into the same bulletin | If login skipped (per OQ-04 default), contribution still unavailable until seated | Abandons join; remains Guest still able to read | CAP-01, CAP-02, CAP-03 |
| J-15 | Author | Retags published writing | Edits tag set on own article → verifies lane membership moves; attempts empty tag set → refused | Reader in an old lane no longer finds the article there after tag removal | Cancels edit; prior tags remain | CAP-04 |
| J-16 | Peer member | Probes shelf privacy | Member A favorites an article; Member B attempts to inspect A’s shelf | B cannot see A’s favorites; A’s shelf unchanged by B’s probe | B favorites the same article into B’s own private shelf instead | CAP-05 |
| J-17 | Former seated member (now Guest) | Confirms bulletin stays open after unseat | Logs out → opens global feed → opens an article they authored while seated → reads as Guest | Contribution actions on that same visit still fail closed | Leaves without reseating | CAP-01, CAP-02 |
| J-18 | Seated member | Abandons compose / unseats mid-compose | Starts composing a tagged article → logs out or abandons without publish → Guest feed unchanged | Partial client compose state must not create a published article | N/A — abandon/unseat is the act | CAP-02, CAP-03 |
| J-19 | Peer member | Attacks nameplate ownership | Attempts to change another member’s public profile | Target profile unchanged; denial observed | Returns to own nameplate | CAP-06 |

Brief-omitted paths used to break outline-echo: J-04 multi-tag hop, J-07 unseat+reseat, J-08 guest probe, J-10 peer ownership attack, J-12 empty-bulletin bootstrap, J-14 mid-read conversion, J-15 retag revision, J-16 shelf privacy, J-17 post-unseat guest read of own prior work, J-18 abandon/unseat mid-compose, J-19 peer nameplate attack.

## 13. Domain terms

| Term | Meaning in this INIT | Collision with existing product? |
|------|----------------------|----------------------------------|
| Guest / unseated | Actor without an authenticated contribution seat; may read the public bulletin only | None in meta catalog |
| Member | Actor with a membership record; contribution requires a seated session | None |
| Contribution seat | Authenticated session that enables publish, favorite, and nameplate self-update; obtained by login, dropped by logout | Framing term for this candidate |
| Eligibility | Membership record created by registration; not itself a seat | Specific to this candidate’s Lock 20 |
| Bulletin | Shared published space: global feed + tag lanes + openable published articles | Framing synonym for commons/library in earlier thinks — same product surface |
| Membership privilege / contribution action | Publish, favorite, and profile self-update — available only while seated | Matches kill-assumption wording |
| Session / seat period | Authenticated period ended by logout; reseat requires login again | None |
| Article | Member-authored markdown piece with ≥1 tag; immediately published | RealWorld vernacular; no prior INIT PRD here |
| Tag / tag lane | Author label; lane is the published set currently sharing that tag | None |
| Global feed | Ungated listing of published articles (not a personalized feed) | Distinct from non-goal “your feed” |
| Private shelf / favorite | Private per-member bookmark of another author’s article; isolated across members | “Shelf” is this candidate’s framing for the favorite list |
| Nameplate / public profile | Guest-visible member presentation + that member’s published articles | “Nameplate” shared with think-3; ownership attack elevated here |
| Peer member | Second member used to prove ownership denial, shelf isolation, and nameplate ownership | Collision-journey actor |
| Bootstrap publish | First seated publish that moves the bulletin from empty to readable content for Guests | Shared kill-path idea with think-2/3; retained here |

---

## Discovery notes (not scored)

**T1 Challenge (inline):** Challenged “build Conduit” as the job. Recommended job: **public bulletin + session-bound contribution seat**, with Conduit API+web as solution vehicle. Solution vs job aligned — no hard-stop fork. Locks 1–12 from Lead-approved brief; locks 13–20 added as necessary consequences (seat as privilege unit, product-level denial, post-unseat guest reading including own prior work, shelf isolation, nameplate ownership, no server draft, empty-bulletin bootstrap, register≠seat).

**T2 Model (inline) — OST fork:**

| Outcome | Verdict |
|---------|---------|
| **A. Bulletin + contribution-seat Conduit slice** (public read + seat lifecycle + seated publish + own-work revision + private shelf + own nameplate) | **Recommended for this INIT** |
| B. Social-graph RealWorld (follows + personalized feed + social proof) | Rejected — contradicts load-bearing non-goals |
| C. Moderated editorial platform (drafts/approvals) | Rejected — contradicts immediate visibility / no-draft lock |
| D. Fence-first or library-stewardship packaging from think-2/3 | Rejected as *this* candidate’s cut — valid alternates; this run splits shelf vs nameplate and elevates seat/unseat + mid-compose abandon + peer nameplate |
| E. API-only contract prove without web UAT surface | Rejected — Wave0a UAT needs guest/member journeys on web against API |

**T3 Stress (inline, ≤5 claims):**

| Claim | Fails if | Cheapest test | Verdict |
|-------|----------|---------------|---------|
| Guest can read feed and open article (incl. after bootstrap and after unseat) | Guest blocked or cannot open published article | Live J-01 + J-12 + J-17 | Survivor → REQ-01, REQ-02, REQ-07, REQ-17 |
| Member can authenticate (take a seat) and publish tagged article into feed | Cannot seat or tagged article never guest-visible | Live J-06 | Survivor → REQ-10, REQ-15 |
| Logout unseats; re-login reseats; bulletin read remains | Post-logout contribution succeeds, reseat fails, or guest read breaks | Live J-07 | Survivor → REQ-12, REQ-13 |
| Own-work revision + tag rules hold; no draft leak | Peer edits others’ articles, retag/zero-tag fails, or abandon publishes | Live J-10 + J-15 + J-18 | Survivor → REQ-19, REQ-21, REQ-22, REQ-24 |
| Shelf privacy + nameplate ownership hold / non-social-proof | Peer sees another’s shelf, peer changes nameplate, or who-favorited exposed | Live J-16 + J-19 + inspection J-13 | Survivor → REQ-25, REQ-27, REQ-31; social proof stays non-goal |

**Promote complete.** Think-4 content is the promoted PRD at `prd/INIT-REALWORLD-001.md` per Hermes promote brief (`recommend: C4`). Discovery Challenge / Model / Stress above are retained as provenance, not as open pipeline stops. Next: `/validate-requirements` (incremental after document updates) → `/prd-impact-map`.
