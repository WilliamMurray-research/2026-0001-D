# **README.md**

## **Project Template Framework**  
**Licence: CC‑BY‑SA‑4.0**

This repository defines the **canonical template framework** used across all projects. It contains multiple documents, specifications, and structural standards that together form a **complete operational scaffold**. Each project must instantiate this framework in full, preserving all directories, files, and structural invariants, even when individual branches contain no artefacts.

This repository is **not a project** and **not a single template**.  
It is a **collection of templates**, including:

- structural directory schema  
- documentation templates  
- operational record templates  
- accounting templates (`*.ods`, `*.odt`)  
- governance templates  
- architectural templates  
- versioning and changelog specifications  
- postmortem and critique templates  

The framework ensures that every project begins with the same **complete, predictable, auditable structure**.

---

## **Purpose**

The template framework exists to:

- enforce **uniformity** across all projects  
- ensure **every operational domain is represented**, even if unused  
- provide **ready‑to‑fill templates** for research, architecture, accounting, logging, and governance  
- maintain **structural invariants** across time and across projects  
- support **auditability**, **traceability**, and **reproducible reasoning**  
- eliminate ambiguity about what a project must contain

Null directories are intentional.  
They represent **unpopulated domains**, not omissions.

---

## **Contents of This Repository**

This repository includes multiple template documents, such as:

- **directory tree specification**  
- **documentation templates** (whitepapers, hypotheses, proofs, algorithms)  
- **operational templates** (compute logs, activity logs, procurement records)  
- **governance templates** (roles, constraints, architecture, motivation)  
- **versioning and changelog specifications**  
- **postmortem and critique templates**  
- **empty directory placeholders** for required project branches

Each template is designed to be copied into new projects **without modification to its structure**.

---

## **Structural Invariants**

Every project must:

- include **all directories** defined in the schema  
- include **all top‑level files**, even if blank  
- preserve directory names exactly  
- commit empty directories to version control  
- treat the structure as **immutable**, except for adding new branches  
- populate templates as the project evolves  
- maintain append‑only logs where specified  
- archive immutable snapshots in `versions/`

The structure itself is part of the governance model.

---

## **Licence**

All templates in this repository are licensed under:

**Creative Commons Attribution–ShareAlike 4.0 International (CC‑BY‑SA‑4.0)**

This ensures:

- templates remain open  
- derivative templates remain open  
- attribution is preserved  
- structural standards cannot be closed or privatized

---

## **Usage**

1. Clone this repository when starting a new project.  
2. Copy the entire structure into the new project.  
3. Do **not** remove or rename any directories or template files.  
4. Populate templates as needed.  
5. Leave unused branches empty — emptiness is meaningful.  
6. Use `versions/` for immutable snapshots.  
7. Use `logs/` for append‑only historical tracking.

This framework is designed for **operational consistency**, not convenience.

---

## **Status**

This repository is the **authoritative reference** for project structure and template documents.  
All future projects must conform to this framework.

---

*Contributions off: however, you are welcome to copy and adapt, in accordance with the requirements of the licence*
