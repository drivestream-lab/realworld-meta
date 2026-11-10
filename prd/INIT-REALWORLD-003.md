# INIT-REALWORLD-003: Replay-ready personal search memory

| Field | Value |
|-------|-------|
| Initiative | INIT-REALWORLD-003 |
| Status | promoted |
| Brief | Lead conversation (Floor wave guinea-pig INIT — human mode; saved-searches outline) |
| Promoted from | `prd/reports/INIT-REALWORLD-003-prd-think-2.md` (C2 via `/prd-quality` + Hermes promote brief `recommend: C2`) |
| Score | `/prd-quality` — C2 recommended; promote authorized |
| Series | think 2 of 4 — C2; prior `prd/reports/INIT-REALWORLD-003-prd-think.md` (C1 owner-private query-bookmark shelf) deliberately **not** cloned — reframes job as **replay-ready personal search memory** (park → recall continuity) |
| Product context | Sibling `prd/INIT-REALWORLD-001.md` (promoted; private favorites shelf — noun collision avoided); sibling `prd/INIT-REALWORLD-002.md` (promoted; author subscription — not reopened); `config/service-catalog-drivestream-lab.yaml` (realworld-api, realworld-web, realworld-local, realworld-meta); `planning/` skipped (README only) |
| Companions | `/grilling`, `/domain-modeling`, `/opportunity-solution-tree`, `/strategy-red-team` not installed — inline Challenge / Model / Stress |
| Host mode | Non-interactive Hermes — T1 locks applied from Lead-approved brief; no AskQuestion |

## 1. Job and outcome

- **Job:** Give a **signed-in reader** a durable, **owner-private memory of parked search intents** — each park keeps the query text (and an optional mnemonic label) — so they can **recall that same query text later** to continue discovery without retyping, and so no other actor can harvest or alter those parks.
- **Why now:** Floor-wave guinea-pig INIT (human mode) needs a tiny, proveable RealWorld slice that exercises ownership-private create/list/delete on `realworld-api` while product truth lands in `realworld-meta`, before larger social/discovery expansions.
- **If we do nothing:** Readers lose prior search intents when a session ends; floor-wave has no small ownership-isolation feature to prove; later settings UI has no stewarded parked-intent object to hang on.
- **Solution vs job:** “CRUD under a small saved-searches API, persisted in Postgres” is the **delivery vehicle**. The job is **replay-ready personal search-memory continuity + isolation** — not a settings screen, not share/public links, not a new search ranking product, not auto-executing searches as a kill path, not INIT-001 favorites or INIT-002 subscriptions, and not new infra services.
- **OST fork (T2):** (A) C1-style bookmark-shelf stewardship, (B) **replay-ready parked-intent memory** (chosen / promoted), (C) label-as-unique-slot identity. Outcome **B** is the promoted cut so continuity/recall fidelity is first-class without inventing unique-label product rules the brief did not lock.
- **Kill assumption:** Fails if a seated owner cannot park, recall (list), and discard their own search intents with query text preserved for later reuse, or if an unauthorized actor (guest, post-logout, or peer member) can observe or mutate another member’s parks.

## 2. Locked decisions

Lead-approved brief treated as T1 locks (applied; not re-asked), plus grill consequences required for a coherent replay-ready search-memory product:

1. **(Programme note)** Floor-wave guinea-pig INIT in human mode; product changes stay inside **`realworld-api` + `realworld-meta`**; no new infra services.
2. A seated reader may **park** a search as a query string with an **optional mnemonic label**.
3. A seated reader may **list (recall)**, **relabel**, and **discard** **only their own** parked searches.
4. Parked searches **persist durably** across sessions for the owning membership (brief delivery vehicle names Postgres; product lock is durable retention — storage engine is engineering).
5. **No share / public** parked searches in this INIT.
6. **Settings UI list** (and other web UI for this feature) is **out of scope** for this INIT; continuity is proven on the **machine-consumable API surface** of `realworld-api`.
7. Success bar named by Lead: **create + list + delete** work for the owning user; unauthorized users cannot see others’ saves (relabel remains in-scope stewardship per lock 3).
8. **(This grill)** “Signed-in reader” means a **seated member** under INIT-REALWORLD-001 seat rules; guests and post-logout actors are unseated.
9. **(This grill)** A parked search is a **replay-ready intent record**: the retained query string must be **re-presentable unchanged** on owner recall so a later discovery step can reuse that text; save does **not** require current article hits, and this INIT does **not** invent a new ranking product.
10. **(This grill)** **Relabel** means changing the optional **mnemonic label** only; changing the parked query string after create is deferred (OQ-01).
11. **(This grill)** Ownership isolation is load-bearing: peer members must not list, inspect, relabel, or discard another member’s parks; unseated park/list/relabel/discard fail closed.
12. **(This grill)** Parks **persist across unseat/reseat** for the same membership (logout drops the seat, not the memory); after reseat, owner recall reflects parks that existed before logout unless changed while seated.
13. **(This grill)** Empty own-recall set is a valid outcome (including after discarding the last park).
14. **(This grill)** INIT-REALWORLD-001 favorites shelf and INIT-REALWORLD-002 author-subscription rules are **not** reopened; parked search memory is a separate private retention object.
15. **(This grill)** Owner recall must expose each park’s **query string** (and label if present) so continuity is observable without a UI this INIT.
16. **(This grill)** Empty or whitespace-only query text is **not** a parkable intent (reject create; no record created).
17. **(This grill)** Route paths, payload layouts, frameworks, and module names stay out of product REQ text; engineering consumes the WHAT + CTR absence + OQs.

## 3. In scope / non-goals

### In scope

- Seated park of an owner-private search intent (non-empty query string required; mnemonic label optional).
- Seated recall (list) of **own** parks with query text + label fidelity (populated or empty).
- Seated relabel of **own** park mnemonic.
- Seated discard of **own** park.
- Durable retention across unseat/reseat for the owning membership.
- Fail-closed denial for unseated stewardship attempts.
- Fail-closed isolation so peers cannot observe or mutate another’s parks.
- Product write-up in `realworld-meta`; implementation ownership on `realworld-api` only for this feature surface.

### Non-goals (load-bearing)

- Share / public / collaborative saved searches.
- Settings (or any) **web UI** list/management for this INIT (`realworld-web` feature work deferred).
- New infra services beyond existing catalog services.
- Reopening INIT-REALWORLD-001 publish / seat / favorites / nameplate requirement sets.
- Reopening INIT-REALWORLD-002 author subscription / subscription-stream rules.
- Inventing a new article-search ranking, relevance, or full-text product beyond retaining the reader’s query string.
- **Auto-running** a parked query against the bulletin as a required success path this INIT (replay *readiness* of the retained string is in scope; automatic execution is adjacent — OQ-02).
- Treating labels as unique slot identities (label-as-identity packaging deferred to a later think / OQ-06).
- Comments, OAuth, email verification, mobile/native clients.
- Admin/moderation tooling over other members’ parks.
- Cross-member transfer or export programmes.

## 4. Actors

| Actor | Can actually | Cannot / OQ |
|-------|----------------|-------------|
| Guest (unseated) | Continue INIT-001/002 ungated bulletin behaviors unchanged by this INIT | Park/list/relabel/discard search memory; observe any member’s parks |
| Seated member (owner) | Park, recall, relabel, discard **own** search intents; see own parks after reseat with query text intact | Observe or mutate a peer’s parks; keep stewardship after logout; share parks publicly; require UI this INIT |
| Peer member | Steward only their own parks | Inspect, relabel, or discard another member’s parks; harvest another’s query text via list or direct access |
| Programme UAT / API prove observer | Drive owner vs peer vs unseated paths against `realworld-api` to judge the kill assumption | Not an in-product role; must not require settings UI this INIT |

## 5. Capabilities

| ID | Capability | Journeys covered | Notes |
|----|------------|------------------|-------|
| CAP-01 | Park a personal search intent | J-01, J-02, J-08, J-12 | Non-empty query + optional mnemonic; seated-only; refuse empty/whitespace |
| CAP-02 | Recall and maintain own search memory | J-01, J-02, J-03, J-04, J-05, J-08, J-10 | List with query fidelity; relabel mnemonic; discard; empty recall valid; persist across reseat |
| CAP-03 | Private continuity isolation | J-06, J-07, J-09, J-11 | Peer opacity (no query harvest); unseated fail-closed; missing/non-owned mutate denied |

Divergence from C1: C1 packaged **owner-private query-bookmark shelf** (create/steward/isolation as collection CRUD). C2 packages **replay-ready personal search memory** — park → recall continuity with **query-string fidelity on list**, explicit reject of empty parks, and auto-run kept non-goal. Later thinks should still diverge (e.g. label-as-identity slots, discovery-session MRU) rather than clone this CAP/REQ table.

## 6. Requirements

| ID | CAP | Requirement (WHAT) | Condition / event | Observable result | Evidence |
|----|-----|--------------------|-------------------|-------------------|----------|
| REQ-01 | CAP-01 | Park a search intent with a mnemonic label | Seated member parks a non-empty query string and a non-empty label | An owner-private park exists with that exact query string and that label; owner recall shows both | live (CAP-01, J-01) |
| REQ-02 | CAP-01 | Park a search intent without a label | Seated member parks a non-empty query string and omits a label | An owner-private park exists with that exact query string and no label; owner recall shows the unlabeled park | live (CAP-01, J-02) |
| REQ-03 | CAP-01 | Refuse park of empty or whitespace-only query text | Seated member attempts to park empty or whitespace-only query text | No park is created; owner recall unchanged by that attempt | live (CAP-01, J-12) |
| REQ-04 | CAP-03 | Refuse park while unseated | Guest or post-logout actor attempts to park a search intent | No new park is created for any membership | live (CAP-03, J-07) |
| REQ-05 | CAP-02 | Recall only the owner’s parks with query fidelity | Seated member requests their search-memory list when they own zero or more parks | List contains exactly that member’s parks (or empty); each listed park presents its retained query string (and label if any); no other member’s parks appear | live (CAP-02, J-03) |
| REQ-06 | CAP-02 | Relabel an owned park | Seated member changes the mnemonic label on a park they own | Subsequent owner recall shows the updated label; retained query string unchanged | live (CAP-02, J-04) |
| REQ-07 | CAP-02 | Discard an owned park | Seated member discards a park they own | That park no longer appears on the owner’s recall list | live (CAP-02, J-05) |
| REQ-08 | CAP-02 | Persist parks across unseat and reseat | Seated member parks an intent, logs out, then logs in again without changing parks while unseated | After reseat, owner recall still includes that park with the same query string | live (CAP-02, J-08) |
| REQ-09 | CAP-02 | Allow empty own-recall after the last discard | Seated member discards their last remaining park | Owner recall list is empty and valid (not an error wall) | live (CAP-02, J-10) |
| REQ-10 | CAP-03 | Keep one member’s parks invisible to another seated member | Member A owns ≥1 park; Member B is seated and is not A | B cannot obtain A’s park contents (including query text) via list or direct access | live (CAP-03, J-06) |
| REQ-11 | CAP-03 | Refuse relabel or discard of another member’s park | Seated peer attempts to relabel or discard Member A’s park | A’s park unchanged; peer’s own recall unchanged by that attempt | live (CAP-03, J-09) |
| REQ-12 | CAP-03 | Deny list / relabel / discard while unseated | Guest or post-logout actor attempts list, relabel, or discard | No park contents of any member are disclosed as a successful recall result; no relabel/discard side effects | live (CAP-03, J-07) |
| REQ-13 | CAP-03 | Refuse mutate of a missing or non-owned park identity | Seated member attempts relabel or discard against a park identity that does not exist for them | Own recall unchanged; fail closed (OQ-03 default) | unit / live (CAP-03, J-11) |

## 7. Negative and failure paths

| REQ | Condition | Required behavior | Why it matters |
|-----|-----------|-------------------|----------------|
| REQ-02 / J-02 | Label omitted | Park still creatable; label absence is valid | Optional mnemonic must not become a hidden required field |
| REQ-03 / J-12 | Empty / whitespace query | Create refused; no park record | Continuity object must carry real query text for later reuse |
| REQ-05 / J-03 | Owner has zero parks | Empty recall list, still seated-only | Empty ≠ error; matches success “list works” |
| REQ-05 | Owner has parks | Listed query strings match what was parked | Replay readiness without auto-run |
| REQ-04 / REQ-12 | Unseated park/list/relabel/discard | Fail closed; no disclosure; no mutations | Kill assumption — seat gate |
| REQ-10 / J-06 | Peer tries to read owner’s parks | Isolation holds; no query harvest | Kill assumption — unauthorized cannot see others’ saves |
| REQ-11 / J-09 | Peer tries to relabel/discard owner’s park | Target unchanged | Isolation beyond read opacity |
| REQ-09 / J-10 | Last park discarded | Empty own-recall allowed | Prevents “must always have one” false rule |
| REQ-13 / J-11 | Missing / non-owned identity | Fail closed; own memory unchanged | Prevents cross-owner leakage via guessed identities |
| REQ-08 / J-08 | Logout then login | Parks still present with same query text | Durable continuity vs session-only memory |

## 8. Contract seeds (semantic)

None — no cross-repo product seam in this INIT. Stewardship is owned and proven on `realworld-api`; `realworld-web` settings UI is an explicit non-goal; `realworld-meta` carries product truth only.

## 9. NFR applicability

| Area | Requirement or N/A rationale |
|------|------------------------------|
| Security | Seat-bound stewardship; unseated and peer access fail closed (REQ-04, REQ-10–REQ-13). No share/public surface. |
| Reliability | N/A beyond fail-closed park/list/discard behavior — not a multi-region SLA INIT. |
| Performance / capacity | N/A for guinea-pig scale; no concurrent-load target locked (per-member count limits → OQ-04). |
| Observability | N/A as product REQ — operational logging is engineering choice. |
| Privacy / data handling | Parks are private to the owning membership; peers and guests must not observe query text or labels (REQ-10, REQ-12). |
| Migration / compatibility | Additive private state for existing members; default empty own-recall. Does not migrate or rewrite INIT-001 favorites. |
| Rollback / recovery | N/A as product REQ — delivery rollback is engineering. |
| Operations / support | No new infra services; prove against existing `realworld-api` (local compose may host prove without expanding product scope to web UI). |

## 10. Assumptions

| ID | Assumption | Status | Dependent REQs | Default if false |
|----|------------|--------|----------------|------------------|
| A-01 | INIT-REALWORLD-001 contribution-seat semantics (login seats, logout unseats) remain the gate for “signed-in reader” | accepted-for-draft | REQ-04, REQ-08, REQ-12 | If seat meaning changed, reopen with Lead before drafting alternate REQs |
| A-02 | Park success does not require the query to match live article hits at save time; fidelity of retained text is enough for replay readiness | accepted-for-draft | REQ-01, REQ-02, REQ-05 | If save must validate against current search results, replace via OQ-02 / CHG |
| A-03 | Relabel is mnemonic-only; query-string edit is not required for this INIT’s kill bar | accepted-for-draft | REQ-06 | If query edit is required, resolve OQ-01 into a REQ |
| A-04 | “Unauthorized cannot see others’ saves” includes both guests and peer seated members, not only anonymous actors | accepted-for-draft | REQ-10, REQ-12 | If peer visibility were allowed, kill assumption would be incoherent — reopen with Lead |
| A-05 | Durable retention means membership-scoped persistence across logout/login, not merely in-process memory | accepted-for-draft | REQ-08 | Session-only memory fails the brief’s persist intent |
| A-06 | Owner recall exposing query text is sufficient continuity proof without a web UI or auto-run this INIT | accepted-for-draft | REQ-05 | If UI or auto-run becomes kill-path, reopen scope with Lead |

## 11. Open questions

| ID | Question | Owner | Blocking | Required-by | Default if deferred |
|----|----------|-------|----------|-------------|---------------------|
| OQ-01 | May the owner change the retained query string after park, or is mutate limited to relabel + discard? | PM | no | spec-draft | Relabel + discard only this INIT; query string immutable after park |
| OQ-02 | Must continuity include auto-running the parked query against the existing article-search surface, or is re-presentable query text enough? | PM | no | spec-draft / later | Re-presentable text enough; auto-run is non-goal this INIT |
| OQ-03 | Exact fail-closed shape for missing vs non-owned park identity (indistinguishable not-found vs explicit forbidden) | PM | no | spec-draft | Indistinguishable not-found to the requester; no park contents disclosed |
| OQ-04 | Per-member maximum number of parks and max query/label lengths | PM | no | spec-draft | Eng reasonableness limits acceptable; blank label treated as “no label” |
| OQ-05 | Owner-recall ordering rule for prove expectations | PM | no | spec-draft | Newest-first by park time; exact timestamp source left to eng |
| OQ-06 | Whether duplicate query strings (same owner, same query, distinct parks) are allowed, and whether labels must be unique per owner | PM | no | spec-draft | Duplicate query parks allowed; labels need not be unique (label-as-identity not chosen this candidate) |
| OQ-07 | Whether clearing a label (relabel to no label) is allowed the same as setting a new mnemonic | PM | no | spec-draft | Allowed — mnemonic may be cleared without discarding the park |

## 12. Journeys

| ID | Actor | Trigger | Main flow | Primary edge | Abandon | Caps exercised |
|----|-------|---------|-----------|--------------|---------|----------------|
| J-01 | Seated member | Wants to keep a named search intent for later reuse | Parks query + label → recalls → sees same query + label | Duplicate query allowed (OQ-06 default) | Abandons before park → no park | CAP-01, CAP-02 |
| J-02 | Seated member | Wants to keep a query without naming it | Parks query with no label → recalls → sees unlabeled park with same query | — | Abandons → no park | CAP-01, CAP-02 |
| J-03 | Seated member | Wants to continue a prior search | Opens own recall list and reads retained query text | Empty list when none parked | Leaves without changes | CAP-02 |
| J-04 | Seated member | Wants a clearer mnemonic | Relabels own park → recalls → sees new label; query unchanged | Clear label to none (OQ-07 default) | Abandons mid-relabel → prior label remains | CAP-02 |
| J-05 | Seated member | No longer wants a parked intent | Discards own park → recalls → absent | — | — | CAP-02 |
| J-06 | Peer member | Tries to harvest another’s search memory | Attempts to list/access Member A’s parks | Denied / no query disclosure | — | CAP-03 |
| J-07 | Guest / post-logout | Tries stewardship without a seat | Attempts park, list, relabel, or discard | Fail closed; no side effects; no disclosure | — | CAP-03 |
| J-08 | Seated member | Relies on continuity across sessions | Parks intent → logs out → logs in → recalls | Same query text still present | — | CAP-01, CAP-02 |
| J-09 | Peer member | Tries to alter another’s park | Attempts relabel or discard of A’s park | A unchanged | — | CAP-03 |
| J-10 | Seated member | Clears the last park | Discards final park → recalls empty | Empty is valid | — | CAP-02 |
| J-11 | Seated member | Uses a bad park identity | Attempts relabel/discard on missing/non-owned id | Fail closed; own recall unchanged | — | CAP-03 |
| J-12 | Seated member | Tries to park empty intent | Attempts park with empty/whitespace query | Refused; recall unchanged | — | CAP-01 |

Brief already listed create / list / rename / delete and unauthorized opacity; **J-03** (recall for continuity with query fidelity), **J-08** (persist across reseat with same query), **J-10** (empty after last discard), **J-11** (missing identity), and **J-12** (refuse empty park) are whole-product paths the outline did not spell out — and they distinguish this candidate from C1’s bookmark-shelf packaging.

## 13. Domain terms

| Term | Meaning in this INIT | Collision with existing product? |
|------|----------------------|----------------------------------|
| Parked search / search memory / saved search | Durable owner-private record retaining a search query string and optional mnemonic label for later recall | “Saved search” is new; do **not** call this the INIT-001 “private shelf” (favorites) |
| Query string | Opaque text the reader parked so they can reuse it later; must re-present unchanged on owner recall | Not a new ranking algorithm; not INIT-002 subscription stream membership |
| Mnemonic label | Optional human-facing handle for which park to resume; relabel edits this field only | Distinct from article tags (INIT-001); not a unique slot id this candidate |
| Owner | Seated membership that parked the intent; sole steward | Aligns with seat-bound ownership patterns; object is new |
| Own-recall / own-list | The set of parks belonging to one membership, returned with query fidelity | Distinct from favorites shelf and subscription stream |
| Replay readiness | Retained query text is available unchanged for a later discovery step; does **not** mean auto-run this INIT | Adjacent to article search; auto-execution is non-goal |
| Unseated | Guest or post-logout actor under INIT-001 seat rules | Same seat vocabulary; no new auth product |

---

## Discovery notes (not scored)

**Promote complete.** Think-2 content is the promoted PRD at `prd/INIT-REALWORLD-003.md` per Hermes promote brief (`recommend: C2`). Inline Challenge / Model / Stress provenance remains in locks and §1 OST fork; not open pipeline stops. Next: `/validate-requirements` (incremental after document updates) → `/prd-impact-map`.
