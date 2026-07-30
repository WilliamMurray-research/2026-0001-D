# **scripts/validate/README.md**

## **Overview**

The `scripts/validate/` directory contains all structural‑validation and compliance‑automation tooling for the project.  
These tools enforce the canonical directory schema, generate required architectural artefacts, and ensure that the repository remains consistent with the Universal Project Template Framework (v0.0.3).

The primary component of this directory is the **deterministic ledger‑driven architecture generator**, implemented in Prolog.

---

## **Ledger‑Driven Architecture Generator**

### **Purpose**

The ledger engine automates the creation of required files in the `architecture/` domain.  
It uses a **double‑entry YAML ledger** stored in:

```
architecture/roadmap/build_plan.md
```

This ledger enumerates all required architectural artefacts and tracks their completion state (`pending` or `complete`).  
The Prolog engine consumes this ledger and generates missing artefacts deterministically.

---

## **Key Files**

### **1. `ledger_engine.pl`**

This Prolog module implements the full deterministic generation loop:

- loads the ledger  
- parses YAML  
- selects the next pending artefact  
- clears generation context  
- generates the artefact  
- updates the ledger  
- writes the ledger back to disk  
- repeats until all artefacts are complete  

It is fully deterministic, auditable, and safe to resume after interruption.

See **ledger-engine.md** for the complete predicate set.

---

### **2. `ledger-engine.md`**

A technical reference document containing:

- module declaration  
- predicate definitions  
- YAML extraction logic  
- generation loop  
- determinism guarantees  

This file serves as the canonical specification for the ledger engine.

---

## **Execution Model**

The engine is invoked by running the Prolog module:

```
swipl -s ledger_engine.pl -g run -t halt
```

Execution proceeds as follows:

1. The ledger is loaded from disk.  
2. The next `pending` artefact is identified.  
3. Generation context is cleared.  
4. The artefact is generated deterministically.  
5. The ledger is updated and rewritten.  
6. The loop continues until all artefacts are marked `complete`.

The engine halts automatically when no pending entries remain.

---

## **Governance Alignment**

This directory enforces several governance invariants:

- **Structural compliance**  
  Ensures all required architectural artefacts exist.

- **Deterministic generation**  
  Prevents drift and ensures reproducibility.

- **Auditability**  
  The ledger provides a historical record of generation.

- **Separation of concerns**  
  Generation tooling is isolated from architectural artefacts.

---

## **Extending the Validation Suite**

Additional validators may be added to this directory, such as:

- schema validators  
- directory‑structure checkers  
- pre‑commit guards  
- template consistency checkers  

All validators must preserve:

- determinism  
- auditability  
- non‑destructive operation  
- compliance with the canonical template

---

## **Directory Structure**

```
scripts/
└── validate/
    ├── ledger_engine.pl
    ├── ledger-engine.md
    ├── README.md
    └── (optional additional validators)
```

---



---

If you want, I can also generate a **governance placement note** or a **validator suite index** to accompany this README.
