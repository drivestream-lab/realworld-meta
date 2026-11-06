---
schema_version: 1
initiative: INIT-REALWORLD-001
map_revision: 2
source_prd: prd/INIT-REALWORLD-001.md
source_prd_digest: sha256:76337dd4c9bdf53b0fc60512baa8f97800699e16828fcbaf63562134686a1038
previous_revision: 1
previous_artifact_commit: b9ad144b9039dd7427c049b9c75d44650b39d79f
change_reason: >-
  Supersede closed PR #1 C3 catalog-loop map with validated C4 membership-gated
  peer publishing commons (CAP-01..05, CTR-01..06); material scope widen on
  api+web
material_change: true
generated_at: 2026-11-06T10:43:01Z
---

# Impact map — INIT-REALWORLD-001 — revision 2

> This file is generated locally before PR creation and becomes the scope source
> of truth when committed. Effective approval is derived from a tech-lead
> GitHub APPROVED review on the exact current meta PR head SHA; dynamic PR state
> is not stored in this artifact's frontmatter.

## T0 identity collision (resolved under Hermes host)

```yaml
identity_collision:
  detection: same-initiative
  evidence:
    - "Closed PR https://github.com/drivestream-lab/realworld-meta/pull/1 — title [INIT-REALWORLD-001] PRD draft; state CLOSED 2026-11-06; head chore/INIT-REALWORLD-001-prd"
    - "Remote branch remotes/origin/chore/INIT-REALWORLD-001-prd still present with prior Impact-Map revision 1 (C3 catalog framing; PRD digest sha256:4552dc6384ee851456014fc9738186bf1a068dc3c23246b0de693e1d8e1de926)"
    - "Local develop has untracked promoted C4 PRD prd/INIT-REALWORLD-001.md + validation/resolution reports; no local Impact-Map before this revision"
    - "No other INIT id / open PR competing for this product initiative"
  recommended_resolution: supersede-existing
  human_decision: supersede-existing
  decision_authority: hermes-host-non-interactive
  external_action_authorized: false
  notes: >-
    Closed draft already ended GitHub competition; no close/comment/update
    authorized this run. Map revision 2 supersedes revision 1 content for the
    same INIT. T0 restarted after lock; mapping continued.
```

## 1. Source and revision

| Field | Value |
|-------|-------|
| PRD | `prd/INIT-REALWORLD-001.md` |
| PRD digest | `sha256:76337dd4c9bdf53b0fc60512baa8f97800699e16828fcbaf63562134686a1038` |
| Map revision | `2` |
| Previous revision | `1` |
| Previous artifact commit | `b9ad144b9039dd7427c049b9c75d44650b39d79f` |
| Change reason | Supersede closed PR #1 C3 map with validated C4 membership-gated commons (CAP-01..05, CTR-01..06) |
| Material change | yes — product framing, capabilities, contracts, and per-repo scope digests all changed vs revision 1 |

**Catalog resolved:** `config/service-catalog-drivestream-lab.yaml` (org `drivestream-lab` from unique `governance-drivestream-lab.yaml`). Catalog has no `owns` / `depends_on` fields; matching used service `description` + stack roles + PRD §3/§8 (`realworld-api` provider, `realworld-web` consumer, `realworld-local` compose support only).

## 2. Affected repositories

| Service | Repo | Team | Scope summary | Scope digest | Spec to create | Confidence |
|---------|------|------|---------------|--------------|----------------|------------|
| realworld-api | drivestream-lab/realworld-api | @drivestream-lab/backend-devs | Provide membership-gated peer publishing commons API: guest feed/article/tag/profile reads; register/login/logout session gate; own-article publish/edit/delete; private peer favorites; self profile update; bind CTR-01..CTR-06 for realworld-web | `sha256:6eb5eab022770d48538d7f6df6eb665737abbbdbb4f628dd2c2fb2fd61346664` | `INIT-REALWORLD-001-api.md` | High |
| realworld-web | drivestream-lab/realworld-web | @drivestream-lab/frontend-devs | Consume CTR-01..CTR-06 for guest commons UI, membership gate UX, member publish/edit/delete, private favorites, and self profile maintain; refuse gated actions without session; dual-role guest visibility after publish | `sha256:eb429c8a0caf45ae3092f3a2db505abf75d041229c8e526f5d040b1d7862f344` | `INIT-REALWORLD-001-web.md` | High |

**Capability → service match (semantic):**

| CAP / contracts | realworld-api | realworld-web |
|-----------------|---------------|---------------|
| CAP-01 open commons reading (CTR-04 + article/profile reads) | Global feed, article body, tag lanes, empty states; delete clears public indexes | Guest feed / article / tag / empty UX |
| CAP-02 membership establishment & session gate (CTR-01, CTR-02) | Register uniqueness; login/logout session; fail-closed invalid creds; incomplete registration creates no member | Register / login / logout UX; gated-action refusal after logout |
| CAP-03 member contribution lifecycle (CTR-03) | Immediate publish; owner-only edit/delete; peer/unauth write denial | Editor publish/edit/delete UX; surface ownership/auth refusals |
| CAP-04 member-private peer bookmarks (CTR-05) | Favorite/unfavorite non-owned; private list; persist across logout; clear on source delete; guest list open denied | Favorite controls + private favorites list UX; guest denial |
| CAP-05 public membership presence (CTR-06) | Public profile + bio + authored published list; self-only update | Profile view + self-edit UX; peer update refusal |

## 3. Deferred repositories

| Service | Repo | Reason | Revisit condition |
|---------|------|--------|-------------------|
| realworld-local | drivestream-lab/realworld-local | Compose wiring for api+web on `adh_local` / DB `realworld` — no product CAP/REQ; PRD marks local as delivery support only | Revisit if local prove cannot run guest commons + membership gate + publish/favorite/profile against the shared stack, or if compose env/ports must change for CTR-01..06 |

## 4. Transitively affected repositories

| Service | Repo | Depends on | Potential impact | Disposition |
|---------|------|------------|------------------|-------------|
| realworld-local | drivestream-lab/realworld-local | realworld-api, realworld-web (inferred from catalog description “api+web compose”; catalog has no explicit `depends_on`) | May need env/health updates if api/web contract surfaces change for local UAT prove | monitor (deferred product scope) |

## 5. Not affected

| Service | Repo | Reason |
|---------|------|--------|
| realworld-meta | drivestream-lab/realworld-meta | Meta control-plane hosts PRD/impact artifacts only; does not implement commons, membership, favorites, or profile product capabilities |

## 6. Cross-repository contracts

| Contract ID | Provider repo | Consumer repo | Capability | Owner | Status |
|-------------|---------------|---------------|------------|-------|--------|
| CTR-01 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-02 — establish / end member session | @drivestream-lab/backend-devs (provider) | new |
| CTR-02 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-02 — register member identity | @drivestream-lab/backend-devs (provider) | new |
| CTR-03 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-03 — publish / update / delete article | @drivestream-lab/backend-devs (provider) | new |
| CTR-04 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-01 — index published articles (global + by tag) | @drivestream-lab/backend-devs (provider) | new |
| CTR-05 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-04 — maintain private peer favorites | @drivestream-lab/backend-devs (provider) | new |
| CTR-06 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-05 — read / update public profile | @drivestream-lab/backend-devs (provider) | new |

> Status `new` is relative to `develop` (prior closed-PR CTR-01..03 C3 semantics never merged). Revision-diff vs map rev 1 treats those prior contract ids as superseded by this CTR set.

## 7. Dependency and build order

```text
drivestream-lab/realworld-api → drivestream-lab/realworld-web
```

| Repo | Depends on | Reason |
|------|------------|--------|
| drivestream-lab/realworld-api | none | Provider of CTR-01..06; no catalog `depends_on` |
| drivestream-lab/realworld-web | drivestream-lab/realworld-api | Consumer of CTR-01..06; guest/member UI cannot prove without provider |

## 8. Revision diff

| Repo | Prior status | Current status | Scope digest changed? | Change |
|------|--------------|----------------|-----------------------|--------|
| drivestream-lab/realworld-api | affected | affected | yes | widened — C3 catalog/publish/read → C4 CAP-01..05 + CTR-01..06 |
| drivestream-lab/realworld-web | affected | affected | yes | widened — same product widen on consumer UI |
| drivestream-lab/realworld-local | deferred | deferred | n/a | unchanged disposition (still compose monitor) |
| drivestream-lab/realworld-meta | not affected | not affected | n/a | unchanged |

## 9. Downstream ripple ledger

| Repo | In-flight artifact | Required action | Reason | Owner | Blocking |
|------|--------------------|-----------------|--------|-------|----------|
| drivestream-lab/realworld-api | none | open | Widened in revision 2; no merged/in-flight app spec from closed PR #1 | @drivestream-lab/backend-devs | no |
| drivestream-lab/realworld-web | none | open | Widened in revision 2; no merged/in-flight app spec from closed PR #1 | @drivestream-lab/frontend-devs | no |
| drivestream-lab/realworld-local | none | hold | Deferred / monitor only | @drivestream-lab/platform-devs | no |
| drivestream-lab/realworld-meta | none | continue | Not affected; hosts this map only | @drivestream-lab/platform-devs | no |

## 10. Open questions

| ID | Lane | Question | Owner | Blocking | Required by | Default if deferred | Status |
|----|------|----------|-------|----------|-------------|---------------------|--------|
| IM-01 | PE | Must `realworld-local` compose change for CTR-01..06 UAT prove, or is current api+web wiring enough? | @drivestream-lab/platform-devs | no | local prove | Hold local; open only if prove cannot run guest/member journeys | open |
| — | PM | PRD OQ-01..OQ-09 remain non-blocking product defaults in `prd/INIT-REALWORLD-001.md` (email optional, newest-published feed, durable reopen, soft/hard delete ok, bylines follow current identity, unfavorite on both surfaces, session until logout, no favorite-count mandate, logout cue optional) | PM / PE per PRD | no | spec-draft / feasibility | Use PRD defaults | open (non-blocking) |

> **Gate 1:** any row with `Blocking: yes` and `Status: open` **closes**
> coding-readiness / Gate 1 until resolved or deferred with default
> (`prayog-skills/references/id-conventions.md`). No blocking IM rows — Gate 1 may open after matching tech-lead APPROVED on current head.

## 11. PR readiness handoff

| Item | Value |
|------|-------|
| Verdict | PR READY |
| Collision detection | same-initiative → supersede-existing (Hermes-locked; T0 restarted) |
| Collision evidence | Closed PR #1 + remote `chore/INIT-REALWORLD-001-prd` with rev-1 C3 map; local promoted C4 PRD + Validation-Report rev 4 clean; no open competing PR |
| Human resolution | supersede-existing |
| Resolution completed | yes — T0 was rerun after Hermes lock; PR already CLOSED so no further GitHub mutation authorized/needed |
| Existing PR | none open (closed: https://github.com/drivestream-lab/realworld-meta/pull/1) |
| Proposed branch | `chore/INIT-REALWORLD-001-prd` |
| Proposed base | `develop` |
| Proposed title | `[INIT-REALWORLD-001] PRD — Membership-gated peer publishing commons` |
| Files to commit | `prd/INIT-REALWORLD-001.md`, `prd/reports/Impact-Map-INIT-REALWORLD-001.md`, `prd/reports/Validation-Report-INIT-REALWORLD-001.md`, `prd/reports/Resolution-INIT-REALWORLD-001.md`, related think/quality/hermes reports under `prd/reports/` as approved lineage |
| Reviewer | @drivestream-lab/platform-devs |
| Initial Gate 1 label | `impact-map-pending` |
| Additional invalidation label | `impact-map-revised` (recommended on publish because map_revision advanced past closed-PR rev 1) |
| Blocking items | none |

**No GitHub side effects have occurred.** Publish via `/open-draft-pr` (or ForgeClient on `prd-pr-action`) after authorization. This skill does not open the PR.

### Proposed Draft PR body

```markdown
## Product change
INIT-REALWORLD-001 delivers a membership-gated peer publishing commons (API + web): guests browse the global feed, articles, tag lanes, and public profiles without an account; members register/login to publish/edit/delete their own tagged markdown articles, privately favorite peers’ articles, and update their own profile — with those privileges revoked on logout while guest reading remains open.

## Impact-map summary
- Revision: 2
- PRD digest: `sha256:76337dd4c9bdf53b0fc60512baa8f97800699e16828fcbaf63562134686a1038`
- Affected repos: drivestream-lab/realworld-api, drivestream-lab/realworld-web
- Deferred repos: drivestream-lab/realworld-local (compose monitor)
- Blocking questions: none
- Artifact: `prd/reports/Impact-Map-INIT-REALWORLD-001.md`
- Supersedes: closed PR #1 revision-1 C3 catalog map

## Gate 1 — engineering handoff readiness
- [ ] Product/domain blocking questions are resolved in committed artifacts
- [ ] Impact-map scope and dependency order are complete
- [ ] PRD digest and map revision match this PR head
- [ ] PE/tech lead has reviewed the exact current head

Requested reviewer: @drivestream-lab/platform-devs
Initial label: `impact-map-pending`
Additional label on publish: `impact-map-revised`
```

## 12. Approval request (after Draft PR creation)

Tech lead must review this artifact on the meta PR and submit GitHub
**Approve** on the exact PR head SHA using:

```text
Impact map approved
initiative: INIT-REALWORLD-001
map_revision: 2
meta_pr_head_sha: {SHA after this artifact is committed}
prd_digest: sha256:76337dd4c9bdf53b0fc60512baa8f97800699e16828fcbaf63562134686a1038
artifact: prd/reports/Impact-Map-INIT-REALWORLD-001.md
```

The gate remains closed until the review, current PR head SHA, PRD digest, map
revision, and artifact path all match.

All Gate 1 labels must be provisioned before PR creation/update:

```bash
launchpad apply-gates --meta --apply
```

Apply labels through the GitHub REST issues-label endpoint and request team
review through the REST `requested_reviewers` endpoint. Do not use `gh pr edit`
for these operations because its GraphQL path may fail on deprecated Projects
Classic fields.

PE updates labels as follows:

| Decision | Remove | Add |
|----------|--------|-----|
| Pending/new revision | `impact-map-lgtm`, `impact-map-blocked` | `impact-map-pending` |
| Request changes/hold | `impact-map-pending`, `impact-map-lgtm` | `impact-map-blocked` |
| Approve current head | `impact-map-pending`, `impact-map-blocked`, `impact-map-revised`, `impact-map-stale` | `impact-map-lgtm` |

---

```yaml
handoff:
  contract: sdd-delivery/v2
  stage: prd-impact-map
  outcome: pass
  artifact:
    path: prd/reports/Impact-Map-INIT-REALWORLD-001.md
    digest: sha256:76337dd4c9bdf53b0fc60512baa8f97800699e16828fcbaf63562134686a1038
  blockers: []
  signals:
    pr_ready: true
    map_revision: 2
    source_prd_digest: sha256:76337dd4c9bdf53b0fc60512baa8f97800699e16828fcbaf63562134686a1038
    affected_repos:
      - drivestream-lab/realworld-api
      - drivestream-lab/realworld-web
    deferred_repos:
      - drivestream-lab/realworld-local
    collision_detection: same-initiative
    recommended_resolution: supersede-existing
    human_decision: supersede-existing
    material_change: true
    scope_digests:
      drivestream-lab/realworld-api: sha256:6eb5eab022770d48538d7f6df6eb665737abbbdbb4f628dd2c2fb2fd61346664
      drivestream-lab/realworld-web: sha256:eb429c8a0caf45ae3092f3a2db505abf75d041229c8e526f5d040b1d7862f344
  next_candidates:
    - prd-pr-action
  human_checkpoint: false
  external_action: true
  forge:
    action: open_draft_pr
    draft: true
    apply_labels:
      - impact-map-pending
    title: "[INIT-REALWORLD-001] PRD — Membership-gated peer publishing commons"
    body_path: prd/reports/Impact-Map-INIT-REALWORLD-001.md
```
