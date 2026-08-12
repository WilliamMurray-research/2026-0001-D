## Walk Through 



---

## 1️⃣  Top‑Level Directory Overview  

| Folder | What it holds (high‑level) | Why it matters |
|--------|-----------------------------|-----------------|
| **`docs/`** | Narrative/spec docs – research papers, governance rationale, ops specs, etc. | The *public* knowledge base; keeps “why we do this” in one place. |
| **`architecture/`** | Formal system diagrams & data models (C4, schemas, interfaces). | The *blueprint* that all code must follow – it lives here so you can version‑control the spec itself. |
| **`risk/`** | Proprietary risk registers / taxonomy (kept in .gitkeep so the folder stays). | Confidential – only exposed in releases; governance controls how it’s updated. |
| **`security/`** | Proprietary threat models, policies, controls. | Same as `risk/`; must never be public. |
| **`src/`** | Your source code – split by target (frontend/backend/shared). | The “work‑horse”; every new module is added under an existing branch here. |
| **`scripts/`** | Build / release / validate scripts. | Tooling that lives in the repo, not external CI. |
| **`tests/`** | Unit & integration test suites (no tests inside `src/`). | Keeps test artefacts separate from production code. |
| **`assets/`** | Static media, schemas, static resources. | Anything that doesn’t change at runtime but is part of the repo’s surface. |
| **`versions/`** | Immutable project snapshots (`v{MAJOR}.{MINOR}.{PATCH}_{YYYY-MM-DD}/`). | The canonical archive you can replay any release from. |
| **`logs/`** | Append‑only operational / audit logs (CHANGELOG.md, critique_history.log). | Audit trail – never rewrite. |
| **`.gitignore`** | Exclusion rules (including the special rules to keep risk/security structure). | Prevent accidental leakage of proprietary content. |
| **`CONTRIBUTING.md`** | On‑boarding guidance for contributors. | Keeps everyone on the same page. |
| **`CODEOWNERS`** | GitHub CODEOWNERS file. | Automates review routing. |
| **`NOTICE`** | Licence boundary declaration (MIT + proprietary notice). | Legal requirement. |
| **`README.md`** | Public repo intro (project title, template origin). | The first thing visitors see. |
| **`LICENSE`** | MIT licence file for all non‑proprietary content. | Open‑source license. |

> **Key point:** *All directories that appear in the tree are mandatory.  You must never delete or rename them – only add new sub‑directories under existing branches.*  

---

## 2️⃣  Detailed Sub‑folder Contents (within `docs/` and `architecture/`)  

### A. `docs/`

```
docs/
├── research/
│   ├── whitepapers/
│   ├── hypotheses/
│   ├── proofs/
│   └── algorithms/
├── governance/
│   ├── motivation.md
│   ├── roles.md
│   └── constraints.md
└── operations/
    ├── procurement/
    │   ├── CCE-finance.ods
    │   └── CCE-procurement.odt
    ├── compute/
    │   ├── CCE-compute.ods
    │   └── CCE-log.odt
    └── records/  (same ODS/ODT files)
```

| Subfolder | Purpose | Notes |
|-----------|---------|-------|
| **`research/`** | Research artefacts – whitepapers, hypotheses, proofs, algorithm docs. | Only *public* research lives here. |
| **`governance/`** | Governance docs: motivation (why the project exists), roles (who does what), constraints (rules that must be obeyed). | These are the *policy* of the repo; they live under `docs`. |
| **`operations/`** | Operational specs: procurement, compute, and operational records. | Real‑world data that is kept in ODS / ODTS for auditability. |

> **Tip:**  Keep any **proprietary logs** (risk/security) out of these public folders; only the minimal `.gitkeep` & README remain.

### B. `architecture/`

```
architecture/
├── system/
│   ├── context.md
│   ├── containers.md
│   ├── components.md
│   └── code.md (optional)
├── data/
│   ├── models.md
│   ├── flows.md
│   └── storage.md
├── interfaces/
│   ├── api.md
│   ├── dsl.md
│   └── rendering.md
└── roadmap/
    ├── evolution.md
    └── versioning.md
```

| Subfolder | Purpose | Notes |
|-----------|---------|-------|
| **`system/`** | C4 system diagram docs – context, containers, components. | Keep the *formal* layout of your architecture. |
| **`data/`** | Data models (schemas), pipelines, persistence rules. | Keeps data‑centric invariants separate from code. |
| **`interfaces/`** | Interface specs: API surface, DSL definitions, rendering rules. | Keeps external surfaces in one place. |
| **`roadmap/`** | Evolution & versioning docs – what changes will happen next. | Aligns with the `versions/` folder. |

> **Governance note:**  All of these files are *immutable*.  When you add a new component, create a new file under an existing branch (e.g., add `architecture/data/migration.md`) – never rename or delete.

---

## 3️⃣  Governance & Operational “Why” Sections  

| Folder | What it explains |
|--------|--------------------|
| **`docs/governance/`** | The *rules* that govern the project.  Includes motivation, roles, constraints, and versioning. |
| **`docs/operations/`** | How the system is run day‑to‑day: procurement, compute records, operational logs. |

> These folders are separate because they *control* how other parts of the repo behave; you keep them at the top level so the rest of the code can simply “consume” these rules.

---

## 4️⃣  Extension Policy (How to Add New Content)

1. **Add new directories under an existing branch** – e.g., `src/` → add `src/services/`, `tests/integration/fixtures/`.  
2. **Do not rename or delete any of the top‑level folders** listed above.  
3. **Use `.gitkeep` for empty subfolders** – this keeps them in Git and signals intentional emptiness.  
4. **Never commit proprietary risk/security content into public branches** – only `.gitkeep`, `README.md` (and `.gitignore` rules to block the rest).  
5. **Append‑only logs** – `CHANGELOG.md` and `critique_history.log` must never be edited or rewritten.  

---

## 5️⃣  Quick Checklist for “Getting Started”

1. **Fill out the root README** – give your project a title, a short description, and note that you’re using UPTF v0.0.4.  
2. **Add `.gitkeep` to every empty folder** (`risk/.gitkeep`, `security/.gitkeep`, etc.).  
3. **Write the governance docs** (`motivation.md`, `roles.md`, `constraints.md`).  These are your project’s *policy*.  
4. **Create the first architecture files** – start with `architecture/system/context.md` and work down to interfaces/roadmap.  
5. **Add a minimal source module** in `src/main` (or whatever entry point is appropriate).  Keep it under its own subfolder (`frontend`, `backend`, or `shared`).  
6. **Write the first test** in `tests/unit`.  Do not place tests inside `src/`.  
7. **Create a simple build script** in `scripts/build/make.sh` that compiles your code and copies files into `versions/`.  
8. **Add the pre‑commit hook** from `scripts/validate/pre-commit.sample` (rename to `.git/hooks/pre-commit`).  This ensures you don’t accidentally commit risk/security changes.  

---

## 6️⃣  Common Gotchas

| Scenario | What to Watch For |
|----------|--------------------|
| **Accidentally deleting a folder** – e.g., `src/telemetry/` | The scaffold will break; re‑add it with `.gitkeep`. |
| **Moving risk/security files outside the folder** | They’ll be lost from version control and violate governance. |
| **Editing an existing log file** (e.g., `CHANGELOG.md`) | Disallowed – always append new entries only. |
| **Renaming a top‑level directory** (e.g., `docs` → `documentation`) | Violates the template; revert to original name. |
| **Adding a new subfolder inside `risk/` but not tracking it** | Keep `.gitkeep` so Git sees it. |

---

## 7️⃣  Summary Cheat Sheet

| File / Folder | Purpose | Key Rule |
|---------------|---------|-----------|
| `README.md` | Public repo intro | Must exist; never delete. |
| `LICENSE` | MIT licence for non‑proprietary parts | Include in all releases. |
| `.gitignore` | Keeps risk/security content private | Use the rules shown in the README. |
| `docs/` | All governance / research docs | Keep separate from code. |
| `architecture/` | Formal system specs | Never rename; only add new files under branches. |
| `src/` | Code, split by target | Only add subfolders, never delete `src`. |
| `scripts/` | Build / validate tooling | Use `build`, `release`, `validate`, etc. |
| `tests/` | Test suites | No tests inside `src/`. |
| `assets/` | Static media | Keep them in the repo. |
| `versions/` | Immutable snapshots | Create at every tag; never edit. |
| `logs/CHANGELOG.md` | Append‑only changelog | Never rewrite past entries. |
| `.gitkeep` | Tracks empty folders | Add to all empty dirs. |

---

## 8️⃣  Final Words

- **Keep the tree as shown** – it’s your governance model.  
- **Treat every folder name as a *contract*** – don’t change it unless you update the README and document the change.  
- **Add new content only under existing branches** – this is the single allowed extension rule.  
- **Use the provided scripts and hooks** to keep everything compliant automatically.  

With this guide, you can confidently navigate the UPTF scaffold and know exactly where each piece belongs. If you need a deeper dive into any specific file (e.g., how to write `roles.md` or craft an architecture diagram), just let me know!
