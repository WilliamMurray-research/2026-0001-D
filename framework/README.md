# README.md — Universal Project Template Framework (v0.0.3)

---

## 1. Project Identity

**Project Title:**
*(Insert project name here)*

**Template Origin:**
This project is instantiated from the **Universal Project Template Framework (v0.0.3)**.
The framework defines mandatory structural, operational, and governance invariants.
All projects inheriting this scaffold must preserve its canonical structure in full.

---

## 2. Governance Statement

This repository is governed by the structural and procedural standards defined in the canonical template framework. The directory schema, required files, and operational conventions constitute part of the project's governance model and **must not be altered** except where explicitly permitted.

Structural emptiness is meaningful. Null directories represent unpopulated operational domains and must be retained in version control using explicit tracking placeholders (`.gitkeep`).

This template is designed to serve as a **canonical reference for automated instantiation**. Build tooling should treat this structure as the authoritative source and derive project scaffolds from it directly, rather than maintaining independent copies.

---

## 3. Canonical Directory Structure

The following structure is normative and must be preserved exactly:

```
/
├── docs/                                 # Conceptual & narrative specifications
│   ├── research/
│   │   ├── whitepapers/
│   │   ├── hypotheses/
│   │   ├── proofs/
│   │   └── algorithms/
│   ├── governance/
│   │   ├── motivation.md
│   │   ├── roles.md
│   │   └── constraints.md
│   └── operations/
│       ├── procurement/
│       ├── compute/
│       └── records/
│
├── architecture/                         # Formal technical layout & system designs
│   ├── system/                           # C4 Model layout
│   │   ├── context.md                    # C4 Level 1
│   │   ├── containers.md                 # C4 Level 2
│   │   ├── components.md                 # C4 Level 3
│   │   └── code.md                       # C4 Level 4 (optional)
│   ├── data/
│   │   ├── models.md                     # Schemas, invariants
│   │   ├── flows.md                      # Pipelines, telemetry paths
│   │   └── storage.md                    # Persistence, immutability rules
│   ├── interfaces/
│   │   ├── api.md                        # External surface
│   │   ├── dsl.md                        # DSL specifications
│   │   └── rendering.md                  # Deterministic rendering rules
│   └── roadmap/
│       ├── evolution.md
│       └── versioning.md
│
├── risk/                                 # [PROPRIETARY] Internal risk management
│   ├── .gitkeep
│   ├── README.md
│   ├── register.md
│   ├── taxonomy.md
│   ├── assessment/
│   │   ├── methodology.md
│   │   └── templates/
│   ├── mitigations/
│   │   ├── strategies.md
│   │   └── controls.md
│   └── audit/
│       ├── risk_log.md
│       └── risk_snapshots/
│
├── security/                             # [PROPRIETARY] Security policies & models
│   ├── .gitkeep
│   ├── README.md
│   ├── framework.md
│   ├── policies/
│   │   ├── access_control.md
│   │   ├── data_protection.md
│   │   ├── cryptography.md
│   │   ├── network_security.md
│   │   ├── application_security.md
│   │   └── operational_security.md
│   ├── threat_model/
│   │   ├── methodology.md
│   │   ├── adversary_classes.md
│   │   ├── attack_surfaces.md
│   │   └── scenarios/
│   ├── controls/
│   │   ├── technical_controls.md
│   │   ├── administrative_controls.md
│   │   └── physical_controls.md
│   └── audit/
│       ├── security_log.md
│       └── security_snapshots/
│
├── src/                                  # Source implementation code
│   ├── telemetry/
│   ├── config/
│   └── main                              # Language-agnostic entry point placeholder
│
├── scripts/                              # Automation & operational scripts
│   ├── build/                            # Build and compilation scripts
│   ├── release/                          # Release preparation and packaging
│   ├── validate/                         # Structural and compliance validation
│   └── env/                              # Environment setup and teardown
│
├── tests/                                # Functional & unit test suites
│   ├── unit/
│   ├── integration/
│   └── fixtures/
│
├── assets/                               # Static media, schemas, static resources
│
├── versions/                             # Immutable project snapshots
│   └── README.md                         # Snapshot naming convention (see §7)
│
├── logs/                                 # Append-only audit logs
│   ├── issues/
│   │   └── postmortem.md
│   ├── CHANGELOG.md
│   └── critique_history.log
│
├── .gitignore                            # Version control exclusion rules
├── CONTRIBUTING.md
├── CODEOWNERS
├── NOTICE                                # Licence boundary declaration (see §8)
├── README.md
└── LICENSE                               # MIT Licence (public scope only — see §8)
```

### Directory Purpose References

| Directory | Purpose |
|---|---|
| `docs/` | Narrative specifications, research, operational requirements, high-level governance |
| `architecture/` | Formal C4 system structures, data models, interface definitions, evolutionary roadmaps |
| `risk/` | Internal risk registers, taxonomy, assessment frameworks, and mitigations *(proprietary)* |
| `security/` | Threat models, security control frameworks, and audit records *(proprietary)* |
| `src/` | Implementation code; language and entry point are project-specific |
| `scripts/` | Tooling for build, validation, release, and environment automation |
| `tests/` | Unit, integration, and fixture artefacts |
| `logs/` | Historical, append-only operational records and execution traces |
| `versions/` | Immutable snapshot archives for auditability and tag verification |

---

## 4. Structural Invariants

All projects must adhere to the following invariants:

- All directories defined in the schema are mandatory.
- Directory names are immutable.
- Top-level tracking files must exist, even if blank.
- Empty directories must contain a `.gitkeep` file to ensure they are tracked by version control.
- Append-only logs must never be rewritten or force-pushed over.
- Immutable snapshots must be stored in `versions/` following the convention defined in `versions/README.md`.
- The scaffold may be extended only by **adding** new branches, never by removing or renaming existing ones.
- The structure itself is part of the project's governance and must be treated as such.
- `src/` entry point filename and extension are determined at instantiation time and must be recorded in `architecture/system/context.md`.

---

## 5. Operational Usage Requirements

To maintain compliance with the framework:

- Populate templates as the project evolves.
- Leave unused branches empty — emptiness is an explicit signal, not an omission.
- Use `logs/` for historical, append-only tracking.
- Use `versions/` for archival snapshots, named per the convention in `versions/README.md`.
- Maintain governance documents in `docs/governance/`.
- Maintain research artefacts in `docs/research/`.
- Maintain operational artefacts in `docs/operations/`.
- Store reproducible tool scripts under `scripts/` in the appropriate sub-directory.
- All test artefacts belong under `tests/`; no test files should reside in `src/`.

---

## 6. Extension Policy

Projects may extend this scaffold only by:

- adding new directories under existing branches
- adding new documents or source modules
- adding new operational logs
- adding new execution scripts

Projects may **not**:

- rename directories
- remove directories
- relocate directories
- delete required top-level files
- rewrite append-only logs
- alter the canonical structure

---

## 7. Snapshot Convention (`versions/`)

Snapshots in `versions/` must follow this naming convention to be considered valid immutable records:

```
versions/
└── v{MAJOR}.{MINOR}.{PATCH}_{YYYY-MM-DD}/
    ├── snapshot.tar.gz       # Compressed archive of repo state at that tag
    └── manifest.md           # SHA-256 checksums and provenance notes
```

Snapshots must be created at every release tag. They must not be modified after creation. The `manifest.md` must include the corresponding Git tag and commit hash.

---

## 8. Licence & Confidentiality Dual-Bound

### Codebase Licensing

The non-proprietary codebase, infrastructure scripts, and standard documentation are licensed under the **MIT Licence** (see `LICENSE`).

### Proprietary Exclusion Boundary

The `risk/` and `security/` directories contain confidential, non-public governance and operational posture specifications. **The MIT Licence explicitly excludes these directories and their contents.**

The `NOTICE` file at the repository root states this boundary in plain terms and must be preserved in all distributions. It is the authoritative declaration of scope for both human readers and automated tooling.

### `.gitignore` Enforcement

The following rules must appear in `.gitignore` to prevent proprietary content leaking into public commits while retaining directory structure:

```gitignore
# Exclude proprietary contents; retain structure markers and READMEs
risk/*
!risk/.gitkeep
!risk/README.md

security/*
!security/.gitkeep
!security/README.md
```

### Pre-commit Hook (Recommended)

To prevent accidental push of proprietary content before `.gitignore` is applied, projects should install a pre-commit hook that blocks commits touching `risk/` or `security/` paths beyond `.gitkeep` and `README.md`. A reference hook is provided in `scripts/validate/`.

### Release Policy

When preparing a public release or external distribution:

- Retain the full directory structure using `.gitkeep` files.
- Omit or sanitise all proprietary risk logs, security models, and strategy details.
- Ensure no sensitive internal logs are included in published `versions/` snapshots or `logs/` distributions.
- Verify `NOTICE` is included in the distribution root.

---

## 9. NOTICE File

The `NOTICE` file must contain, at minimum:

```
This repository includes software licensed under the MIT Licence.
See LICENSE for terms.

The following directories are NOT covered by the MIT Licence and are
subject to project-specific confidentiality and intellectual property
constraints:

  risk/
  security/

These directories and their contents must not be redistributed,
published, or disclosed without explicit written authorisation.
```

---

## 10. Compliance Status

This project conforms to the **Universal Project Template Framework (v0.0.3)**.

Structural invariants must be preserved throughout the project's lifecycle. Any deviation must be justified, documented, and approved through the formal governance process defined in `docs/governance/constraints.md`.

---

