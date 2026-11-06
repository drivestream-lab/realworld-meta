# INIT-REALWORLD-001: Membership-gated peer publishing commons

| Field | Value |
|-------|-------|
| Initiative | INIT-REALWORLD-001 |
| Status | promoted |
| Brief | conversation (Wave0a UAT clean-slate RealWorld Conduit; Lead-approved outline for T1 locks) |
| Promoted from | `prd/reports/INIT-REALWORLD-001-prd-think-4.md` (C4) via Hermes promote brief |
| Lineage | Think candidates C1–C4 remain under `prd/reports/` only |
| Quality | `/prd-quality` — C4 handover yes; C4-wins |

## 0. Challenge digest (T1 — brief as hypothesis)

The brief is a **hypothesis**. C1 framed Conduit as a discover→publish→favorite **feature loop**. C2 reframed it as an **accountable authorship desk**. C3 reframed it as a **public magazine + personal reading shelf**. This promoted PRD (from C4) challenges all three: the load-bearing product job is a **public peer commons** that anyone may enter as a **guest**, with **membership** (register + authenticated session) as the gate that unlocks peer publishing, peer bookmarking, and self-presented identity — and that **closes those privileges again on logout**.

| Grill | Challenge | Hermes lock (Lead brief + recommendation) |
|-------|-----------|-------------------------------------------|
| Job | Brief verb list can be filled as features, authorship law, or reader continuity — and still miss the guest/member gate as the product spine. | **Product job** = a shared public writing commons anyone can read without an account; membership unlocks publishing tagged markdown articles the member alone may change or remove, bookmarking others’ articles privately, and maintaining a public profile. Programme UAT (PMAgent → draft PR → park `pe.review`) is **why-now**, not a CAP. |
| Why now | Clean-slate could mean empty docs only. | Proceed as Wave0a UAT seed: product behaviour defined from empty agreed scope; empty commons feed is valid. |
| Solution vs job | API+web Conduit might be a pipeline proxy. | Same surface still delivers commons + membership gate + peer publish/favorite/profile; lock Conduit-style blogging. Do not invent a different product. |
| Actors | Brief silent on commenter, follower, moderator, “member without publish”. | Guest + Member/Author only. No commenter, follower, admin, or separate non-publishing member role. |
| Non-goals | Mobile locked. Silence on comments, follow, email, drafts, public social proof. | Mobile, comments, follow, drafts/moderation queue, email verification, OAuth, native apps, public who-favorited = load-bearing non-goals. |
| Kill | “Commons works” / “UAT blog works” is untestable. | **Fails if** an unauthenticated guest cannot browse the global feed and open a published article, **or** a registered member cannot authenticate and publish a tagged markdown article that appears in that feed, **or** after logout membership-gated actions (publish, favorite, profile self-update) remain available without logging in again. |

Hard-stop check: job and solution **agree**. Proceed to REQs.

**Divergence vs C1 / C2 / C3 (intentional provenance):**

- vs C1: centres **membership gate** (what opens and closes with session), not a co-equal feature checklist.
- vs C2: ownership remains law, but the **spine is guest vs member privilege**, not “attribution desk”; incomplete registration must not create partial membership; non-owners cannot update peers’ profiles.
- vs C3: favorites remain private member bookmarks, but continuity-across-relogin is secondary to **privilege revocation on logout**; adds member dual-role (verify own publish on guest surfaces), last-article-leaves-tag-lane empty state, and abandoned-registration-as-guest-continuity journeys.

## 1. Job and outcome

- **Job:** When people share a public writing commons, anyone can browse and read published articles without joining; people who take membership can publish tagged markdown articles they alone may edit or delete, bookmark others’ articles privately, present a public profile, and lose those membership privileges when they log out — while guest reading of the commons remains open.
- **Why now:** Wave0a UAT needs a clean-slate RealWorld Conduit INIT so the PM lane can run to a new draft PR and park at `pe.review` against a real product baseline, not inherited debt.
- **If we do nothing:** No agreed Conduit product surface for RealWorld Wave0a; guests and members have no locked commons/membership behaviour; the PMAgent UAT cannot prove the PM lane on this INIT.
- **Kill assumption:** Fails if an unauthenticated guest cannot browse the global feed and open a published article, or a registered member cannot authenticate and publish a tagged markdown article that appears in that feed, or after logout membership-gated actions remain available without logging in again.

## 2. Locked decisions

1. This INIT delivers **clean-slate RealWorld Conduit-style blogging** (API + web) for Wave0a UAT — not a different product domain.
2. The product has two access modes: **Guest** (unauthenticated) and **Member** (registered + authenticated). “Author” in the brief = Member with publishing privileges; no separate non-publishing member class.
3. **Guests** can browse the **global feed**, open any **published** article to read its body, use **tag lanes**, and view **public profiles** — without authenticating.
4. **Membership** is established by **registration** with credentials the product treats as unique, then **log in**; **log out** ends the authenticated session.
5. Membership unlocks: **publish / edit / delete own articles**, **favorite / unfavorite others’ articles**, **view private favorites list**, **update own profile** fields the product displays.
6. After **logout**, those membership-gated actions are **unavailable** until the same identity logs in again; guest commons reading remains available.
7. Publishing is **immediate**: title + markdown body + tags → **published** into the commons. **No draft or moderation queue**.
8. Members may **edit** and **delete** **only their own** articles; ownership is the mutation boundary among peers.
9. Members may **favorite** and **unfavorite** articles they did **not** write; the favorites list is **private to that member** (not a public profile tab).
10. Favorite membership for that identity **persists across logout/login** (logout revokes privilege to act, not the stored bookmark set). Deleted source articles leave every member’s favorites list.
11. **Profiles** show display identity, optional **bio**, and **authored published articles** — readable without login; members may update only **their own** displayed profile fields.
12. **Tags** are topical commons lanes: articles with tags are discoverable by those tags; an article with multiple tags is discoverable under **each** tag; a lane with zero members is an explicit empty result.
13. **Scope = API + web only.** Mobile / native / non-web clients are out of scope.
14. **Comments**, **follow/unfollow**, **following feed**, **email verification**, **password-reset-via-email**, **OAuth**, and **public who-favorited / social proof requirements** are **non-goals**.
15. Programme goal “PMAgent → draft PR → park `pe.review`” is **delivery/UAT context**, not a product REQ.
16. **Clean-slate** = behaviour defined here only; no obligation to migrate prior tenant content.
17. Incomplete or abandoned registration creates **no** member identity and leaves the user able to continue as guest.

## 3. In scope / non-goals

### In scope

- Guest commons: global feed, full-article read, tag lanes (incl. multi-tag membership and empty-lane state)
- Membership gate: register, log in, log out; privilege availability tied to authenticated session
- Immediate publish of markdown articles with tags; edit/delete own only; peer mutation refusal
- Private member favorites of others’ articles; favorites list; persistence of bookmark set across re-login; removal when source article is deleted
- Privilege revocation on logout for publish / favorite / profile self-update
- Public profiles: identity + bio + authored published list; self-update only; peer profile-update refusal
- Empty commons feed and empty favorites list as valid explicit states
- Member dual-role check: after publish, article is visible on guest-readable commons surfaces
- API + web experiences that jointly deliver the above (`realworld-api`, `realworld-web`; `realworld-local` compose is delivery support only)

### Non-goals (load-bearing)

- Mobile / native clients
- Drafts, scheduled publish, or moderation/approval before visibility
- Comments / discussion threads
- Follow / unfollow; personalized “following” feed
- Public favorites tab; “who favorited this” social graph; favorite-count mandates
- Email verification, magic-link, password-reset-via-email
- Third-party OAuth / social login
- Admin / moderation consoles / takedown workflows
- Notifications (email / push / in-app)
- Multi-tenant org workspaces; paid / ads / SEO programme work
- Migrating pre-INIT production content
- Separate curator / editor / non-publishing-member roles

## 4. Actors

| Actor | Can actually | Cannot / OQ |
|-------|----------------|-------------|
| Guest | Browse global feed; read published articles; use tag lanes; view profiles and authored lists; begin registration | Publish/edit/delete; favorite; update any profile; see any member’s private favorites |
| Member (registered, authenticated) | All guest commons surfaces; publish/edit/delete own articles; favorite/unfavorite others; open private favorites; update own profile | Edit/delete peers’ articles; update peers’ profiles; see peers’ favorites; comment/follow (non-goals); admin |
| Former session (after logout) | Guest commons surfaces only until login again | Membership-gated actions until re-authenticated |
| Programme operator / PMAgent | Outside product — drives PM artifacts for UAT | Not assigned product REQs |

## 5. Capabilities

| ID | Capability | Journeys covered | Notes |
|----|------------|------------------|-------|
| CAP-01 | Open commons reading (feed, article, tag lanes, empty commons) | J-01, J-05, J-09, J-14, J-15, J-16 | Guest-first; no account required |
| CAP-02 | Membership establishment and session gate | J-02, J-07, J-12, J-16 | Register / login / logout / fail-closed; incomplete registration creates no membership |
| CAP-03 | Member contribution lifecycle (own articles only) | J-03, J-08, J-10, J-11, J-14 | Immediate publish; peer ownership law |
| CAP-04 | Member-private peer bookmarks | J-04, J-11, J-12, J-13 | Private; privilege gated; bookmark set durable; cleared of deleted sources |
| CAP-05 | Public membership presence (profile + self-maintain) | J-06, J-17 | Bio/identity + authored published list; self-only update |

## 6. Requirements

| ID | CAP | Requirement (WHAT) | Condition / event | Observable result | Evidence |
|----|-----|--------------------|-------------------|-------------------|----------|
| REQ-01 | CAP-01 | Guests can browse a global feed of published articles | Guest opens the public commons feed when ≥1 published article exists | Feed presents published articles with required cues title, author, and tags (summary optional) sufficient to choose one | unit; live CAP-01, J-01 |
| REQ-02 | CAP-01 | Guests can read the full published article body | Guest opens a published article from feed, tag lane, or profile | Full body is shown with markdown meaning preserved for the reader | unit; live CAP-01, J-01 |
| REQ-03 | CAP-01 | Guests can use a tag lane to find published articles bearing that tag | Guest selects a tag present on ≥1 published article | Discovery result includes those articles and excludes articles lacking the tag | unit; live CAP-01, J-05 |
| REQ-04 | CAP-01 | Multi-tag articles appear under each of their tags | Article published with tags A and B; guest opens tag A then tag B | The same article is offered in both tag lane results | unit; live CAP-01, J-05 |
| REQ-05 | CAP-01 | Empty commons feed is an empty state, not a system failure | Guest opens feed with zero published articles | Product communicates that nothing is published yet; not an error presentation | unit; live CAP-01, J-01 |
| REQ-06 | CAP-01 | A deleted article is absent from all public commons surfaces | After owner deletes an article, guest uses feed, tag lane, profile authored list, or a prior open path | Article is not listed; reopen is refused or clearly unavailable | unit; live CAP-01, J-09 |
| REQ-07 | CAP-01 | A tag lane with zero matching articles is an empty result, not a system failure | Guest opens a tag that currently has no published members (including after the last article left) | Product shows an empty lane; not an error presentation | unit; live CAP-01, J-15 |
| REQ-08 | CAP-02 | A new user can register as a member | Guest completes registration with credentials the product accepts as unique | Member identity exists; user can authenticate | unit; live CAP-02, J-02 |
| REQ-09 | CAP-02 | Incomplete or abandoned registration creates no member identity | Guest starts registration and abandons before successful completion | No member identity exists; guest commons remains usable | unit; live CAP-02, J-16 |
| REQ-10 | CAP-02 | A registered member can log in and log out | Valid login; later logout | After login, membership-gated actions available; after logout, those actions unavailable until login | unit; live CAP-02, J-02, J-12 |
| REQ-11 | CAP-02 | Invalid credentials do not create a member session | Login with wrong or unknown credentials | No authenticated session; guest commons remains usable; retry possible | unit; live CAP-02, J-07 |
| REQ-12 | CAP-02 | After logout, membership-gated actions are refused | Logged-out user attempts publish, favorite, or own-profile update | Each attempt is refused; no write side-effects | unit; live CAP-02, J-12 |
| REQ-13 | CAP-03 | An authenticated member can immediately publish a markdown article with tags | Member submits title, markdown body, zero or more tags | Article is published, attributed to that member, tagged as submitted, and appears in the global feed without a separate approval step | unit; live CAP-03, J-03 |
| REQ-14 | CAP-03 | A newly published article is visible on guest-readable commons surfaces | Member publishes; a guest (or the same person using guest surfaces) opens the feed | The article is listed and openable without authentication | unit; live CAP-03, J-14 |
| REQ-15 | CAP-03 | An authenticated member can edit their own article | Member changes title, body, and/or tags on an owned article | Subsequent reads show updates; authorship unchanged; tag lanes reflect new tags | unit; live CAP-03, J-03 |
| REQ-16 | CAP-03 | An authenticated member can delete their own article | Member deletes an owned article | Article leaves feed, tag lanes, author’s authored list, and others’ favorites (see REQ-06, REQ-21) | unit; live CAP-03, J-03 |
| REQ-17 | CAP-03 | Non-owners cannot mutate another member’s article | Authenticated member attempts edit or delete on non-owned article | Mutation refused; article unchanged for all readers | unit; live CAP-03, J-08 |
| REQ-18 | CAP-03 | Unauthenticated publish is refused | Guest attempts to publish | No new article created | unit; live CAP-03, J-11 |
| REQ-19 | CAP-04 | An authenticated member can favorite and unfavorite another member’s article | Member favorites a non-owned article; later unfavorites | Favorite state visible to that member on the article; after unfavorite, article absent from their favorites list | unit; live CAP-04, J-04 |
| REQ-20 | CAP-04 | An authenticated member can open their private favorites list | Member opens favorites after ≥1 favorite | Listed articles match current favorites only | unit; live CAP-04, J-04 |
| REQ-21 | CAP-04 | Deleted articles leave every member’s favorites list | Member A favorites Member B’s article; B deletes it; A opens favorites | Deleted article is absent from A’s list; reopen unavailable | unit; live CAP-04, J-13 |
| REQ-22 | CAP-04 | Favorites for a member identity persist across logout and later login | Member favorites an article, logs out, logs in again, opens favorites | Favorited article remains listed | unit; live CAP-04, J-12 |
| REQ-23 | CAP-04 | Guests cannot favorite | Guest attempts favorite | Favorite refused; no favorites entry recorded | unit; live CAP-04, J-11 |
| REQ-24 | CAP-04 | Self-favorite is not a successful peer bookmark | Member attempts to favorite their own article | Refusal or no-op that does not place own article on the others-favorites list | unit; live CAP-04, J-04 |
| REQ-25 | CAP-04 | Empty favorites list is an explicit empty state | Authenticated member opens favorites with zero favorites | Product shows an empty list, not a system failure | unit; live CAP-04, J-13 |
| REQ-26 | CAP-05 | Anyone can view a public profile with bio and authored published articles | Guest or member opens a profile for a member with ≥0 published articles | Profile shows display identity, bio if set, and authored **published** articles (not that member’s private favorites) | unit; live CAP-05, J-06 |
| REQ-27 | CAP-05 | An authenticated member can update their own displayed profile fields | Member changes bio and/or display identity | Subsequent profile views show the updates | unit; live CAP-05, J-06 |
| REQ-28 | CAP-05 | A member cannot update another member’s profile | Authenticated member attempts to change another member’s displayed profile fields | Update refused; peer profile unchanged | unit; live CAP-05, J-17 |
| REQ-29 | CAP-04 | Guests cannot open a member’s private favorites list | Guest or unauthenticated user attempts to open the private favorites list | Attempt refused or unavailable; no favorites list contents disclosed | unit; live CAP-04, J-11 |

## 7. Negative and failure paths

| REQ | Condition | Required behavior | Why it matters |
|-----|-----------|-------------------|----------------|
| REQ-11 | Wrong / unknown credentials | No session; clear refusal; guest commons still works | Auth boundary for membership |
| REQ-12 | Publish / favorite / profile self-update after logout | Refusal; no write side-effects | Session end must revoke privileges |
| REQ-17 | Edit/delete by non-owner | Refusal; content unchanged | Peer ownership law |
| REQ-18 | Guest publish attempt | No article created | Guests are commons readers |
| REQ-23 | Guest favorite attempt | No favorites entry | Bookmarks are membership-gated |
| REQ-29 | Guest/unauthenticated open of private favorites list | Refused or unavailable; no list contents disclosed | Private favorites are membership-gated to view, not only to act |
| REQ-24 | Favorite own article | No self-bookmark success path | Favorites mean peers’ writing |
| REQ-08 | Duplicate registration identity | Registration refused; existing member unchanged | Identity uniqueness |
| REQ-09 | Abandoned registration | No partial membership; guest commons usable | Incomplete join must not pollute commons |
| REQ-05 | Zero published articles | Empty commons state, not error | Clean-slate start |
| REQ-07 / REQ-15 | Last article leaves a tag lane | Empty lane, not error; removed tag no longer lists article | Lane honesty |
| REQ-06 / REQ-16 / REQ-21 | Stale open or favorites entry after delete | Unavailable / absent; lists consistent; no crash | Delete must be real for commons and bookmarks |
| REQ-13 | Incomplete publish (missing required title/body per product rules) | Publish refused; no partial published article | Avoid ghost commons entries |
| REQ-28 | Peer profile update attempt | Refusal; peer profile unchanged | Membership presence is self-only |
| REQ-25 | Zero favorites | Empty list state, not error | New members need a clear favorites surface |

## 8. Contract seeds (semantic)

Cross-repo seam: `realworld-api` (provider) ↔ `realworld-web` (consumer).

| ID | Provider | Consumer | Logical operation | Field meaning | Invariants | Errors |
|----|----------|----------|-------------------|---------------|------------|--------|
| CTR-01 | realworld-api | realworld-web | Establish / end member session | Session binds to exactly one registered member; logout ends membership privileges for that client | Invalid credentials never yield a session; logout does not erase that member’s stored favorites set | Invalid / unknown credentials → denied |
| CTR-02 | realworld-api | realworld-web | Register member identity | Registration creates at most one member for a unique credential set | Incomplete registration creates no member; duplicate unique credentials refused | Duplicate identity → denied; incomplete → no identity |
| CTR-03 | realworld-api | realworld-web | Publish / update / delete article | Article carries owner, title, markdown body, tags; publish is immediate commons visibility | Only owner mutates; delete removes article from feed, tag lanes, authored lists, and all favorites lists; unauthenticated write denied | Not owner → denied; missing → not found; unauthenticated write → denied |
| CTR-04 | realworld-api | realworld-web | Index published articles (global + by tag) | Feed lists published articles; tag membership equals article tags | Multi-tag ⇒ membership in each tag; empty feed and empty tag lane are valid empty | Tag with no members → empty result, not system failure |
| CTR-05 | realworld-api | realworld-web | Maintain private peer favorites | Favorite links endorsing member → non-owned article; list is endorser-private; survives session end | No guest favorite; no guest favorites-list open; no successful self-favorite; deleted articles leave favorites lists; acting on or opening favorites requires authenticated session | Unauthenticated favorite or list open → denied; missing article → not found |
| CTR-06 | realworld-api | realworld-web | Read / update public profile | Profile = display identity + bio + authored published articles | Profile read needs no auth; authored list matches ownership of published articles; only owning member may update; favorites not required on public profile | Missing profile → not found; non-owner profile update → denied |

## 9. NFR applicability

| Area | Requirement or N/A rationale |
|------|------------------------------|
| Security | Auth required for publish/edit/delete/favorite/favorites-list open/profile self-update; ownership and peer-profile boundaries enforced; fail-closed login; logout revokes membership privileges (REQ-11, REQ-12, REQ-17, REQ-18, REQ-23, REQ-28, REQ-29). |
| Reliability | Commons read and member write/favorites must succeed under normal single-community UAT use; empty feed, empty tag lane, and empty favorites are valid (REQ-05, REQ-07, REQ-25); delete clears commons indexes and favorites (REQ-06, REQ-21). |
| Performance / capacity | N/A quantified SLO for Wave0a — interactive single-community UAT; no capacity lock. |
| Observability | Auth denial vs ownership denial vs missing article vs peer-profile denial must be distinguishable as product outcomes for support; deep telemetry stack out of product scope. |
| Privacy / data handling | Registration/profile fields operate the commons only; favorites are private to the endorsing member; no OAuth brokers; no mandated public favorite social proof. |
| Migration / compatibility | N/A — clean-slate; no prior content obligation. |
| Rollback / recovery | N/A as user-facing Conduit behaviour — delivery concern. |
| Operations / support | `realworld-local` may host API+web for UAT; not a product journey. |

## 10. Assumptions

| ID | Assumption | Status | Dependent REQs | Default if false |
|----|------------|--------|----------------|------------------|
| A-01 | Markdown is the authoring body format; readers see preserved markdown meaning — no separate rich-format product | accepted | REQ-02, REQ-13, REQ-15 | Reopen body-format OQ |
| A-02 | Global feed is one community commons listing of all published articles — not personalized | accepted | REQ-01, REQ-05 | If personalization required, new CAP/OQ |
| A-03 | Immediate publish is the only write path; “save draft” is not offered | accepted | REQ-13 | If drafts required, reopen non-goal and CAP-03 |
| A-04 | Favorites are member-private; public profile does not list favorites | accepted | REQ-20, REQ-26, REQ-29 | If public favorites required, reverse lock 9 and add REQs |
| A-05 | Logout revokes acting privilege but does not wipe the member’s stored favorites set | accepted | REQ-12, REQ-22 | If favorites were session-ephemeral, reopen A-05 and REQ-22 |
| A-06 | API + web suffice to prove every CAP | accepted | all | Mobile already non-goal |
| A-07 | Clean-slate may start with zero articles; seed content optional | accepted | REQ-05 | If seed mandatory, add seed REQ |
| A-08 | “Member” and brief “author” are the same registered authenticated actor | accepted | CAP-02–CAP-05 | If non-publishing members required, new actor/CAP |

## 11. Open questions

| ID | Question | Owner | Blocking | Required-by | Default if deferred |
|----|----------|-------|----------|-------------|---------------------|
| OQ-01 | Must registration require an email address, or is username+secret enough? | PM | no | spec-draft | Username + secret sufficient; email optional only if needed for display |
| OQ-02 | Global feed ordering: newest-published vs newest-updated vs other stable rule? | PM | no | spec-draft | Newest published first; edits do not reshuffle unless Lead later locks otherwise |
| OQ-03 | Is a human-readable article slug required, or is any durable reopen path enough? | PE | no | feasibility | Durable reopen enough; pretty slug not mandated |
| OQ-04 | Soft-delete vs hard-remove in storage? | PE | no | feasibility | Either, if REQ-06 / REQ-16 / REQ-21 observables hold |
| OQ-05 | After display-identity change, do historical article bylines show old, new, or both? | PM | no | spec-draft | Bylines follow current display identity |
| OQ-06 | May a member unfavorite only from the article surface, only from the favorites list, or both? | PM | no | spec-draft | Both surfaces may clear the same favorites membership |
| OQ-07 | Session lifetime / idle expiry product expectation? | PE | no | feasibility | Session lasts until logout or client discard for Wave0a; favorites data unaffected by idle policy |
| OQ-08 | Should favorite **counts** be visible to guests on an article, even if who-favorited stays private? | PM | no | spec-draft | Counts not required; only endorser’s own state + private list required |
| OQ-09 | Must the product expose an explicit “you are logged out / guest mode” cue after logout, or is refusal of gated actions enough? | PM | no | spec-draft | Refusal of gated actions + continued guest commons is enough; explicit mode cue optional |

## 12. Journeys

| ID | Actor | Trigger | Main flow | Primary edge | Abandon | Caps exercised |
|----|-------|---------|-----------|--------------|---------|----------------|
| J-01 | Guest | Wants to read the public commons | Open global feed → pick article → read body | Empty feed → empty state (REQ-05) | Skims feed, leaves | CAP-01 |
| J-02 | Guest → Member | Wants membership to publish | Register → log in → membership-gated actions available | Duplicate registration refused | Abandons (see J-16) | CAP-02 |
| J-03 | Member | Ready to contribute | Compose markdown + tags → immediate publish → see in feed → edit (incl. tags) → optional delete | Incomplete publish refused | Abandons compose | CAP-03 |
| J-04 | Member | Bookmarks a peer’s article | Open article → favorite → open favorites → unfavorite | Self-favorite refused/no-op | Favorites once, never opens list | CAP-04 |
| J-05 | Guest | Follows a topic via tags | From tag cue → tag lane → open matching article; multi-tag under each lane | Tag with no articles → empty lane (REQ-07) | Leaves tag unread | CAP-01 |
| J-06 | Guest / Member | Curious about a writer | Open profile → bio → authored published article | Empty bio still shows identity + list; favorites not on profile | Views profile only | CAP-05 |
| J-07 | Member | Returns / mistypes secret | Successful login; separate bad-credentials attempt fails closed; logout returns to guest commons | Failed login still leaves guest read usable | Gives up after failures | CAP-02 |
| J-08 | Member | Tries to alter a peer’s article | Authenticated edit/delete on non-owned article | Always denied; unchanged | Stops after denial | CAP-03 |
| J-09 | Guest | Returns to a previously read article after owner deleted it | Uses prior path / feed / tag / profile | Article unavailable; lists no longer include it | Gives up | CAP-01 |
| J-10 | Member | Changes tags after publish | Edit tags on owned article → check old and new tag lanes | Removed tag no longer lists article; new tag does | Abandons edit | CAP-03 |
| J-11 | Guest | Tries membership actions without auth | Attempt publish, favorite, and/or open private favorites list while logged out | Each refused; no write side-effects; no favorites list disclosure | Registers (J-02) or leaves | CAP-03, CAP-04 |
| J-12 | Member | Ends session then returns | Favorite → logout → gated actions refused → login → favorites still listed; gated actions restored | REQ-12 + REQ-22 together | Does not return | CAP-02, CAP-04 |
| J-13 | Member | Favorites hygiene after source delete / empty list | Open empty favorites; or open favorites after favorited article was deleted | Empty state (REQ-25) or deleted entry gone (REQ-21) | Leaves favorites | CAP-04 |
| J-14 | Member | Verifies own publish on guest commons | Publish while authenticated → confirm article appears for guest read (self as guest surface or second guest) | Article openable without auth (REQ-14) | Skips verification | CAP-03, CAP-01 |
| J-15 | Guest | Opens a tag after its last article left | Last article under tag deleted or retagged away → guest opens that tag | Empty lane, not error (REQ-07) | Leaves | CAP-01 |
| J-16 | Guest | Abandons registration mid-flow | Starts register → leaves without completing → continues browsing commons | No member identity created (REQ-09) | Never returns to register | CAP-02, CAP-01 |
| J-17 | Member | Tries to change a peer’s profile | Authenticated update on another member’s profile fields | Always denied; peer profile unchanged (REQ-28) | Stops after denial | CAP-05 |

Brief-omitted paths included on purpose: **J-12** logout privilege revocation + favorites durability, **J-14** member dual-role guest-visibility check, **J-15** empty tag lane after last article leaves, **J-16** abandoned registration, **J-17** peer profile mutation refusal. Comments/follow/drafts/public-social-proof journeys explicitly absent (non-goals).

## 13. Domain terms

| Term | Meaning in this INIT | Collision with existing product? |
|------|----------------------|----------------------------------|
| Guest | Unauthenticated reader of the public commons | None |
| Member / Author | Registered authenticated user; brief “author” = this actor | Framing term for this PRD — same person as C1–C3 “Author” |
| Commons | Public reading surfaces: global feed, article body, tag lanes | Framing term — not a separate service |
| Membership gate | Registration + authenticated session that unlocks publish, favorite, and own-profile update | Spine of this PRD |
| Article | Published unit: title, markdown body, tags, owning member — visible once published | None |
| Immediate publish | Submit creates a publicly visible commons article; no draft/moderation step | Same lock family as C2/C3; restated for membership framing |
| Tag / Tag lane | Label used for public commons index membership | “Lane” is C4 framing for tag discovery |
| Global feed | Public listing of all published articles in this community | Not a following feed |
| Favorite | Private, durable bookmark from a member to another member’s article; acting requires session | Emphasizes membership privilege vs C3 “shelf continuity” alone |
| Profile | Public display identity + bio + authored published articles; self-update only | None |
| Clean-slate | Behaviour defined without prior tenant content obligations | Programme UAT term |
| Conduit | RealWorld reference blogging shape (API + web) | Matches `realworld-api` / `realworld-web` |

---

## Stress survivors (T3 — ≤5 load-bearing claims)

| Claim | Fails if ___ | Cheapest test | Outcome |
|-------|--------------|---------------|---------|
| Guests get a usable commons without membership | Feed/article requires login | Open feed logged out → read article | Survived → REQ-01, REQ-02 |
| Membership unlocks publish into the commons | Member cannot publish tagged markdown that guests see | Register → login → publish → guest opens feed | Survived → REQ-08, REQ-13, REQ-14 |
| Logout revokes membership privileges | Publish/favorite/profile-update still work after logout | Logout → attempt publish and favorite | Survived → REQ-12, J-12 |
| Peers cannot mutate each other’s contributions or profiles | Non-owner can edit article or update peer profile | Authenticated peer edit + peer profile update | Survived → REQ-17, REQ-28, J-08, J-17 |
| Incomplete join does not create partial membership | Abandoned registration leaves a usable or half-formed member | Start register → abandon → attempt login with unfinished credentials / inspect commons | Survived → REQ-09, J-16 |

Casualties → non-goals: comments, follow, drafts/moderation, OAuth/email reset, public who-favorited / favorite-count mandates.

## OST fork (T2 — one recommended outcome)

| Outcome | Meaning | Verdict |
|---------|---------|---------|
| A. Membership-gated peer publishing commons (API+web) | Matches kill assumption; centres guest vs member gate while keeping Lead publish/favorite/profile locks | **Recommended — this PRD** (promoted from C4) |
| B. Feature-checklist Conduit (C1-style) | Valid alternate framing; already captured in C1 | Not this PRD’s framing |
| C. Accountable authorship desk (C2-style) | Valid alternate framing; already captured in C2 | Not this PRD’s framing |
| D. Public magazine + personal reading shelf (C3-style) | Valid alternate framing; already captured in C3 | Not this PRD’s framing |
| E. Social Conduit (comments + follow + public favorites) | Broader than Wave0a; dilutes UAT | Reject for this INIT |
| F. Pipeline-only meta docs / stub product | Fails product kill assumption | Reject |

---

**Promoted.** Quality compare and promote gates for this file are complete. Next: `/validate-requirements` (incremental after document updates), then `/prd-impact-map` when validation is clean.
