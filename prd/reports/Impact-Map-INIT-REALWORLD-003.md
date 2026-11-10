---
schema_version: 1
initiative: INIT-REALWORLD-003
map_revision: 1
source_prd: prd/INIT-REALWORLD-003.md
source_prd_digest: sha256:5cccf07066a0333027279aac0cae64d3f3be10773b7a5b37106302f2bbb9ceb8
previous_revision: null
previous_artifact_commit: null
change_reason: initial map
material_change: true
generated_at: 2026-11-10T10:46:44Z
---

# Impact map — INIT-REALWORLD-003 — revision 1

> This file is generated locally before PR creation and becomes the scope source
> of truth when committed. Effective approval is derived from a tech-lead
> GitHub APPROVED review on the exact current meta PR head SHA; dynamic PR state
> is not stored in this artifact's frontmatter.

## 1. Source and revision

| Field | Value |
|-------|-------|
| PRD | `prd/INIT-REALWORLD-003.md` |
| PRD digest | `sha256:5cccf07066a0333027279aac0cae64d3f3be10773b7a5b37106302f2bbb9ceb8` |
| Map revision | `1` |
| Previous revision | none |
| Previous artifact commit | none |
| Change reason | Initial map after promoted think-2 PRD (C2 via Hermes promote; validation report rev 3 clean) |
| Material change | yes — first map; establishes affected repo scopes for replay-ready personal search memory (API-only) |

## 2. Affected repositories

| Service | Repo | Team | Scope summary | Scope digest | Spec to create | Confidence |
|---------|------|------|---------------|--------------|----------------|------------|
| realworld-api | drivestream-lab/realworld-api | @drivestream-lab/backend-devs | Provider for CAP-01..CAP-03 and REQ-01..REQ-13: seated owner-private park/recall/relabel/discard of replay-ready search intents with query-string fidelity on recall; refuse empty/whitespace parks; durable membership retention across unseat/reseat; fail-closed unseated and peer isolation; machine-consumable API prove surface only (no cross-repo CTR this INIT). | `sha256:6e1a5775a890e03ad0295e43e795e36962fd431132a03412cf647282dc8331c7` | `INIT-REALWORLD-003-api.md` | High |

Catalog: `config/service-catalog-drivestream-lab.yaml` (org `drivestream-lab` via `config/governance-drivestream-lab.yaml`). Catalog has no explicit `owns` / `depends_on` fields; matching uses `description` + PRD Lock 1 (product changes in `realworld-api` + `realworld-meta`) + §8 contract seeds (none) + non-goal (no web UI). This meta wave does not open per-repo spec/impl PRs; affected scopes are Gate 1 identity for later eng waves.

## 3. Deferred repositories

| Service | Repo | Reason | Revisit condition |
|---------|------|--------|-------------------|
| realworld-web | drivestream-lab/realworld-web | Settings / any web UI for parked-search stewardship is an explicit non-goal this INIT; no CTR consumer seam (PRD §8). | Later INIT that adds settings (or other) UI for search-memory stewardship |
| realworld-local | drivestream-lab/realworld-local | Compose joins api+web; this INIT proves on the API machine-consumable surface and does not expand product scope to web UI. Optional local API host does not mint a product CAP. | Eng needs compose/env delta specifically for API-only live prove of CAP-01..CAP-03 |

## 4. Transitively affected repositories

| Service | Repo | Depends on | Potential impact | Disposition |
|---------|------|------------|------------------|-------------|
| realworld-web | drivestream-lab/realworld-web | drivestream-lab/realworld-api | Future UI could consume a new parks API; no product seam this INIT | deferred |
| realworld-local | drivestream-lab/realworld-local | drivestream-lab/realworld-api, drivestream-lab/realworld-web | May host API prove without web feature work; no CAP ownership | deferred |

No additional transitive-only repos beyond the deferred set. Catalog lacks `depends_on`; dependency edges inferred from catalog descriptions (SPA consumes API; compose joins api+web) and PRD Lock 1 / §8.

## 5. Not affected

| Service | Repo | Reason |
|---------|------|--------|
| realworld-meta | drivestream-lab/realworld-meta | Tenant control-plane (PRD/impact-map host). No product CAP/REQ implementation; delivers this map via meta PR only. |

## 6. Cross-repository contracts

| Contract ID | Provider repo | Consumer repo | Capability | Owner | Status |
|-------------|---------------|---------------|------------|-------|--------|
| — | — | — | none — PRD §8: no cross-repo product seam; stewardship owned and proven on `realworld-api` | — | — |

## 7. Dependency and build order

```text
drivestream-lab/realworld-api
```

| Repo | Depends on | Reason |
|------|------------|--------|
| drivestream-lab/realworld-api | none | Sole product implementation owner for CAP-01..CAP-03; API prove surface |

## 9. Downstream ripple ledger

| Repo | In-flight artifact | Required action | Reason | Owner | Blocking |
|------|--------------------|-----------------|--------|-------|----------|
| — | none | — | Initial map (revision 1); no prior affected repos | — | no |

## 10. Open questions

| ID | Lane | Question | Owner | Blocking | Required by | Default if deferred | Status |
|----|------|----------|-------|----------|-------------|---------------------|--------|
| IM-01 | PM | OQ-01: May the owner change the retained query string after park, or is mutate limited to relabel + discard? | PM | no | spec-draft | Relabel + discard only this INIT; query string immutable after park | open |
| IM-02 | PM | OQ-02: Must continuity include auto-running the parked query against article search, or is re-presentable query text enough? | PM | no | spec-draft / later | Re-presentable text enough; auto-run is non-goal this INIT | open |
| IM-03 | PM | OQ-03: Exact fail-closed shape for missing vs non-owned park identity | PM | no | spec-draft | Indistinguishable not-found to the requester; no park contents disclosed | open |
| IM-04 | PM | OQ-04: Per-member maximum number of parks and max query/label lengths | PM | no | spec-draft | Eng reasonableness limits acceptable; blank label treated as “no label” | open |
| IM-05 | PM | OQ-05: Owner-recall ordering rule for prove expectations | PM | no | spec-draft | Newest-first by park time; exact timestamp source left to eng | open |
| IM-06 | PM | OQ-06: Whether duplicate query strings (same owner) are allowed, and whether labels must be unique per owner | PM | no | spec-draft | Duplicate query parks allowed; labels need not be unique | open |
| IM-07 | PM | OQ-07: Whether clearing a label (relabel to no label) is allowed the same as setting a new mnemonic | PM | no | spec-draft | Allowed — mnemonic may be cleared without discarding the park | open |

> **Gate 1:** no Blocking=yes open rows. Spec-draft may consume IM-01..IM-07 defaults.

## 11. PR readiness handoff

| Item | Value |
|-------|-------|
| Verdict | PR READY |
| Collision detection | no-collision |
| Collision evidence | Open/closed PRs for INIT-REALWORLD-003: none (`gh pr list --search INIT-REALWORLD-003` empty). Remote heads for 003: none. Local prior Impact-Map for 003: none. Sibling INIT-REALWORLD-001 / INIT-REALWORLD-002 are different initiatives (unrelated evidence). Single promoted PRD `prd/INIT-REALWORLD-003.md`. |
| Human resolution | none |
| Resolution completed | yes — T0 was rerun after completion |
| Existing PR | none |
| Proposed branch | `chore/INIT-REALWORLD-003-prd` |
| Proposed base | `develop` |
| Proposed title | `[INIT-REALWORLD-003] PRD — Replay-ready personal search memory` |
| Files to commit | `prd/INIT-REALWORLD-003.md`, `prd/reports/Impact-Map-INIT-REALWORLD-003.md`, `prd/reports/Validation-Report-INIT-REALWORLD-003.md`, `prd/reports/Resolution-INIT-REALWORLD-003.md` (and companion think/quality/promote reports under `prd/reports/` as approved) |
| Reviewer | @drivestream-lab/platform-devs |
| Initial Gate 1 label | `impact-map-pending` |
| Additional invalidation label | none |
| Blocking items | none |

**No GitHub side effects have occurred.** Publish via `/open-draft-pr` (or orchestrator ForgeClient on `prd-pr-action`) after explicit authorization.

### Proposed Draft PR body

```markdown
## Product change
Signed-in readers need durable, owner-private memory of parked search intents: park a non-empty query (optional mnemonic), recall with exact query-string fidelity, relabel, and discard — with fail-closed isolation from guests, post-logout actors, and peers, and persistence across logout/login. Settings/web UI, share/public, and auto-run are out of scope. This meta wave lands the product write-up and Impact-Map only — implementation ownership is `realworld-api`; no per-repo spec/impl PRs in this wave.

## Impact-map summary
- Revision: 1
- PRD digest: `sha256:5cccf07066a0333027279aac0cae64d3f3be10773b7a5b37106302f2bbb9ceb8`
- Affected repos: drivestream-lab/realworld-api
- Deferred repos: drivestream-lab/realworld-web, drivestream-lab/realworld-local
- Blocking questions: none
- Artifact: `prd/reports/Impact-Map-INIT-REALWORLD-003.md`

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
initiative: INIT-REALWORLD-003
map_revision: 1
meta_pr_head_sha: {SHA after this artifact is committed}
prd_digest: sha256:5cccf07066a0333027279aac0cae64d3f3be10773b7a5b37106302f2bbb9ceb8
artifact: prd/reports/Impact-Map-INIT-REALWORLD-003.md
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
    path: prd/reports/Impact-Map-INIT-REALWORLD-003.md
    digest: sha256:5cccf07066a0333027279aac0cae64d3f3be10773b7a5b37106302f2bbb9ceb8
  blockers: []
  signals:
    pr_ready: true
    map_revision: 1
    collision_detection: no-collision
    affected_repos:
      - drivestream-lab/realworld-api
  next_candidates:
    - prd-pr-action
  human_checkpoint: false
  external_action: true
  forge:
    action: open_draft_pr
    draft: true
    apply_labels:
      - impact-map-pending
    title: "[INIT-REALWORLD-003] PRD — Replay-ready personal search memory"
    body_path: prd/reports/Impact-Map-INIT-REALWORLD-003.md
```
