I need to keep the following structure:

/
├── docs/                                 
│   ├── research/
│   │   ├── whitepapers/
│   │   ├── hypotheses/
│   │   ├── proofs/
│   │   └── algorithms/
│   │
│   ├── governance/
│   │   # motivation, roles, constraints, architecture live here
│   │
│   ├── operations/
│   │   ├── procurement/
│   │   ├── compute/
│   │   └── records/
│   │
│   ├── motivation.md
│   ├── dsl-spec.md
│   ├── architecture.md
│   ├── telemetry.md
│   ├── rendering.md
│   ├── roles.md
│   ├── constraints.md
│   ├── versioning.md
│   ├── changelog-spec.md
│   └── roadmap.md
│
├── risk/                                 
│   ├── README.md
│   ├── register.md
│   ├── taxonomy.md
│   │
│   ├── assessment/
│   │   ├── methodology.md
│   │   └── templates/
│   │
│   ├── mitigations/
│   │   ├── strategies.md
│   │   └── controls.md
│   │
│   └── audit/
│       ├── risk_log.md
│       └── risk_snapshots/
│
├── security/                             
│   ├── README.md
│   ├── framework.md
│   │
│   ├── policies/
│   │   ├── access_control.md
│   │   ├── data_protection.md
│   │   ├── cryptography.md
│   │   ├── network_security.md
│   │   ├── application_security.md
│   │   └── operational_security.md
│   │
│   ├── threat_model/
│   │   ├── methodology.md
│   │   ├── adversary_classes.md
│   │   ├── attack_surfaces.md
│   │   └── scenarios/
│   │
│   ├── controls/
│   │   ├── technical_controls.md
│   │   ├── administrative_controls.md
│   │   └── physical_controls.md
│   │
│   └── audit/
│       ├── security_log.md
│       └── security_snapshots/
│
├── src/                                   # implementation domain
│   ├── telemetry/
│   │   ├── *.py
│   │   └── *.py
│   ├── config/
│   └── main.py
│
├── assets/
│   ├── *.md
│   └── *.md
│
├── tests/
│   ├── *.md
│   └── *.md
│
├── versions/                              # immutable project snapshots
│
├── logs/                                   # append-only audit logs
│   ├── issues/
│   │   └── postmortem.md
│   ├── CHANGELOG.md
│   └── critique_history.log
│
├── CONTRIBUTING.md
├── CODEOWNERS
├── README.md
└── LICENSE

Incorporate the following into the above:

[directory tree here]
