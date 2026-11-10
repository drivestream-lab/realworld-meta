---
schema_version: 1
initiative: INIT-REALWORLD-002
map_revision: 1
source_prd: prd/INIT-REALWORLD-002.md
source_prd_digest: sha256:5a9b49dd102202262edca3cb3d2bf315f43782884372d945be9274124b974c92
previous_revision: null
previous_artifact_commit: null
change_reason: initial map
material_change: true
generated_at: 2026-11-10T08:55:06Z
---

# Impact map — INIT-REALWORLD-002 — revision 1

> This file is generated locally before PR creation and becomes the scope source
> of truth when committed. Effective approval is derived from a tech-lead
> GitHub APPROVED review on the exact current meta PR head SHA; dynamic PR state
> is not stored in this artifact's frontmatter.

## 1. Source and revision

| Field | Value |
|-------|-------|
| PRD | `prd/INIT-REALWORLD-002.md` |
| PRD digest | `sha256:5a9b49dd102202262edca3cb3d2bf315f43782884372d945be9274124b974c92` |
| Map revision | `1` |
| Previous revision | none |
| Previous artifact commit | none |
| Change reason | Initial map after promoted think-4 PRD (validation report rev 3 clean) |
| Material change | yes — first map; establishes affected repo scopes for author-subscription + denial-honest empties |

## 2. Affected repositories

| Service | Repo | Team | Scope summary | Scope digest | Spec to create | Confidence |
|---------|------|------|---------------|--------------|----------------|------------|
| realworld-api | drivestream-lab/realworld-api | @drivestream-lab/backend-devs | Provider for CAP-01..CAP-04 and CTR-01..CTR-04: ungated unpersonalized public discovery; seat-bound author subscribe/unsubscribe with viewer-relative state and reseat persistence; denial-honest empties and fail-closed unseated/self/missing outcomes; subscription-stream lifecycle honesty including publish-in/delete-out and stream privacy. | `sha256:be0c01c3cff0ebd26fabd21761bac6c5f1b10baf4859e82be947b590879e5bd0` | `INIT-REALWORLD-002-api.md` | High |
| realworld-web | drivestream-lab/realworld-web | @drivestream-lab/frontend-devs | Consumer UAT surface for CAP-01..CAP-04 and CTR-01..CTR-04: guest ungated public discovery; seated subscription stewardship UI; denial-honest empty/denied outcomes; subscription-stream vs global/tag surfaces; kill-path prove against API. | `sha256:63d4c2c76934a2659455417bb02885bcc61843a4c5d8b517bc5e966631f1e566` | `INIT-REALWORLD-002-web.md` | High |
| realworld-local | drivestream-lab/realworld-local | @drivestream-lab/platform-devs | Live-prove compose environment joining api+web on adh_local/DB realworld; no product CAP ownership beyond enabling continuous UAT of author-subscription and denial-honest empty kill paths. | `sha256:a43cf05dc8d4ddacef6d61c97b0efe2a7dad7ebe1ed7bbd4060ea5ebf7a1a358` | `INIT-REALWORLD-002-local.md` | High |

Catalog: `config/service-catalog-drivestream-lab.yaml` (org `drivestream-lab` via `config/governance-drivestream-lab.yaml`). Catalog has no explicit `owns` / `depends_on` fields; matching uses `description` + PRD contract seeds (CTR-01..CTR-04) + Lock 1 api↔web seam naming. This meta wave does not open per-repo spec/impl PRs (PRD Lock 1 / non-goals); affected scopes are Gate 1 identity for later eng waves.

## 3. Deferred repositories

| Service | Repo | Reason | Revisit condition |
|---------|------|--------|-------------------|
| — | — | none | — |

## 4. Transitively affected repositories

| Service | Repo | Depends on | Potential impact | Disposition |
|---------|------|------------|------------------|-------------|
| realworld-web | drivestream-lab/realworld-web | drivestream-lab/realworld-api | Consumes CTR-01..CTR-04; any API subscription/discovery contract change requires web client updates | affected (primary) |
| realworld-local | drivestream-lab/realworld-local | drivestream-lab/realworld-api, drivestream-lab/realworld-web | Compose must run api+web together for live prove of subscription and denial-honest empty kill paths | affected (primary) |

No additional transitive-only repos beyond the primary affected set. Catalog lacks `depends_on`; dependency edges inferred from PRD CTR provider→consumer and compose description.

## 5. Not affected

| Service | Repo | Reason |
|---------|------|--------|
| realworld-meta | drivestream-lab/realworld-meta | Tenant control-plane (PRD/impact-map host). No product CAP/REQ implementation; delivers this map via meta PR only. |

## 6. Cross-repository contracts

| Contract ID | Provider repo | Consumer repo | Capability | Owner | Status |
|-------------|---------------|---------------|------------|-------|--------|
| CTR-01 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-01 ungated unpersonalized public discovery | @drivestream-lab/backend-devs | new |
| CTR-02 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-02 seat-bound author-subscription stewardship (+ CAP-03 denial paths on mutate) | @drivestream-lab/backend-devs | new |
| CTR-03 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-04 subscription-stream lifecycle honesty (+ CAP-03 empty-stream honesty) | @drivestream-lab/backend-devs | new |
| CTR-04 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-01/CAP-04 tag-true discovery under subscription churn | @drivestream-lab/backend-devs | new |

## 7. Dependency and build order

```text
drivestream-lab/realworld-api → drivestream-lab/realworld-web → drivestream-lab/realworld-local
```

| Repo | Depends on | Reason |
|------|------------|--------|
| drivestream-lab/realworld-api | none | Contract provider for CTR-01..CTR-04; subscription graph and stream membership source of truth |
| drivestream-lab/realworld-web | drivestream-lab/realworld-api | Consumer of all CTR seams; guest/member UAT surface |
| drivestream-lab/realworld-local | drivestream-lab/realworld-api, drivestream-lab/realworld-web | Compose joins api+web for live kill-path prove |

## 9. Downstream ripple ledger

| Repo | In-flight artifact | Required action | Reason | Owner | Blocking |
|------|--------------------|-----------------|--------|-------|----------|
| — | none | — | Initial map (revision 1); no prior affected repos | — | no |

## 10. Open questions

| ID | Lane | Question | Owner | Blocking | Required by | Default if deferred | Status |
|----|------|----------|-------|----------|-------------|---------------------|--------|
| IM-01 | PM | OQ-01 public follower/following counts vs viewer-relative boolean only | PM | no | spec-draft | Boolean subscription state only; counts out of scope | open |
| IM-02 | PM | OQ-02 ordering rule for global listing vs subscription stream | PM | no | spec-draft | Newest-first by same publish/update time rule as INIT-001 OQ-06 default | open |
| IM-03 | PM | OQ-03 subscribe/unsubscribe targeting missing or deactivated author | PM | no | spec-draft | Fail closed; subscription graph unchanged (REQ-12) | open |
| IM-04 | PM | OQ-04 unknown tag: empty lane vs distinct not-found | PM | no | spec-draft | Empty lane for unknown/blank-normalized tags | open |
| IM-05 | PM | OQ-05 Guest observation of another viewer’s subscription state on public profiles | PM | no | spec-draft | Omit seated-only subscription state for Guest; show subscribe affordance without gating public discovery | open |
| IM-06 | PM | OQ-06 last-unsubscribe empty-stream chrome without re-open | PM | no | later | Same visit after re-check/re-open is enough | open |
| IM-07 | PM | OQ-07 clarification rounds counted per CTR vs per product PR thread | PM | no | later | Per product PR conversation; ≤2 rounds total | open |
| IM-08 | PM | OQ-08 composed subscription ∩ tag surface | PM | no | spec-draft | Separate surfaces only; no composed third surface | open |
| IM-09 | PM | OQ-09 own-author self-subscribe affordance chrome | PM | no | spec-draft | No successful self-subscribe path; hide or disable both fine if REQ-10 holds | open |
| IM-10 | PM | OQ-10 already-subscribed subscribe attempt distinguishability | PM | no | later | Both leave state subscribed; no error required if graph unchanged | open |
| IM-11 | PM | OQ-11 subscription-stream delete-out same-visit without re-open | PM | no | later | Next open of the stream after delete is enough | open |

> **Gate 1:** no Blocking=yes open rows. Spec-draft may consume IM-01..IM-05 and IM-08..IM-09 defaults.

## 11. PR readiness handoff

| Item | Value |
|-------|-------|
| Verdict | PR READY |
| Collision detection | no-collision |
| Collision evidence | Open/closed PRs for INIT-REALWORLD-002: none (`gh pr list --search INIT-REALWORLD-002` empty). Remote heads for 002: none. Local prior Impact-Map for 002: none. Sibling INIT-REALWORLD-001 PRs #1–#7 are a different initiative (unrelated evidence). Single PRD `prd/INIT-REALWORLD-002.md`. |
| Human resolution | none |
| Resolution completed | yes — T0 was rerun after completion |
| Existing PR | none |
| Proposed branch | `chore/INIT-REALWORLD-002-prd` |
| Proposed base | `develop` |
| Proposed title | `[INIT-REALWORLD-002] PRD — Author-subscription trust with denial-honest empties` |
| Files to commit | `prd/INIT-REALWORLD-002.md`, `prd/reports/Impact-Map-INIT-REALWORLD-002.md`, `prd/reports/Validation-Report-INIT-REALWORLD-002.md`, `prd/reports/Resolution-INIT-REALWORLD-002.md` (and companion think/quality/promote reports under `prd/reports/` as approved) |
| Reviewer | @drivestream-lab/platform-devs |
| Initial Gate 1 label | `impact-map-pending` |
| Additional invalidation label | none |
| Blocking items | none |

**No GitHub side effects have occurred.** Publish via `/open-draft-pr` (or orchestrator ForgeClient on `prd-pr-action`) after explicit authorization.

### Proposed Draft PR body

```markdown
## Product change
After INIT-REALWORLD-001’s bulletin/seat baseline, seated members need trustworthy author subscription: subscribe/unsubscribe with viewer-relative state that persists across reseat, a private subscription stream that is an honest projection of current subscriptions (including publish-in and delete-out), and denial-honest empties/fail-closed outcomes for unseated, self, and missing-author attempts. Public discovery stays ungated and unpersonalized. This meta wave lands the product write-up and Impact-Map only — no per-repo spec/impl PRs in this wave.

## Impact-map summary
- Revision: 1
- PRD digest: `sha256:5a9b49dd102202262edca3cb3d2bf315f43782884372d945be9274124b974c92`
- Affected repos: drivestream-lab/realworld-api, drivestream-lab/realworld-web, drivestream-lab/realworld-local
- Deferred repos: none
- Blocking questions: none
- Artifact: `prd/reports/Impact-Map-INIT-REALWORLD-002.md`

## Gate 1 — engineering handoff readiness
- [ ] Product/domain blocking questions are resolved in committed artifacts
- [ ] Impact-map scope and dependency order are complete
- [ ] PRD digest and map revision match this PR head
- [ ] PE/tech lead has reviewed the exact current head

Requested reviewer: @drivestream-lab/platform-devs
Initial label: `impact-map-pending`
```

## 12. Approval request (after Draft PR creation)

Tech lead must review this artifact on the meta PR and submit GitHub
**Approve** on the exact PR head SHA using:

```text
Impact map approved
initiative: INIT-REALWORLD-002
map_revision: 1
meta_pr_head_sha: {SHA after this artifact is committed}
prd_digest: sha256:5a9b49dd102202262edca3cb3d2bf315f43782884372d945be9274124b974c92
artifact: prd/reports/Impact-Map-INIT-REALWORLD-002.md
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

```yaml
handoff:
  contract: sdd-delivery/v2
  stage: prd-impact-map
  outcome: pass
  artifact:
    path: prd/reports/Impact-Map-INIT-REALWORLD-002.md
    digest: sha256:5a9b49dd102202262edca3cb3d2bf315f43782884372d945be9274124b974c92
  blockers: []
  signals:
    pr_ready: true
    map_revision: 1
    collision_detection: no-collision
    affected_repos:
      - drivestream-lab/realworld-api
      - drivestream-lab/realworld-web
      - drivestream-lab/realworld-local
  next_candidates:
    - prd-pr-action
  human_checkpoint: false
  external_action: true
  forge:
    action: open_draft_pr
    draft: true
    apply_labels:
      - impact-map-pending
    title: "[INIT-REALWORLD-002] PRD — Author-subscription trust with denial-honest empties"
    body_path: prd/reports/Impact-Map-INIT-REALWORLD-002.md
```
