`2026-0001-D-read-001.md`

---

**CLASSIFICATION**: D

**Document Reference**: `2026-0001-D-read-001`
# Universal Project Template Framework
### Project Readme

**Type**: read
**Version**: 2.0

William Murray
Systems Architect
14 August 2026

**Status**: Draft

**Scope**: Defines the canonical project‑level scaffold used across the ecosystem, including the required directory tree, governance surfaces, structural invariants, and lifecycle phases that every project must inherit. Establishes the baseline structure for reproducible, governed, and ISO‑aligned project instantiation.

**Primary Model / Scheme**: 2026 Naming & Directory Model

---

## Overview

The **Universal Project Template Framework** is the canonical structural scaffold used across all projects in this ecosystem. It defines the directory tree, governance rules, naming conventions, and operational invariants that every project must inherit in full.

The framework exists to ensure that every project begins with a **correct**, **governed**, and **reproducible** structure.

---

## 1. Purpose

The framework operates across two lifecycle phases:

**Phase 1 — Standardisation (v1.x)**
Establish and lock the canonical directory tree, naming conventions, governance surfaces, mandatory documents, and structural invariants. Phase 1 is about correctness, clarity, and reproducibility.

**Phase 2 — Automation (v2.x)**
Once the structure is stable, introduce symbolic governance, pointer‑driven materialisation, deterministic ledger‑based generation, template dereferencing, and structural validation tooling. Phase 2 transforms the framework from a static scaffold into a hybrid symbolic–native architecture engine.

---

> **Author's Note — Standards Alignment**
>
> The justification above references ISO/IEC 15288 as the primary alignment standard. As this framework matures, additional standards warrant consideration. The ISO 8000 series (Data Quality) is a likely candidate — particularly ISO 8000‑1 (concepts and vocabulary) and ISO 8000‑61 (data quality management) — given the framework's emphasis on artefact integrity and provenance. The ISO 9000 series (Quality Management Systems) may also apply, particularly ISO 9001, where process repeatability and conformity assessment are concerns. Further alignment with ISO/IEC 12207 (Software Lifecycle Processes) is worth exploring as the automation phase matures. This note will be expanded and formalised as specific standards are confirmed and mapped to framework obligations.

## 2. Why This Framework Exists

The Project Template Framework establishes a **uniform, governed, and repeatable structural baseline** for all projects in the ecosystem. Its purpose aligns with the principles of ISO/IEC 15288, which emphasise consistent system life‑cycle processes, defined interfaces, and controlled artefact structures to ensure predictable behaviour across development, operation, and maintenance.

Standardising the repository structure provides the following ISO‑aligned benefits:

- **Consistency of artefact organisation** — all projects follow a common directory schema and document placement model, supporting predictable navigation and reducing structural ambiguity.
- **Repeatability of processes** — a stable scaffold enables repeatable instantiation, verification, and maintenance activities across the system life cycle.
- **Improved maintainability and traceability** — uniform structures simplify long‑term maintenance, facilitate provenance tracking, and support auditability of artefacts and decisions.
- **Interoperability of tooling and automation** — a consistent layout allows automated systems and validation pipelines to operate across projects without bespoke adaptation.
- **Reduction of cognitive load** — a predictable structure reduces the mental overhead of navigating or re‑deriving project layouts.
- **Increased operational efficiency** — standardisation eliminates redundant structural decision‑making, enabling clearer workflows and more efficient lifecycle execution.
- **Support for conformity assessment** — a defined structural baseline enables automated and manual compliance checks against governance and quality criteria.

Phase **v1.x** focuses on establishing and stabilising this standard. Phase **v2.x** will enforce and materialise it programmatically.

---

## 3. Relationship to the Ecosystem

This framework is the root from which all projects in the ecosystem are instantiated. Every project inherits its directory tree, governance surfaces, naming conventions, and structural invariants. Compliance with this framework is a precondition for project instantiation — not an optional alignment.

---

## 4. Licence

This repository uses a dual‑licensing model to balance two requirements: the framework itself must remain openly shareable and structurally standardised; template documents must be freely reusable in downstream projects without imposing ShareAlike inheritance.

### 4.1 Repository Licence — CC0-1.0

The framework itself — including its structure, governance rules, specifications, and non‑template documentation — is licensed under the **Creative Commons 1.0 Universal Licence (CC0-1.0)**. This covers structural standards, governance specifications, compliance rules, directory schema definitions, and explanatory documentation.

### 4.2 Template Documents — MIT Licence

All documents intended to be copied into downstream projects are licensed under the **MIT Licence**. This allows downstream projects to reuse template documents without inheriting CC0-1.0 obligations. Template documents include canonical directory placeholders, standardised `.md` files, structural governance stubs, and template artefacts used during project instantiation.

### 4.3 Proprietary Exclusion Boundary

As defined in the root `NOTICE` file, `risk/` and `security/` are not covered by either licence. They are governed by project‑specific confidentiality constraints and must not be redistributed.

### 4.4 Summary

| Component | Licence |
|---|---|
| Framework (structure, rules, specifications) | CC0-1.0 |
| Template documents copied into projects | MIT |
| Proprietary directories (`risk/`, `security/`) | Excluded / Confidential |

---
