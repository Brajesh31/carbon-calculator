# 🗂️ Project Structure

## Current repository map

```text
carbon-calculator/
├── .github/
│   ├── ISSUE_TEMPLATE/       # Bug, feature, methodology forms
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── workflows/            # CI and link validation
├── docs/
│   ├── assets/                # Project SVG diagrams
│   ├── decisions/             # Architecture Decision Records
│   ├── templates/             # Reusable review and release templates
│   └── *.md                   # User, developer, and maintainer guides
├── app.py                     # Streamlit UI and calculations
├── README.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── SECURITY.md
├── SUPPORT.md
├── ROADMAP.md
├── CITATION.cff
└── LICENSE
```

## Responsibilities

| Path | Responsibility | Review expectation |
|---|---|---|
| `app.py` | Streamlit UI, inputs, factors, annualization, results | Units and assumptions explicit; add calculation tests when extracted |
| `.github/workflows/` | Repository automation | Least privilege and understandable failure output |
| `.github/ISSUE_TEMPLATE/` | Structured issue intake | No sensitive data collection |
| `docs/` | Project, methodology, and operations guides | Update with code behavior |
| `docs/assets/` | Diagrams | Keep diagrams aligned with implementation |
| `docs/templates/` | Repeatable project reviews | Keep templates usable and complete |
| Root policy files | Governance, support, security, licensing | Keep contact and project identity accurate |

## Possible future modular structure

This is a proposal, not the current code:

```text
future/
├── app.py
├── carbon_calculator/
│   ├── calculations.py
│   ├── factors.py
│   └── validation.py
├── tests/
│   ├── test_calculations.py
│   └── test_validation.py
├── data/
│   └── factor-sources/
└── requirements.txt
```

Only introduce this split when the responsibilities and interfaces are clear. Do not add empty files merely to inflate the tree.
