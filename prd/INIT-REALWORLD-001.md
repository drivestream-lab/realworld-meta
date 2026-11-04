# INIT-REALWORLD-001: Public catalog states + list↔read fidelity

| Field | Value |
|-------|-------|
| Initiative | INIT-REALWORLD-001 |
| Status | draft |
| Brief | Lead conversation / outline (Hermes host; Lead-approved T1 locks) |
| Promoted path | `prd/INIT-REALWORLD-001.md` (this document) |
| Promotion source | `prd/reports/INIT-REALWORLD-001-prd-think-3.md` (C3) via Hermes promote brief |
| Quality | `prd/reports/INIT-REALWORLD-001-prd-quality.md` — C3 recommended |
| Lineage | Promoted from think C3; diverges from C1 and C2 |

## T0 inventory

| Input | Result |
|-------|--------|
| Brief | Lead outline for INIT-REALWORLD-001 (job, locks, non-goals, fail-if) |
| Initiative id | INIT-REALWORLD-001 (given; not invented) |
| Promoted PRD | `prd/INIT-REALWORLD-001.md` (living draft) |
| Product context | `config/service-catalog-drivestream-lab.yaml` (realworld-api, realworld-web, realworld-local); `planning/` empty of initiative content — skipped beyond catalog |
| Prior think candidates | `prd/reports/INIT-REALWORLD-001-prd-think.md` (C1), `prd/reports/INIT-REALWORLD-001-prd-think-2.md` (C2), `prd/reports/INIT-REALWORLD-001-prd-think-3.md` (C3 — promoted) |
| Promote | completed — C3 promoted to this path per Hermes promote brief |

## T1 Challenge (inline; companions missing; non-interactive)

Brief treated as hypothesis. Lead locks confirmed as grill outputs. Recommendations locked without waiting / AskQuestion.

| Probe | Challenge | Resolution |
|-------|-----------|------------|
| Job / done-in-the-world | Is “something stored” or author preview enough? | **No.** Done-in-the-world = a **later visitor** (not the author, outside the write session) finds the article on **home** and reads the **same** title, body, and author attribution. |
| Why now | Proxy for polish? | Without a public publish → home discover → read path, the platform has no observable function; later features depend on publicly visible articles. |
| If we do nothing | | Site looks permanently empty or broken; authors publish into darkness; visitors leave. |
| Solution vs job | Is home listing a proxy for storage? | **Disagree if so.** Home is the **only** discovery surface. Storage without home visibility fails. Under Lead locks, job and solution **agree** — proceed. |
| Actors | Hats from prior INIT / prior candidates? | Do not assume C1/C2 naming as baseline. Actors who can actually act: **Catalog visitor** (anonymous allowed), **Publishing author**, **Second distinct author**. Platform owns catalog state transitions. |
| Non-goals | Load-bearing? | Comments, favorites, following, tag discovery, edit/delete, drafts/unlisted, ranking/newest-first as a product rule, profiles beyond minimum identity to publish — all out. |
| Kill assumption | | Fails if publish reports success but a later non-author visitor cannot find the article on home and read attributed title + body. |
| Whole-product gap vs brief / C1 / C2 | Brief TOC ≈ empty → publish → read; C1 = author-pipeline; C2 = observer-prove-first + same-author accumulation | Elevate **catalog state machine** (Empty → Single → Multi), **list↔read integrity** (listed ⇒ openable with matching substance), and **attribution binding** (list + read show the publishing identity). Same-author second publish is **not** elevated (Lead locked distinct second author only) — park as non-goal / out of prove unless Lead expands. |

## T2 Model (inline)

**OST fork (name → recommend one):**

| Outcome | Meaning | Keep? |
|---------|---------|-------|
| A. Author confirmation / session echo | Publish UI success proves the product | **Reject** — violates done-in-the-world |
| B. Reachability without home | Tag/feed/secret-link discovery | **Reject** — discovery lock = home only |
| C. Observer-first narrative (C2 shape) | Outside observer defines success sequence | Valid but **already explored in C2** — do not re-clone |
| D. Catalog-state + fidelity loop | Public catalog has explicit states; successful publish is a state transition; home lists only real entries; opening a listed entry yields bound attribution + same title/body; multi-author occupancy preserves every entry | **Recommend (this candidate)** |

**Adjacent surfaces:** keep home as catalog surface, public attributed read, identity as attribution-binding gate, multi-author coexistence, refuse of incomplete/identity-absent publish; defer tags/feeds/profiles/edit/same-author multi-publish prove; non-goal comments/favorites/following/drafts/ranking rules.

**Divergence summary:**

| Candidate | Spine |
|-----------|--------|
| C1 | Author pipeline: identity → publish → discover → read; incomplete-substance refuse |
| C2 | Outside-observer prove-first; same-session anti-prove; same-author + second-author accumulation; identity-absent refuse |
| C3 (this) | **Catalog states + list↔read fidelity + attribution binding**; multi-entry = second distinct author only; broken list→read seam is an explicit kill path |

## T3 Stress (inline; ≤5 claims)

| # | Claim | Fails if | Cheapest test | Verdict |
|---|-------|----------|---------------|---------|
| 1 | Successful publish is an Empty→occupied **catalog state transition**, not a session echo | Author sees success but catalog visitor still sees empty home | Publish; separate anonymous visit to home | Survivor → REQ |
| 2 | Home listing and public read are one **fidelity loop** | Article listed on home but open fails, or title/body/attribution differ from publish | From home, open listed entry; compare substance | Survivor → REQ |
| 3 | Attribution is **bound** to the publishing identity | List or read shows a different author than who published | Publish as author A; outsider checks list + read attribution | Survivor → REQ |
| 4 | Multi-author occupancy preserves every public entry | Second distinct author’s publish hides or breaks the first | Two authors publish; both listed; both open with correct substance + attribution | Survivor → REQ |
| 5 | Invalid publish must not advance catalog state | Identity-absent or incomplete submit still yields success / new home entry | Attempt without identity; attempt missing title or body; state unchanged | Survivor → REQ |

---

## 1. Job and outcome

- **Job:** When a visitor lands on an empty RealWorld site, nothing yet proves the platform works. After the first person registers and publishes an article, that publish must advance the **public catalog** so the article appears on the **home** listing. A **later visitor** (not the author, outside the write session) must open that listing entry and read the **same** title, body, and **bound** author attribution.
- **Why now:** Without a public publish → discover → read path, the platform has no observable function. Later features depend on articles existing and being publicly visible. This is the minimum proof the writing↔reading loop works.
- **If we do nothing:** The site looks permanently empty or broken. Authors publish into darkness (private or session-only writes). Visitors leave and never return.
- **Kill assumption:** Fails if publish reports success but a later non-author visitor cannot find the article on home and read attributed title + body.

## 2. Locked decisions

1. Done-in-the-world = a later visitor finds and reads a published article on **home** — not “API accepted”, not author-only view, not write-session confirmation.
2. Starting catalog state for the prove path: home has **zero** published articles (**Empty**).
3. Discovery surface for this INIT = **home article listing** only (not tags, feeds, or secret links).
4. An **anonymous** later visitor can read without registering.
5. Publish substance = **title + body + author attribution** (short description / dek **not** required).
6. A **second distinct author’s** publish must leave **both** articles listed on home and each readable with correct substance and attribution (**Multi** occupancy).
7. A home-listed published article must be **openable** by a later visitor to the **same** title, body, and author attribution that were published (list↔read integrity).
8. Author attribution on list and on read is **bound** to the identity that successfully published the entry.
9. Incomplete substance (missing title or missing body) must **not** advance the public catalog state.
10. Publish without an established author identity must **not** advance the public catalog state.
11. Same-author publishing a second article is **not** a prove obligation in this candidate (Lead locked distinct second author; C2 already explored same-author accumulation).

## 3. In scope / non-goals

### In scope

- Honest **Empty** home catalog when zero published articles exist.
- Minimum author identity as the **gate** to publish and the **binding** for public attribution.
- Successful publish as a catalog state transition that creates a durable public entry (title + body + bound attribution).
- Home listing as the only in-scope discovery surface.
- Later-visitor (anonymous) open-from-home read with **substance fidelity** to what was published.
- List↔read integrity: every listed public entry opens to matching substance.
- **Multi** occupancy when a second distinct author publishes; both entries remain listed and readable with correct per-entry attribution.
- Refusal of identity-absent and incomplete-substance publish so catalog state does not falsely advance.

### Non-goals (load-bearing)

- Comments, favorites, following.
- Tag-based discovery, personalized feeds, secret or unlisted links as the discovery path.
- Edit or delete of articles after publish.
- Drafts or unlisted publication states.
- Ranking or newest-first as a product rule (presence and coexistence matter; order policy is out).
- Profiles beyond the minimum identity needed to publish and attribute.
- Short description / dek as required publish substance.
- Same-author multi-publish as a separate prove path (deferred relative to Lead’s second-author lock; not required to claim this INIT done).
- Treating author write-session confirmation as proof that catalog state advanced for others.

## 4. Actors

| Actor | Can actually | Cannot / OQ |
|-------|----------------|-------------|
| Catalog visitor (later visitor) | Open home; observe Empty or occupied listing; open a listed entry; read title + body + attribution **without** registering | Is not the publishing author for the prove; is outside the write session; cannot alone advance catalog state |
| Publishing author | Establish minimum identity; publish title + body; bind attribution to that identity | Cannot satisfy done-in-the-world by self-view in the write session |
| Second distinct author | Establish a different identity; publish; coexist in **Multi** occupancy | Must not displace or corrupt the first public entry’s substance or attribution |
| Platform (system) | Own catalog states; enforce list↔read fidelity; refuse invalid publish | N/A |

## 5. Capabilities

| ID | Capability | Journeys covered | Notes |
|----|------------|------------------|-------|
| CAP-01 | Present honest public catalog states on home (Empty, occupied) | J-01, J-03, J-04, J-05 | Empty is a valid success state; occupied lists only durable public entries |
| CAP-02 | Advance catalog state by publishing under a bound author identity with complete substance | J-02, J-04, J-06 | Success = durable public entry; refusal leaves state unchanged |
| CAP-03 | Preserve list↔read fidelity for later visitors | J-03, J-04, J-05 | Listed ⇒ openable; substance matches publish |
| CAP-04 | Bind and show author attribution consistently on list and read | J-02, J-03, J-04 | Attribution = publishing identity; stable across list and read |

## 6. Requirements

| ID | CAP | Requirement (WHAT) | Condition / event | Observable result | Evidence |
|----|-----|--------------------|-------------------|-------------------|----------|
| REQ-01 | CAP-01 | Home presents the Empty catalog state when no articles are published | Site has zero published articles; a visitor opens home | No published articles are listed (zero published items; Empty list is enough — see OQ-04) | live: CAP-01, J-01 |
| REQ-02 | CAP-02 | A visitor can establish a minimum author identity usable to publish and to bind attribution | Visitor completes registration sufficient to publish | Identity exists for publish; that identity is the attribution source for entries they publish | live: CAP-02, CAP-04, J-02 |
| REQ-03 | CAP-02 | Publish without an established author identity does not advance catalog state | Someone attempts to publish without author identity | No successful public publish; home listing unchanged for that attempt | live: CAP-02, J-06 |
| REQ-04 | CAP-02 | Publish with missing title or missing body does not advance catalog state | Author with identity attempts publish missing title or missing body | No successful public publish; home listing unchanged for that attempt | live: CAP-02, J-06 |
| REQ-05 | CAP-02 | A registered author can publish title + body and advance the catalog from Empty to occupied | Author has identity; submits non-empty title and body; catalog was Empty | Publish reports success **and** a durable public catalog entry exists with that title, body, and bound author attribution | live: CAP-02, CAP-04, J-02 |
| REQ-06 | CAP-01 | After successful publish, home lists the new public entry for a later visitor | REQ-05 succeeded; later visitor (not the author, outside write session) opens home | The article is listed with title and author attribution (sufficient to open) | live: CAP-01, J-03 |
| REQ-07 | CAP-03 | Opening a home-listed public entry yields the published substance to an anonymous later visitor | Later visitor has not registered for this prove and opens the article from the home listing | Visitor sees the **same** title and body that were published | live: CAP-03, J-03 |
| REQ-08 | CAP-04 | List and read show the **bound** publishing identity as author attribution | After successful publish; later visitor views the entry on home and on read | Attribution on list and on read both match the identity that published; they match each other | live: CAP-04, J-03 |
| REQ-09 | CAP-03 | A home-listed public entry must not be a dead end | An article appears on the home listing after successful publish | Later visitor can open it to a successful public read of title + body + attribution (list↔read integrity) | live: CAP-03, J-05 |
| REQ-10 | CAP-01 | Second distinct author’s successful publish yields Multi occupancy without harming the first entry | First article already public; a different author successfully publishes another | Home lists **both**; each opens with its own title, body, and correct bound attribution | live: CAP-01, CAP-03, CAP-04, J-04 |
| REQ-11 | CAP-01 | Reported publish success implies later home discoverability | Publish has reported success for an article | A later non-author visitor can find that article on home (kill-assumption binding) | live: CAP-01, J-03 |

## 7. Negative and failure paths

| REQ | Condition | Required behavior | Why it matters |
|-----|-----------|-------------------|----------------|
| REQ-03 | Publish attempted without author identity | Catalog state unchanged; no public success | Prevents anonymous pollution of the public catalog |
| REQ-04 | Publish attempted without title or without body | Catalog state unchanged; no public success | Prevents empty-shell “success” |
| REQ-09 / REQ-07 | Article listed on home but open fails or substance mismatches publish | Treat as product failure (writing↔reading loop broken) | List↔read integrity kill — brief-omitted seam |
| REQ-08 | List attribution ≠ read attribution, or ≠ publishing identity | Treat as product failure | Attribution binding kill |
| REQ-06 / REQ-11 | Publish reported success but article absent from home for later visitor | Treat as product failure (job unmet) | Direct kill assumption |
| REQ-07 | Later visitor is anonymous | Read still works; no registration gate on public read | Kill path if read is members-only |
| REQ-10 | Second distinct author publishes successfully | First entry remains listed and readable with correct substance + attribution | Prevents last-write-wins / attribution smash |
| REQ-01 | No articles published yet | Home shows Empty published listing (zero published items) | Starting-state honesty |
| CTR-01 | Catalog unavailable when a visitor opens home | Consumer must not claim home catalog success (must not present unavailable as honest Empty or occupied) | Matches CTR-01 error; prevents false catalog state when the list API is down |

## 8. Contract seeds (semantic)

Cross-repo seam exists: `realworld-api` (provider) ↔ `realworld-web` (consumer) per service catalog.

| ID | Provider | Consumer | Logical operation | Field meaning | Invariants | Errors |
|----|----------|----------|-------------------|---------------|------------|--------|
| CTR-01 | realworld-api | realworld-web | List published articles for home catalog state | Each entry identifies a public article for discovery (title + bound author attribution at minimum) | Only publicly published articles; Empty list allowed; Multi coexistence; entries durable beyond write session; every listed entry must be retrievable for read | Catalog unavailable → consumer cannot claim home success |
| CTR-02 | realworld-api | realworld-web | Retrieve one published article for public read | Title, body, bound author attribution for a public article | Retrieved substance matches what was published; readable without visitor registration; attribution matches list | Missing or non-public article → not a successful public read (listed-but-missing is integrity failure) |
| CTR-03 | realworld-api | realworld-web | Accept or refuse publish of title + body under an author identity | Creates a public catalog entry only when identity and substance are complete; binds attribution to that identity | Success ⇒ listable on home and readable with same substance + same bound attribution by a later visitor; refusal leaves catalog state unchanged | No identity → refuse; incomplete substance → refuse |

## 9. NFR applicability

| Area | Requirement or N/A rationale |
|------|------------------------------|
| Security | Anonymous **read** of public articles allowed. Publish requires established author identity. Attribution binding is a product integrity rule, not a full authz matrix. |
| Reliability | After reported successful publish, catalog state must reflect the new entry to a later visitor on home and on read in the same environment. List↔read must not diverge (no ghost listings, no substance drift for this INIT’s prove). Catalog-unavailable: CTR-01 + §7 bind “cannot claim home success”; visitor-visible recovery UX for catalog-down is N/A for this INIT’s prove. |
| Performance / capacity | N/A as a product bar beyond “home and read work for Empty, Single, and two-author Multi.” No ranking or scale SLO. |
| Observability | N/A product requirement; engineering may add logs without PRD mandates. |
| Privacy / data handling | Author attribution is **intended to be public** with the article. No private draft mode in scope. |
| Migration / compatibility | N/A — green public loop; no migration of prior private content required. |
| Rollback / recovery | N/A product rule beyond: refused publish leaves catalog state unchanged (REQ-03, REQ-04). |
| Operations / support | N/A beyond observable Empty → publish → home discover → fidelity read (and Multi with second author). |

## 10. Assumptions

| ID | Assumption | Status | Dependent REQs | Default if false |
|----|------------|--------|----------------|------------------|
| ASS-01 | “Later visitor / outside the write session” is satisfied by a distinct visit that is not the author’s authenticated write context; anonymous is enough | accepted (Lead lock) with OQ-01 for operational prove recipe | REQ-06, REQ-07, REQ-08, REQ-09, REQ-11 | If false, redefine prove to an explicit second browser/user context — still not author-only |
| ASS-02 | Minimum author identity yields a stable public attribution label suitable to show on list and read | accepted with OQ-02 for exact label shape | REQ-02, REQ-05, REQ-06, REQ-08, REQ-10 | Resolve OQ-02 before spec-draft freezes copy |
| ASS-03 | Home listing need not show body or dek; title + author attribution suffice to choose an article | accepted (Lead: dek not required) | REQ-06 | If Lead later requires dek on list, add REQ — out of current locks |
| ASS-04 | Article order on home is unspecified; coexistence and presence matter, not sort policy | accepted (non-goal: ranking rules) | REQ-10 | Do not fail prove on order |
| ASS-05 | Same-author second publish is out of prove for this candidate; Lead’s second-author lock is the Multi obligation | accepted (T2 divergence from C2) | REQ-10 | If Lead later requires same-author Multi prove, add a REQ/journey — do not silently inherit C2 |

## 11. Open questions

| ID | Question | Owner | Blocking | Required-by | Default if deferred |
|----|----------|-------|----------|-------------|---------------------|
| OQ-01 | What operational prove recipe counts as “outside the write session” (anonymous window, signed-out visit, second browser profile)? | PM | no | live fixtures / wave acceptance | Anonymous visit distinct from the author’s authenticated write context is enough |
| OQ-02 | What exact public label is “author attribution” (chosen username vs other display identity)? | PM | no | spec-draft copy / fixtures | Use the publicly visible identity established at registration; keep consistent on list and read |
| OQ-03 | After refused publish (identity-absent or incomplete), what visitor-visible signal is required beyond non-success + catalog unchanged? | PM | no | spec-draft | Any clear non-success is enough; exact messaging not locked |
| OQ-04 | Must home Empty state include explanatory copy, or is an empty list enough? | PM | no | later UX | Empty list with zero published items is enough for REQ-01; stronger Empty UX honesty rules (explanatory copy, anti-placeholder / anti-error-as-broken bars) deferred until Lead locks them |
| OQ-05 | If a listed entry cannot be opened, is any visitor-visible recovery required in this INIT, or is “product failed the fidelity loop” sufficient as the acceptance stance? | PM | no | wave acceptance | Failure of REQ-09 fails the INIT; no separate recovery UX required |

## 12. Journeys

| ID | Actor | Trigger | Main flow | Primary edge | Abandon | Caps exercised |
|----|-------|---------|-----------|--------------|---------|----------------|
| J-01 | Catalog visitor | Arrives before any publish | Open home on Empty catalog | Observes zero published articles (honest Empty) | Leaves — no false proof of content | CAP-01 |
| J-02 | Publishing author | Empty catalog; wants to publish | Establish identity → compose title + body → publish successfully | Catalog advances Empty → occupied; attribution bound to that identity | Abandons or refused → catalog stays Empty | CAP-02, CAP-04 |
| J-03 | Catalog visitor (later) | At least one successful publish exists | Open home → see listed entry → open it → read title, body, bound attribution anonymously | Not the author; outside write session; substance + attribution match publish | Leaves home without opening → job not yet observed for that visit | CAP-01, CAP-03, CAP-04 |
| J-04 | Second distinct author + catalog visitor | First article already public (Single) | Second author establishes identity → publishes → visitor sees **both** on home and reads each with correct substance + attribution | First entry not displaced or re-attributed; Multi occupancy holds | Incomplete second publish → first remains; second absent | CAP-01, CAP-02, CAP-03, CAP-04 |
| J-05 | Catalog visitor | Home shows a listed public entry after reported publish success | Attempts to open the listed entry | Must reach successful public read of matching title, body, attribution — dead listing fails the product | If open fails or substance drifts → INIT kill via fidelity loop | CAP-03, CAP-04 |
| J-06 | Would-be publisher | Attempts invalid publish | Submit without identity, or with identity but missing title/body | Catalog state unchanged; no public success | Retries with identity + full substance → joins J-02 | CAP-02 |

Brief-omitted / C1–C2-diverged paths retained: **J-05** (list↔read integrity as first-class journey), catalog **Empty/Single/Multi** framing in J-01/J-02/J-04, **attribution binding** via CAP-04/REQ-08, and explicit **non-elevation** of same-author accumulation.

## 13. Domain terms

| Term | Meaning in this INIT | Collision with existing product? |
|------|----------------------|----------------------------------|
| Catalog visitor | Person observing or reading the public catalog; anonymous allowed; “later visitor” when used to prove publish | Prefer over C2 “outside observer” as the catalog-facing actor name |
| Publishing author | Person with minimum identity who can advance catalog state by publish | None in meta PRDs |
| Second distinct author | Different identity whose publish must yield Multi occupancy with prior entries | Lead lock |
| Public catalog | Durable set of published articles visible beyond any write session | None |
| Empty / Single / Multi | Catalog states: Empty = zero public entries; Single = exactly one public entry; Multi = ≥2 coexisting public entries after a second distinct author. “Occupied” means non-Empty (Single or Multi). | Framing unique to this INIT |
| Home listing | The home discovery surface presenting catalog state | Discovery lock — not tags/feeds |
| List↔read integrity | Every home-listed public entry opens to matching published substance | Whole-product seam C1/C2 under-weighted |
| Author attribution / bound attribution | Public identity of the publishing author, shown consistently on list and read | Exact label → OQ-02 |
| Substance fidelity | Later read shows the same title and body that were published | Paired with attribution binding for the full loop |
| Write session | Author’s authenticated context in which publish was performed | Later visitor must be outside this |

---

## Stop

Living draft PRD at `prd/INIT-REALWORLD-001.md`, promoted from C3. Think candidates under `prd/reports/` remain lineage only.
