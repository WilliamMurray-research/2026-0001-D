## UPTF Road‑Map (v0.0.4)

> **Goal** – Keep the scaffold *intact* while filling in every required file, wiring the build & test pipelines, and publishing immutable snapshots.

| Phase | Duration | Key Deliverables | Dependencies | Risks / Mitigations |
|-------|----------|------------------|--------------|---------------------|
| **1. Foundation** | 2 weeks | • Scaffold verified (all folders + `.gitkeep`) <br>• README, LICENSE, NOTICE, CODEOWNERS, CONTRIBUTING.md ready <br>• `.gitignore` & pre‑commit hook installed | – None yet – just scaffold | – Mistaken deletion of folder → *Add it back* with `.gitkeep`. |
| **2. Core Architecture** | 4 weeks | • `architecture/system/context.md`, …, `interfaces/rendering.md` <br>• Data models in `architecture/data/`<br>• C4 diagrams (context‑containers‑components) <br>• Draft `roadmap/evolution.md` & `versioning.md` | **Foundation** – scaffold must exist | – Incomplete spec → *Use templates*; keep a draft. |
| **3. Governance & Roles** | 2 weeks | • `governance/motivation.md`, `roles.md`, `constraints.md` <br>• `CODEOWNERS` mapping to teams <br>• Review workflow in `CONTRIBUTING.md` | **Foundation**, **Core Architecture** | – Conflicting constraints → *Escalate* to Project Owner. |
| **4. Source Implementation (src/)** | 6 weeks | • Application entry point (`main`) <br>• Frontend/Backend modules under `src/`<br>• Shared utilities <br>• Telemetry ingestion, DSL parsing, rendering engine | **Core Architecture** | – Runtime errors → *Unit & integration tests* in `tests/`. |
| **5. Build & Test Pipelines** | 3 weeks | • `scripts/build/` (build.sh) <br>• `scripts/validate/` (lint + test runner)<br>• CI config (`.github/workflows`) <br>• Pre‑commit hook enforcing `.gitignore` | **Source Implementation** | – Build failures → *Add debug logs*; keep scripts idempotent. |
| **6. Validation & Governance Compliance** | 2 weeks | • Validate that all required docs are present <br>• Run `scripts/validate/generate_ledger.sh` to update `build_plan.md` <br>• Append first changelog entry in `logs/CHANGELOG.md` | **Build Pipelines** | – Missing ledger entries → *Manual audit*; maintain double‑entry YAML. |
| **7. Release & Snapshotting** | 1 week | • Tag release (`v0.0.4`) <br>• Archive `versions/v0.0.4_YYYY-MM-DD/` (tar.gz + manifest.md) <br>• Update `NOTICE` for new version | **Validation** | – Snapshot corrupt → *Re‑archive*; keep checksum in `manifest.md`. |
| **8. Continuous Governance** | Ongoing | • Review `constraints.md` quarterly <br>• Add new role if needed (e.g., “Compliance Officer”) <br>• Update `roadmap/evolution.md` with upcoming changes | All previous phases | – Unapproved change → *Project Owner approval*; enforce via CODEOWNERS. |

---

## 📌  Milestone Table (quick reference)

| # | Milestone | Due Date | Owner |
|---|------------|-----------|-------|
| 1 | Scaffold verified | Day 7 | Lead Architect |
| 2 | Core architecture docs complete | Day 21 | Research Lead |
| 3 | Governance docs complete | Day 35 | Project Owner |
| 4 | Frontend code (v0.0.4) | Day 70 | Maintainer |
| 5 | Build scripts & CI ready | Day 84 | DevOps |
| 6 | First changelog entry | Day 98 | Lead Architect |
| 7 | Release v0.0.4 snapshot | Day 105 | Project Owner |

---

## 🔧  Dependencies

1. **Foundation** must finish before any other phase – no missing folders or hooks.
2. **Core Architecture** relies on the scaffold; you cannot write `system/context.md` until `architecture/` exists.
3. **Source Implementation** needs the interface specs (`interfaces/api.md`, `dsl.md`) to be drafted first.
4. **Build Pipelines** depend on a working `src/main` entry point and unit tests.

---

## ⚠️  Risks & Mitigation Cheat‑sheet

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|-------------|
| Deleting a mandatory folder | Medium | High | Keep `.gitkeep`; run `scripts/validate/check_scaffold.sh` before every PR. |
| Not updating ledger (`build_plan.md`) | Low | Medium | Prolog engine auto‑updates; human review after each generation cycle. |
| Snapshot corrupted | Low | High | Use checksum in `versions/README.md`; re‑archive if mismatch. |
| Governance breach (e.g., adding new top‑level folder) | Very low | High | Code review + CODEOWNERS enforces; pre‑commit hook blocks. |

---

## 📚  Quick Checklist – “What to Do Next”

1. **Add `.gitkeep`** to every empty directory (`risk/`, `security/`, etc.).  
2. **Create the first architecture file** – start with `architecture/system/context.md`.  
3. **Write a minimal `src/main`** (language‑agnostic placeholder).  
4. **Run `scripts/validate/scaffold_check.sh`** to verify all required files exist.  
5. **Commit** and push – your CI should now pass the scaffolding check.

---

## 🚀  Next Steps for You

- Copy this roadmap into `docs/roadmap.md`.  
- Assign owners (you or teammates) per milestone.  
- Set a project timeline in your issue tracker, e.g., GitHub Projects or Jira.  
- Treat each phase as a *mini‑sprint* – keep it short and focused.

With that plan in place you’ll be able to **progress systematically** while staying fully compliant with the UPTF invariants. 
