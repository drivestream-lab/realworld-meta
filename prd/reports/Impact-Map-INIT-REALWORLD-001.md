---
schema_version: 1
initiative: INIT-REALWORLD-001
map_revision: 1
source_prd: prd/INIT-REALWORLD-001.md
source_prd_digest: sha256:4552dc6384ee851456014fc9738186bf1a068dc3c23246b0de693e1d8e1de926
previous_revision: null
previous_artifact_commit: null
change_reason: initial map
material_change: true
generated_at: 2026-11-04T17:53:41Z
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
| PRD digest | `sha256:4552dc6384ee851456014fc9738186bf1a068dc3c23246b0de693e1d8e1de926` |
| Map revision | `1` |
| Previous revision | none |
| Previous artifact commit | none |
| Change reason | Initial map after validated/promoted PRD (C3) |
| Material change | yes — first map; establishes affected scopes for api + web |

**Catalog resolved:** `config/service-catalog-drivestream-lab.yaml` (org `drivestream-lab` from unique `governance-drivestream-lab.yaml`). Catalog has no `owns` / `depends_on` fields; matching used service `description` + PRD §8 contract seeds + stack roles.

## 2. Affected repositories

| Service | Repo | Team | Scope summary | Scope digest | Spec to create | Confidence |
|---------|------|------|---------------|--------------|----------------|------------|
| realworld-api | drivestream-lab/realworld-api | @drivestream-lab/backend-devs | Provide durable public catalog: Empty/occupied list, identity-gated publish accept/refuse, attributed public read; bind CTR-01/02/03 for home list, article read, and publish | `sha256:5abd532727c56b91cbb26af89d8e91445c23247ac4714e971caf189701a96612` | `INIT-REALWORLD-001-api.md` | High |
| realworld-web | drivestream-lab/realworld-web | @drivestream-lab/frontend-devs | Consume catalog contracts on home list, public read, registration, and publish UI; anonymous later-visitor discover/read; refuse UX without advancing catalog falsely | `sha256:9f68549d9a3acd063a71a9fa283d28fad67f2896d224bfcaac0f2633833d8f34` | `INIT-REALWORLD-001-web.md` | High |

**Capability → service match (semantic):**

| CAP / contracts | realworld-api | realworld-web |
|-----------------|---------------|---------------|
| CAP-01 catalog states on home | List published articles; Empty list truthful; Multi coexistence (CTR-01) | Home listing UI; Empty / occupied presentation |
| CAP-02 publish advances catalog | Identity + substance accept/refuse; durable entry (CTR-03); registration/auth | Registration + editor publish UI; surface non-success on refuse |
| CAP-03 list↔read fidelity | Retrieve published article matching list (CTR-02); no ghost listings | Open-from-home read; anonymous visitor path |
| CAP-04 attribution binding | Persist and return bound author identity on list + read | Show same attribution on list and read |

## 3. Deferred repositories

| Service | Repo | Reason | Revisit condition |
|---------|------|--------|-------------------|
| realworld-local | drivestream-lab/realworld-local | Compose wiring for api+web on `adh_local` / DB `realworld` — no product CAP/REQ owned here; not required to change for catalog semantics | Revisit if local prove cannot run Empty → publish → home discover → read against the shared stack, or if compose env/ports must change for CTR-01/02/03 |

## 4. Transitively affected repositories

| Service | Repo | Depends on | Potential impact | Disposition |
|---------|------|------------|------------------|-------------|
| realworld-local | drivestream-lab/realworld-local | realworld-api, realworld-web (inferred from catalog description: “api+web compose”; catalog has no explicit `depends_on`) | May need env/health updates if api/web contract surfaces change for local prove | monitor (deferred product scope) |

## 5. Not affected

| Service | Repo | Reason |
|---------|------|--------|
| realworld-meta | drivestream-lab/realworld-meta | Meta control-plane hosts PRD/impact artifacts only; does not implement catalog, publish, or public read product capabilities |

## 6. Cross-repository contracts

| Contract ID | Provider repo | Consumer repo | Capability | Owner | Status |
|-------------|---------------|---------------|------------|-------|--------|
| CTR-01 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-01 — list published articles for home catalog state | @drivestream-lab/backend-devs (provider) | new |
| CTR-02 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-03 / CAP-04 — retrieve one published article for public read | @drivestream-lab/backend-devs (provider) | new |
| CTR-03 | drivestream-lab/realworld-api | drivestream-lab/realworld-web | CAP-02 / CAP-04 — accept or refuse publish under author identity | @drivestream-lab/backend-devs (provider) | new |

## 7. Dependency and build order

```text
drivestream-lab/realworld-api → drivestream-lab/realworld-web
```

| Repo | Depends on | Reason |
|------|------------|--------|
| drivestream-lab/realworld-api | none | Provider of CTR-01/02/03; no catalog `depends_on` |
| drivestream-lab/realworld-web | drivestream-lab/realworld-api | Consumer of CTR-01/02/03; home/read/publish UI cannot prove without provider |

## 8. Revision diff

Omit — revision 1 (no prior map).

## 9. Downstream ripple ledger

No prior revision — no in-flight app artifacts. Initial open actions after Gate 1 approval:

| Repo | In-flight artifact | Required action | Reason | Owner | Blocking |
|------|--------------------|-----------------|--------|-------|----------|
| drivestream-lab/realworld-api | none | open | Added in revision 1 | @drivestream-lab/backend-devs | no |
| drivestream-lab/realworld-web | none | open | Added in revision 1 | @drivestream-lab/frontend-devs | no |
| drivestream-lab/realworld-local | none | hold | Deferred / monitor only | @drivestream-lab/platform-devs | no |

## 10. Open questions

| ID | Lane | Question | Owner | Blocking | Required by | Default if deferred | Status |
|----|------|----------|-------|----------|-------------|---------------------|--------|
| — | — | None at Gate 1. PRD OQ-01..OQ-05 remain non-blocking product defaults in `prd/INIT-REALWORLD-001.md`. VF-05 (PRD Dependencies section) deferred via CHG-05; ownership is locked here by affected-repo rows. | — | no | — | — | resolved for Gate 1 |

> **Gate 1:** any row with `Blocking: yes` and `Status: open` **closes**
> coding-readiness / Gate 1 until resolved or deferred with default.
> No blocking IM rows — Gate 1 may open after matching tech-lead APPROVED on current head.

## 11. PR readiness handoff

| Item | Value |
|------|-------|
| Verdict | PR READY |
| Collision detection | no-collision |
| Collision evidence | Local: no prior `Impact-Map-INIT-REALWORLD-001.md`; branch `develop`; untracked `prd/INIT-REALWORLD-001.md` + `prd/reports/*` for this INIT only. `gh pr list`: no open/closed PRs matching INIT-REALWORLD-001 / REALWORLD impact. No competing INIT branches. |
| Human resolution | none |
| Resolution completed | n/a — T0 `no-collision` |
| Existing PR | none |
| Proposed branch | `chore/INIT-REALWORLD-001-prd` |
| Proposed base | `develop` |
| Proposed title | `[INIT-REALWORLD-001] PRD — Public catalog states + list↔read fidelity` |
| Files to commit | `prd/INIT-REALWORLD-001.md`, `prd/reports/Impact-Map-INIT-REALWORLD-001.md`, `prd/reports/Validation-Report-INIT-REALWORLD-001.md`, `prd/reports/Resolution-INIT-REALWORLD-001.md`, related think/quality/hermes reports under `prd/reports/` as approved lineage |
| Reviewer | @drivestream-lab/platform-devs |
| Initial Gate 1 label | `impact-map-pending` |
| Additional invalidation label | none |
| Blocking items | none |

**No GitHub side effects have occurred.** Publish via `/open-draft-pr` (or ForgeClient on `prd-pr-action`) after authorization.

### Proposed Draft PR body

```markdown
## Product change
INIT-REALWORLD-001 proves the public writing↔reading loop: Empty home catalog, identity-gated publish that advances catalog state, home discoverability for a later (anonymous) visitor, list↔read substance fidelity, bound author attribution, and Multi occupancy when a second distinct author publishes. Non-goals include comments, tags/feeds, edit/delete, drafts, and same-author multi-publish prove.

## Impact-map summary
- Revision: 1
- PRD digest: `sha256:4552dc6384ee851456014fc9738186bf1a068dc3c23246b0de693e1d8e1de926`
- Affected repos: drivestream-lab/realworld-api, drivestream-lab/realworld-web
- Deferred repos: drivestream-lab/realworld-local (compose monitor)
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
prd_digest: sha256:4552dc6384ee851456014fc9738186bf1a068dc3c23246b0de693e1d8e1de926
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
    digest: sha256:4552dc6384ee851456014fc9738186bf1a068dc3c23246b0de693e1d8e1de926
  blockers: []
  signals:
    pr_ready: true
    map_revision: 1
    source_prd_digest: sha256:4552dc6384ee851456014fc9738186bf1a068dc3c23246b0de693e1d8e1de926
    affected_repos:
      - drivestream-lab/realworld-api
      - drivestream-lab/realworld-web
    deferred_repos:
      - drivestream-lab/realworld-local
    collision_detection: no-collision
  next_candidates:
    - prd-pr-action
  human_checkpoint: false
  external_action: true
  forge:
    action: open_draft_pr
    draft: true
    apply_labels:
      - impact-map-pending
    title: "[INIT-REALWORLD-001] PRD — Public catalog states + list↔read fidelity"
    body_path: prd/reports/Impact-Map-INIT-REALWORLD-001.md
```
