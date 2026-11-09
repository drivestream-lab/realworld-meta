---
schema_version: 1
initiative: INIT-REALWORLD-001
map_revision: 1
source_prd: prd/INIT-REALWORLD-001.md
source_prd_digest: sha256:cdc1f66d5cf4c1f12fd0f9ed8bf28d320d4aef941d6abbb0612f53886a1fcfb4
previous_revision: null
previous_artifact_commit: null
change_reason: initial map
material_change: true
generated_at: 2026-11-09T12:19:25Z
---

# Impact map — INIT-REALWORLD-001 — revision 1

> This file is generated locally before PR creation and becomes the scope source
> of truth when committed. Effective approval is derived from a tech-lead
> GitHub APPROVED review on the exact current meta PR head SHA; dynamic PR state
> is not stored in this artifact's frontmatter.

## 1. Source and revision

| Field | Value |
|-------|-------|
| PRD | `prd/INIT-REALWORLD-001.md` |
| PRD digest | `sha256:cdc1f66d5cf4c1f12fd0f9ed8bf28d320d4aef941d6abbb0612f53886a1fcfb4` |
| Map revision | `1` |
| Previous revision | none |
| Previous artifact commit | none |
| Change reason | Initial map after promoted think-4 PRD (validation report rev 3 clean) |
| Material change | yes — first map; establishes affected repo scopes |

## 2. Affected repositories

| Service | Repo | Team | Scope summary | Scope digest | Spec to create | Confidence |
|---------|------|------|---------------|--------------|----------------|------------|
| realworld-api | drivestream-lab/realworld-api | @drivestream-lab/backend-devs | Provider for CAP-01..CAP-06 and CTR-01..CTR-06: public bulletin read, contribution seat (register/login/logout), tagged publish, own-article revise/delete, private favorites shelf, own nameplate self-update; fail-closed unseated/peer denials. | `sha256:cc140afde9cf417ae055bab1bd673579edbc510e09ce1c950203abfbe2b4ba4d` | `INIT-REALWORLD-001-api.md` | High |
| realworld-web | drivestream-lab/realworld-web | @drivestream-lab/frontend-devs | Consumer UAT surface for CAP-01..CAP-06 and CTR-01..CTR-06: guest bulletin browse, seat lifecycle UI, seated publish/revise, private shelf, own nameplate; Wave0a kill-path prove against API. | `sha256:0124a41f5c7c3acba48e93564e5cc8cb84f218d6f7b863c27a98bfc3fcfb7549` | `INIT-REALWORLD-001-web.md` | High |
| realworld-local | drivestream-lab/realworld-local | @drivestream-lab/platform-devs | Wave0a live-prove compose environment joining api+web on adh_local/DB realworld; no product CAP ownership beyond enabling continuous UAT of the three kill paths. | `sha256:c771a5d610f5872dc3a5fc06cfc9e406341840f964ae998a630d9fc5a3ea93d9` | `INIT-REALWORLD-001-local.md` | High |

Catalog: `config/service-catalog-drivestream-lab.yaml` (org `drivestream-lab` via `config/governance-drivestream-lab.yaml`). Catalog has no explicit `owns` / `depends_on` fields; matching uses `description` + PRD contract seeds + Lock 9 prove surface.

## 3. Deferred repositories

| Service | Repo | Reason | Revisit condition |
|---------|------|--------|-------------------|
| — | — | none | — |

## 4. Transitively affected repositories

| Service | Repo | Depends on | Potential impact | Disposition |
|---------|------|------------|------------------|-------------|
| realworld-web | drivestream-lab/realworld-web | drivestream-lab/realworld-api | Consumes CTR-01..CTR-06; any API contract change requires web client updates | affected (primary) |
| realworld-local | drivestream-lab/realworld-local | drivestream-lab/realworld-api, drivestream-lab/realworld-web | Compose must run api+web together for Wave0a live prove | affected (primary) |

No additional transitive-only repos beyond the primary affected set. Catalog lacks `depends_on`; dependency edges inferred from PRD CTR provider→consumer and Lock 9 compose prove.

## 5. Not affected

| Service | Repo | Reason |
|---------|------|--------|
| realworld-meta | drivestream-lab/realworld-meta | Tenant control-plane (PRD/impact-map host). No product CAP/REQ implementation; delivers this map via meta PR only. |

## 6. Cross-repository contracts

| Contract ID | Provider repo | Consumer repo | Capability | Owner | Status |
|-------------|---------------|---------------|------------|-------|--------|
| CTR-01 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-01 public bulletin reading | @drivestream-lab/backend-devs | new |
| CTR-02 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-02 contribution seat lifecycle | @drivestream-lab/backend-devs | new |
| CTR-03 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-03 seated bulletin contribution | @drivestream-lab/backend-devs | new |
| CTR-04 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-04 seated own-work revision | @drivestream-lab/backend-devs | new |
| CTR-05 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-05 private shelf | @drivestream-lab/backend-devs | new |
| CTR-06 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-06 own nameplate | @drivestream-lab/backend-devs | new |

## 7. Dependency and build order

```text
drivestream-lab/realworld-api → drivestream-lab/realworld-web → drivestream-lab/realworld-local
```

| Repo | Depends on | Reason |
|------|------------|--------|
| drivestream-lab/realworld-api | none | Contract provider for CTR-01..CTR-06; bulletin/seat source of truth |
| drivestream-lab/realworld-web | drivestream-lab/realworld-api | Consumer of all CTR seams; Wave0a UAT surface |
| drivestream-lab/realworld-local | drivestream-lab/realworld-api, drivestream-lab/realworld-web | Compose joins api+web for live kill-path prove (Lock 9) |

## 9. Downstream ripple ledger

| Repo | In-flight artifact | Required action | Reason | Owner | Blocking |
|------|--------------------|-----------------|--------|-------|----------|
| — | none | — | Initial map (revision 1); no prior affected repos | — | no |

## 10. Open questions

| ID | Lane | Question | Owner | Blocking | Required by | Default if deferred | Status |
|----|------|----------|-------|----------|-------------|---------------------|--------|
| IM-01 | PM | OQ-01 registration field/uniqueness set | PM | no | spec-draft | Unique username + unique email + password; bio/image via nameplate | open |
| IM-02 | PM | OQ-02 tag normalization limits | PM | no | spec-draft | Free-form; reject blank; ≥1 non-blank tag | open |
| IM-03 | PM | OQ-03 nameplate editable vs identity-locked fields | PM | no | spec-draft | Bio/image editable; username/email locked | open |
| IM-04 | PM | OQ-04 register-may-seat vs login-required | PM | no | spec-draft | Eligibility only; login before contribution | open |
| IM-05 | PE | OQ-05 multi-session logout cascade | PE | no | later | Unseat logging-out session only | open |
| IM-06 | PM | OQ-06 global feed ordering | PM | no | spec-draft | Newest-first by publish/update time | open |
| IM-07 | PM | OQ-07 favorite missing/deleted article | PM | no | spec-draft | Fail closed; shelf unchanged | open |
| IM-08 | PM | OQ-08 Guest open-by-reference after delete | PM | no | spec-draft | Stable not-found; no prior body | open |
| IM-09 | PE | OQ-09 mid-read refresh vs next navigation after delete | PE | no | later | Next navigation / reopen sufficient | open |

> **Gate 1:** no Blocking=yes open rows. Spec-draft may consume IM-01..IM-04 and IM-06..IM-08 defaults.

## 11. PR readiness handoff

| Item | Value |
|------|-------|
| Verdict | PR READY |
| Collision detection | no-collision |
| Collision evidence | Open PRs: none. Remote branches `chore/INIT-REALWORLD-001-prd` and `kb/enrich-init-realworld-001` deleted after fetch prune. Historical same-INIT PRs closed/merged+reverted: #1 CLOSED, #2 MERGED then develop revert `3f429c0`, #4 CLOSED. Local prior Impact-Map: none. Single PRD `prd/INIT-REALWORLD-001.md`. |
| Human resolution | none |
| Resolution completed | yes — T0 was rerun after completion |
| Existing PR | none |
| Proposed branch | `chore/INIT-REALWORLD-001-prd` |
| Proposed base | `develop` |
| Proposed title | `[INIT-REALWORLD-001] PRD — Public bulletin with session-bound contribution seat` |
| Files to commit | `prd/INIT-REALWORLD-001.md`, `prd/reports/Impact-Map-INIT-REALWORLD-001.md`, `prd/reports/Validation-Report-INIT-REALWORLD-001.md`, `prd/reports/Resolution-INIT-REALWORLD-001.md` (and companion think/quality reports under `prd/reports/` as approved) |
| Reviewer | @drivestream-lab/platform-devs |
| Initial Gate 1 label | `impact-map-pending` |
| Additional invalidation label | none |
| Blocking items | none |

**No GitHub side effects have occurred.** Publish via `/open-draft-pr` (or orchestrator ForgeClient on `prd-pr-action`) after explicit authorization.

### Proposed Draft PR body

```markdown
## Product change
Wave0a UAT needs a clean-slate Conduit-shaped public bulletin anyone can read without an account, plus a contribution seat obtained only by register+login so members can publish tagged markdown, keep a private favorites shelf, and revise their own nameplate. Logout must drop the seat while guest reading stays open. Kill paths: guest bulletin read, seated auth+publish, post-logout seat denial — without comments, follows, personalized feeds, OAuth, or who-favorited social proof.

## Impact-map summary
- Revision: 1
- PRD digest: `sha256:cdc1f66d5cf4c1f12fd0f9ed8bf28d320d4aef941d6abbb0612f53886a1fcfb4`
- Affected repos: drivestream-lab/realworld-api, drivestream-lab/realworld-web, drivestream-lab/realworld-local
- Deferred repos: none
- Blocking questions: none
- Artifact: `prd/reports/Impact-Map-INIT-REALWORLD-001.md`

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
initiative: INIT-REALWORLD-001
map_revision: 1
meta_pr_head_sha: {SHA after this artifact is committed}
prd_digest: sha256:cdc1f66d5cf4c1f12fd0f9ed8bf28d320d4aef941d6abbb0612f53886a1fcfb4
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

```yaml
handoff:
  contract: sdd-delivery/v2
  stage: prd-impact-map
  outcome: pass
  artifact:
    path: prd/reports/Impact-Map-INIT-REALWORLD-001.md
    digest: sha256:cdc1f66d5cf4c1f12fd0f9ed8bf28d320d4aef941d6abbb0612f53886a1fcfb4
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
    title: "[INIT-REALWORLD-001] PRD — Public bulletin with session-bound contribution seat"
    body_path: prd/reports/Impact-Map-INIT-REALWORLD-001.md
```
