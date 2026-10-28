# realworld-meta

Control-plane for the **RealWorld** proof tenant in `drivestream-lab`.

Forked OSS (gothinkster RealWorld contract, MIT). Overlay harness only — no cookiecutter replace.

| File | Purpose |
| --- | --- |
| `config/programme.yaml` | Identity: slug `realworld`, org `drivestream-lab` |
| `config/governance-drivestream-lab.yaml` | Teams, repos, gitflow, board **RealWorld** |
| `config/harness-drivestream-lab.yaml` | Skills per stack; web has no Next.js constitution |
| `config/scaffold-drivestream-lab.yaml` | All scaffolds **off** |
| `config/service-catalog-drivestream-lab.yaml` | Service map |
| `config/upstream.yaml` | Pinned FastAPI + React SHAs |

Factory secrets live in `~/.config/launchpad/env.d/realworld.env` — never commit them.

GitHub Apps: `adh-dev-backend` and `adh-reviewer` are installed on **all** org repos, so they already cover these forks. `adh-dev-frontend` still needs an org install (the App JWT has zero installations). Install URL: https://github.com/apps/adh-dev-frontend/installations/new

```bash
launchpad --client realworld doctor
launchpad --client realworld status --meta
```
