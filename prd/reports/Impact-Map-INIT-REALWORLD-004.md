---
schema_version: 1
initiative: INIT-REALWORLD-004
map_revision: 1
source_prd: prd/INIT-REALWORLD-004.md
source_prd_digest: sha256:93c847c6e063476413c9ca37e8f76ae2d709a425d9d908b57666a0797b037ff3
previous_revision: null
previous_artifact_commit: null
change_reason: initial map
material_change: true
generated_at: 2026-11-10T11:50:06Z
---

# Impact map — INIT-REALWORLD-004 — revision 1

> This file is generated locally before PR creation and becomes the scope source
> of truth when committed. Effective approval is derived from a tech-lead
> GitHub APPROVED review on the exact current meta PR head SHA; dynamic PR state
> is not stored in this artifact's frontmatter.

## 1. Source and revision

| Field | Value |
|-------|-------|
| PRD | `prd/INIT-REALWORLD-004.md` |
| PRD digest | `sha256:93c847c6e063476413c9ca37e8f76ae2d709a425d9d908b57666a0797b037ff3` |
| Map revision | `1` |
| Previous revision | none |
| Previous artifact commit | none |
| Change reason | Initial map after promoted think-4 PRD (C4 via Hermes promote; validation report rev 3 clean) |
| Material change | yes — first map; establishes affected repo scopes for private membership→tag follow edges (API-only) |

## 2. Affected repositories

| Service | Repo | Team | Scope summary | Scope digest | Spec to create | Confidence |
|---------|------|------|---------------|--------------|----------------|------------|
| realworld-api | drivestream-lab/realworld-api | @drivestream-lab/backend-devs | Provider for CAP-01..CAP-03 and REQ-01..REQ-18: seated owner-private membership→tag follow edges (establish/list/dissolve by tag name) with name fidelity on own outgoing list; refuse empty/whitespace tag names; durable membership retention across unseat/reseat; fail-closed unseated and peer isolation; anti-reciprocity (no inbound followers-of-tag); non-composition with INIT-002 author-follow/subscription-stream; machine-consumable API prove surface only (no cross-repo CTR this INIT). | `sha256:383c6d9230804e3cfe4007373df6cf732d6a9415eb5725e1a7c13bfb3e78b0f5` | `INIT-REALWORLD-004-api.md` | High |

Catalog: `config/service-catalog-drivestream-lab.yaml` (org `drivestream-lab` via `config/governance-drivestream-lab.yaml`). Catalog has no explicit `owns` / `depends_on` fields; matching uses `description` + PRD Lock 1 (product changes in `realworld-api` + `realworld-meta`) + §8 contract seeds (none) + non-goal (no web UI). This meta wave does not open per-repo spec/impl PRs; affected scopes are Gate 1 identity for later eng waves.

## 3. Deferred repositories

| Service | Repo | Reason | Revisit condition |
|---------|------|--------|-------------------|
| realworld-web | drivestream-lab/realworld-web | Settings / any web UI for tag-follow edge stewardship is an explicit non-goal this INIT; no CTR consumer seam (PRD §8). | Later INIT that adds settings (or other) UI for membership→tag follow-edge stewardship |
| realworld-local | drivestream-lab/realworld-local | Compose joins api+web; this INIT proves on the API machine-consumable surface and does not expand product scope to web UI. Optional local API host does not mint a product CAP. | Eng needs compose/env delta specifically for API-only live prove of CAP-01..CAP-03 |

## 4. Transitively affected repositories

| Service | Repo | Depends on | Potential impact | Disposition |
|---------|------|------------|------------------|-------------|
| realworld-web | drivestream-lab/realworld-web | drivestream-lab/realworld-api | Future UI could consume a new tag-follows API; no product seam this INIT | deferred |
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
| IM-01 | PM | OQ-01: May a seated member establish an edge to a tag name whose public lane currently has zero articles, or must the tag already exist in the corpus? | PM | no | spec-draft | Allow edge to any non-empty normalized tag name even if no article currently carries it | open |
| IM-02 | PM | OQ-02: Is follow of an already-edged tag name idempotent success (still one outgoing edge), or a distinct conflict outcome? | PM | no | spec-draft | Idempotent success — outgoing list still shows the tag once | open |
| IM-03 | PM | OQ-03: Exact fail-closed shape for unfollow when not following vs non-owned / missing identity | PM | no | spec-draft | Indistinguishable not-found to the requester; no outgoing-edge contents disclosed | open |
| IM-04 | PM | OQ-04: Per-member maximum number of outgoing tag-follow edges and max tag-name length | PM | no | spec-draft | Eng reasonableness limits acceptable | open |
| IM-05 | PM | OQ-05: Owner outgoing-list ordering rule for prove expectations | PM | no | spec-draft | Newest-established-first; exact timestamp source left to eng | open |
| IM-06 | PM | OQ-06: Tag-name normalization (case folding, whitespace trim, unicode) for identity equality of establish/dissolve/list | PM | no | spec-draft | Trim outer whitespace; case-sensitive match as stored after trim (eng may document storage form) | open |
| IM-07 | PM | OQ-07: Whether establishing a tag-follow edge must appear as viewer-relative “following” state on public tag surfaces this INIT | PM | no | later | No — list/establish/dissolve on the private outgoing-edge surface is enough; public tag CTA state deferred | open |
| IM-08 | PM | OQ-08: Whether dissolving an edge leaves any owner-visible history of former tag follows | PM | no | later | Fully removed from owner outgoing list — no history surface this INIT | open |
| IM-09 | PM | OQ-09: Whether favorites (INIT-001) and tag-follow edges must stay mutually invisible in each other’s recall surfaces beyond the already-locked non-reopen | PM | no | later | Yes — favorites shelf and tag-follow outgoing list remain separate; no cross-write this INIT | open |
| IM-10 | PM | OQ-10: Whether any future programme may reverse-index tag-follow edges without a new INIT | PM | no | later | No — inbound follower disclosure requires a later INIT; this INIT’s anti-reciprocity stands | open |

> **Gate 1:** no Blocking=yes open rows. Spec-draft may consume IM-01..IM-10 defaults.

## 11. PR readiness handoff

| Item | Value |
|------|-------|
| Verdict | PR READY |
| Collision detection | no-collision |
| Collision evidence | Open/closed PRs for INIT-REALWORLD-004: none (`gh pr list --search INIT-REALWORLD-004` empty). Remote heads for 004: none. Local prior Impact-Map for 004: none. Sibling INIT-REALWORLD-001 / INIT-REALWORLD-002 / INIT-REALWORLD-003 are different initiatives (unrelated evidence). Single promoted PRD `prd/INIT-REALWORLD-004.md`. |
| Human resolution | none |
| Resolution completed | yes — T0 was rerun after completion |
| Existing PR | none |
| Proposed branch | `chore/INIT-REALWORLD-004-prd` |
| Proposed base | `develop` |
| Proposed title | `[INIT-REALWORLD-004] PRD — Private membership→tag follow edges` |
| Files to commit | `prd/INIT-REALWORLD-004.md`, `prd/reports/Impact-Map-INIT-REALWORLD-004.md`, `prd/reports/Validation-Report-INIT-REALWORLD-004.md`, `prd/reports/Resolution-INIT-REALWORLD-004.md` (and companion think/quality/promote reports under `prd/reports/` as approved) |
| Reviewer | @drivestream-lab/platform-devs |
| Initial Gate 1 label | `impact-map-pending` |
| Additional invalidation label | none |
| Blocking items | none |

**No GitHub side effects have occurred.** Publish via `/open-draft-pr` (or orchestrator ForgeClient on `prd-pr-action`) after explicit authorization.

### Proposed Draft PR body

```markdown
## Product change
Signed-in readers need durable, owner-private outgoing membership→tag follow edges: establish, inspect, and dissolve by tag name — with fail-closed isolation from guests, post-logout actors, and peers; anti-reciprocity (no inbound followers-of-tag); non-composition with INIT-002 author-follow; and no feed personalization or web UI this INIT. This meta wave lands the product write-up and Impact-Map only — implementation ownership is `realworld-api`; no per-repo spec/impl PRs in this wave.

## Impact-map summary
- Revision: 1
- PRD digest: `sha256:93c847c6e063476413c9ca37e8f76ae2d709a425d9d908b57666a0797b037ff3`
- Affected repos: drivestream-lab/realworld-api
- Deferred repos: drivestream-lab/realworld-web, drivestream-lab/realworld-local
- Blocking questions: none
- Artifact: `prd/reports/Impact-Map-INIT-REALWORLD-004.md`

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
initiative: INIT-REALWORLD-004
map_revision: 1
meta_pr_head_sha: {SHA after this artifact is committed}
prd_digest: sha256:93c847c6e063476413c9ca37e8f76ae2d709a425d9d908b57666a0797b037ff3
artifact: prd/reports/Impact-Map-INIT-REALWORLD-004.md
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
    path: prd/reports/Impact-Map-INIT-REALWORLD-004.md
    digest: sha256:93c847c6e063476413c9ca37e8f76ae2d709a425d9d908b57666a0797b037ff3
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
    title: "[INIT-REALWORLD-004] PRD — Private membership→tag follow edges"
    body_path: prd/reports/Impact-Map-INIT-REALWORLD-004.md
```
