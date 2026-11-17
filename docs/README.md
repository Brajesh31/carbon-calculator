# 📚 Documentation Hub

This folder contains the user, contributor, methodology, and maintainer documentation. It describes the current implementation and does not certify the factor data or outputs.

## 🧭 Reading paths

**App users:** [User guide](user-guide.md) → [Installation](installation.md) → [FAQ](faq.md) → [Methodology](methodology.md) → [Privacy](privacy.md).

**Contributors:** [Development](development.md) → [Architecture](architecture.md) → [Project structure](project-structure.md) → [Testing](testing.md) → [Accessibility](accessibility.md) → [Contributing](../CONTRIBUTING.md).

**Maintainers:** [Deployment](deployment.md) → [Operations runbook](operations-runbook.md) → [Security](security.md) → [Maintenance](maintenance.md) → [Release process](release-process.md).

## 📖 Full document index

| Document | Purpose |
|---|---|
| [architecture.md](architecture.md) | App structure and current formulas |
| [calculation-reference.md](calculation-reference.md) | Formula reference and unit caveats |
| [data-dictionary.md](data-dictionary.md) | Inputs and result fields |
| [methodology.md](methodology.md) | Factor provenance and validation |
| [assumptions-register.md](assumptions-register.md) | Open assumptions and resolution needs |
| [validation-plan.md](validation-plan.md) | Evidence required for trustworthy results |
| [glossary.md](glossary.md) | Project terminology |
| [project-structure.md](project-structure.md) | Repository responsibilities |
| [user-guide.md](user-guide.md) | How to operate the app |
| [installation.md](installation.md) | Environment setup |
| [development.md](development.md) | Contributor workflow |
| [testing.md](testing.md) | Automated and manual checks |
| [accessibility.md](accessibility.md) | Accessibility review |
| [privacy.md](privacy.md) | Data handling |
| [database.md](database.md) | Current no-database design |
| [api.md](api.md) | Current no-public-API design |
| [deployment.md](deployment.md) | Hosting |
| [operations-runbook.md](operations-runbook.md) | Operational checks and incidents |
| [security.md](security.md) | Project security notes |
| [faq.md](faq.md) | Common questions |
| [troubleshooting.md](troubleshooting.md) | Setup and runtime issues |
| [known-issues.md](known-issues.md) | Confirmed limitations |
| [maintenance.md](maintenance.md) | Routine maintenance |
| [release-process.md](release-process.md) | Release procedure |
| [content-guide.md](content-guide.md) | Responsible claims and wording |
| [design-system.md](design-system.md) | UI consistency principles |
| [performance.md](performance.md) | Performance considerations |
| [assets/](assets/README.md) | Diagrams |
| [decisions/](decisions/README.md) | Architecture decisions |
| [templates/](templates/README.md) | Reusable templates |

## 🗺️ System diagrams

![Application flow](assets/application-flow.svg)

![Calculation data flow](assets/calculation-data-flow.svg)

## 📌 Implementation snapshot

- Streamlit entry point: root `app.py`.
- Country selection: India only.
- Activity inputs: daily commute km, monthly electricity kWh, meals/day, weekly waste kg.
- Factors: hard-coded example values without provenance.
- Persistence, accounts, export, and public API: not implemented.
- Dependency lock and automated calculation tests: not present.
- CI: syntax and local Markdown link checks only.

Update this index when new guides are introduced or implementation changes.
