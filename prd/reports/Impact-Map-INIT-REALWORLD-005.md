---
schema_version: 1
initiative: INIT-REALWORLD-005
map_revision: 1
source_prd: prd/INIT-REALWORLD-005.md
source_prd_digest: sha256:b02fb9c6da0fbaacd490637bfef8594c963262002e9e0b86a0ca5900921773b0
previous_revision: null
previous_artifact_commit: null
change_reason: initial map
material_change: true
generated_at: 2026-11-11T08:22:24Z
---

# Impact map — INIT-REALWORLD-005 — revision 1

> This file is generated locally before PR creation and becomes the scope source
> of truth when committed. Effective approval is derived from a tech-lead
> GitHub APPROVED review on the exact current meta PR head SHA; dynamic PR state
> is not stored in this artifact's frontmatter.

## 1. Source and revision

| Field | Value |
|-------|-------|
| PRD | `prd/INIT-REALWORLD-005.md` |
| PRD digest | `sha256:b02fb9c6da0fbaacd490637bfef8594c963262002e9e0b86a0ca5900921773b0` |
| Map revision | `1` |
| Previous revision | none |
| Previous artifact commit | none |
| Change reason | Initial map after promoted think-4 PRD (C4 via Hermes promote; validation report rev 3 clean) |
| Material change | yes — first map; establishes affected repo scopes for deferred-attention / saved-for-later triage queue (API-only) |

## 2. Affected repositories

| Service | Repo | Team | Scope summary | Scope digest | Spec to create | Confidence |
|---------|------|------|---------------|--------------|----------------|------------|
| realworld-api | drivestream-lab/realworld-api | @drivestream-lab/backend-devs | Provider for CAP-01..CAP-03 and REQ-01..REQ-22: seated owner-private deferred-attention / saved-for-later triage queue (defer/list/release by durable published-article identity) with article-identity fidelity; idempotent defer/release; durable membership retention across unseat/reseat; fail-closed unseated and peer isolation; anti-harvest (no inbound who-saved); attention-only semantics (no unfinished-reading/auto-release); feature-unavailable fail-closed; favorites orthogonal coexistence; non-application to public/subscription discovery; machine-consumable API prove surface only (no cross-repo CTR this INIT). | `sha256:d9e6d828f2eb930963252fb2b902514330f540673811fb159236d992668ade2b` | `INIT-REALWORLD-005-api.md` | High |

Catalog: `config/service-catalog-drivestream-lab.yaml` (org `drivestream-lab` via `config/governance-drivestream-lab.yaml`). Catalog has no explicit `owns` / `depends_on` fields; matching uses `description` + PRD Lock 1 (product changes in `realworld-api` + `realworld-meta`) + §8 contract seeds (none) + non-goal (no web UI). This meta wave does not open per-repo spec/impl PRs; affected scopes are Gate 1 identity for later eng waves.

## 3. Deferred repositories

| Service | Repo | Reason | Revisit condition |
|---------|------|--------|-------------------|
| realworld-web | drivestream-lab/realworld-web | Settings / any web UI for triage-queue / saved-for-later stewardship is an explicit non-goal this INIT; no CTR consumer seam (PRD §8). | Later INIT that adds settings (or other) UI for deferred-attention triage-queue stewardship |
| realworld-local | drivestream-lab/realworld-local | Compose joins api+web; this INIT proves on the API machine-consumable surface and does not expand product scope to web UI. Optional local API host does not mint a product CAP. | Eng needs compose/env delta specifically for API-only live prove of CAP-01..CAP-03 |

## 4. Transitively affected repositories

| Service | Repo | Depends on | Potential impact | Disposition |
|---------|------|------------|------------------|-------------|
| realworld-web | drivestream-lab/realworld-web | drivestream-lab/realworld-api | Future UI could consume a new defer/list/release API; no product seam this INIT | deferred |
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
| IM-01 | PM | OQ-01: Exact article-identity rules for deferral target (must currently be published; soft-deleted / missing handling) | PM | no | spec-draft | Defer only resolves to a currently published article; missing identity → refuse create; no deferral created | open |
| IM-02 | PM | OQ-02: Is defer of an already-deferred article idempotent success (still one deferral), or a distinct conflict outcome? | PM | no | spec-draft | Idempotent success — queue still shows the article once (matches Lead acceptance) | open |
| IM-03 | PM | OQ-03: Exact shape for release when deferral absent (no-op success vs indistinguishable not-found vs explicit conflict) | PM | no | spec-draft | Idempotent no-op success for owner; no deferral created; no peer-queue contents disclosed | open |
| IM-04 | PM | OQ-04: May a seated member defer their own published articles? | PM | no | spec-draft | Yes — allowed (self-deferral), distinguishing from INIT-001 favorites own-article refusal | open |
| IM-05 | PM | OQ-05: Owner-visible behavior when a deferred article is later deleted by its author | PM | no | spec-draft | Non-resurrection floor locked by REQ-22; owner queue drops or marks unavailable without exposing body (eng may choose); Guest open-by-reference stays not-found | open |
| IM-06 | PM | OQ-06: Per-member maximum number of deferrals and article-identity length / normalization | PM | no | spec-draft | Eng reasonableness limits acceptable | open |
| IM-07 | PM | OQ-07: Owner triage-queue ordering rule for prove expectations | PM | no | spec-draft | Newest-deferred-first (attention recency); exact timestamp source left to eng | open |
| IM-08 | PM | OQ-08: Whether a feature flag must gate the surface in all environments, and exact unavailable semantics when off | PM | no | feasibility / later | Optional gate; when off → fail-closed unavailable (REQ-21); when enabled for prove, REQ kill paths must pass | open |
| IM-09 | PM | OQ-09: Whether opening or finishing a deferred article should auto-release the deferral this INIT | PM | no | later | No — intentional release only (REQ-19); auto-release deferred | open |
| IM-10 | PM | OQ-10: Whether favorites (INIT-001) and deferrals must stay mutually invisible in each other’s recall surfaces beyond orthogonal coexistence | PM | no | later | Yes for cross-write — surfaces remain separate; coexistence allowed (REQ-20); no merge into one shelf | open |
| IM-11 | PM | OQ-11: Whether any viewer-relative “saved for later” chrome on public article presentation is required this INIT | PM | no | later | No — queue defer/list/release is enough; public article CTA state deferred | open |
| IM-12 | PM | OQ-12: Whether unavailable (flag-off) responses must be distinguishable from unseated denial for prove | PM | no | spec-draft | Eng may distinguish; product requires both fail closed without queue disclosure | open |
| IM-13 | PM | OQ-13: Whether historical deferrals created while the feature was on remain readable after the gate turns off | PM | no | later | No — while gate is off, list/mutate unavailable (REQ-21); durability resumes when gate returns on | open |

> **Gate 1:** no Blocking=yes open rows. Spec-draft may consume IM-01..IM-13 defaults.

## 11. PR readiness handoff

| Item | Value |
|-------|-------|
| Verdict | PR READY |
| Collision detection | no-collision |
| Collision evidence | Open/closed PRs for INIT-REALWORLD-005: none (`gh pr list --search INIT-REALWORLD-005` empty). Remote heads for 005: none. Local prior Impact-Map for 005: none. Sibling INIT-REALWORLD-001 / INIT-REALWORLD-002 / INIT-REALWORLD-003 / INIT-REALWORLD-004 are different initiatives (unrelated evidence). Single promoted PRD `prd/INIT-REALWORLD-005.md`. |
| Human resolution | none |
| Resolution completed | yes — T0 was rerun after completion |
| Existing PR | none |
| Proposed branch | `chore/INIT-REALWORLD-005-prd` |
| Proposed base | `develop` |
| Proposed title | `[INIT-REALWORLD-005] PRD — Deferred-attention / saved-for-later triage queue` |
| Files to commit | `prd/INIT-REALWORLD-005.md`, `prd/reports/Impact-Map-INIT-REALWORLD-005.md`, `prd/reports/Validation-Report-INIT-REALWORLD-005.md`, `prd/reports/Resolution-INIT-REALWORLD-005.md` (and companion think/quality/promote reports under `prd/reports/` as approved) |
| Reviewer | @drivestream-lab/platform-devs |
| Initial Gate 1 label | `impact-map-pending` |
| Additional invalidation label | none |
| Blocking items | none |

**No GitHub side effects have occurred.** Publish via `/open-draft-pr` (or orchestrator ForgeClient on `prd-pr-action`) after explicit authorization.

### Proposed Draft PR body

```markdown
## Product change
Signed-in readers need a durable, owner-private deferred-attention / saved-for-later triage queue: defer, inspect, and release by published-article identity — with idempotent toggle, fail-closed isolation from guests/post-logout/peers, attention-only semantics (no unfinished-reading or auto-release), feature-unavailable fail-closed, favorites orthogonal coexistence, and no feed personalization or web UI this INIT. This meta wave lands the product write-up and Impact-Map only — implementation ownership is `realworld-api`; no per-repo spec/impl PRs in this wave.

## Impact-map summary
- Revision: 1
- PRD digest: `sha256:b02fb9c6da0fbaacd490637bfef8594c963262002e9e0b86a0ca5900921773b0`
- Affected repos: drivestream-lab/realworld-api
- Deferred repos: drivestream-lab/realworld-web, drivestream-lab/realworld-local
- Blocking questions: none
- Artifact: `prd/reports/Impact-Map-INIT-REALWORLD-005.md`

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
initiative: INIT-REALWORLD-005
map_revision: 1
meta_pr_head_sha: {SHA after this artifact is committed}
prd_digest: sha256:b02fb9c6da0fbaacd490637bfef8594c963262002e9e0b86a0ca5900921773b0
artifact: prd/reports/Impact-Map-INIT-REALWORLD-005.md
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
    path: prd/reports/Impact-Map-INIT-REALWORLD-005.md
    digest: sha256:b02fb9c6da0fbaacd490637bfef8594c963262002e9e0b86a0ca5900921773b0
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
    title: "[INIT-REALWORLD-005] PRD — Deferred-attention / saved-for-later triage queue"
    body_path: prd/reports/Impact-Map-INIT-REALWORLD-005.md
```
