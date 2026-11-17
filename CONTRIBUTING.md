# 🤝 Contributing to Personal Carbon Calculator

Thank you for considering a contribution. The most valuable improvements are those that make the application more transparent, correct, accessible, maintainable, and honest about uncertainty.

> [!IMPORTANT]
> This repository currently contains an educational Streamlit prototype with example emission factors. Do not introduce unsupported factors or present outputs as scientifically validated.

## 📑 Contents

- [Code of conduct](#-code-of-conduct)
- [Ways to contribute](#-ways-to-contribute)
- [Before opening an issue](#-before-opening-an-issue)
- [Development setup](#-development-setup)
- [Branch and commit conventions](#-branch-and-commit-conventions)
- [Calculation and data contributions](#-calculation-and-data-contributions)
- [Testing and review](#-testing-and-review)
- [Pull request checklist](#-pull-request-checklist)

## 🌱 Code of conduct

Participation is governed by [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md). Be respectful, assume good faith, and discuss technical disagreements using evidence.

## 💡 Ways to contribute

- Fix reproducible application defects.
- Improve input labels, units, validation, and result explanations.
- Improve documentation and diagrams.
- Add accessibility improvements.
- Extract calculation logic into testable functions.
- Add independently derived tests.
- Research and propose traceable emission-factor sources.
- Improve setup, deployment, and maintenance workflows.

## 🐛 Before opening an issue

1. Search existing issues and discussions.
2. Choose the relevant issue template.
3. Provide clear reproduction steps or a specific user problem.
4. Include OS, Python, Streamlit, and browser versions where relevant.
5. Use fictional sample values.
6. Remove credentials, private paths, and personal data from logs.

For a suspected vulnerability, do not create a public issue. Follow [SECURITY.md](SECURITY.md).

## 🧰 Development setup

```bash
git clone https://github.com/Brajesh31/carbon-calculator.git
cd carbon-calculator
python -m venv .venv
# Windows PowerShell: .venv\Scripts\Activate.ps1
# macOS/Linux: source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install streamlit
python -m streamlit run app.py
```

The project does not yet pin Python or Streamlit versions. Do not claim reproducible dependency installation until a tested dependency manifest is added.

## 🌿 Branch and commit conventions

Create focused branches from `main`, for example:

- `docs/methodology-guide`
- `fix/input-unit-labels`
- `feat/calculation-tests`
- `accessibility/result-announcement`

Use concise commit subjects with a category prefix:

- `docs: explain factor assumptions`
- `fix: clarify commute distance basis`
- `test: add annualization cases`
- `feat: add sourced factor catalog`

Keep each pull request focused. Avoid unrelated formatting changes.

## 🔬 Calculation and data contributions

Every new or changed factor must include:

1. Original publisher and source title.
2. Publication date and effective/reporting year.
3. Geographic coverage.
4. Activity definition and denominator.
5. Explicit numerator and denominator units.
6. System boundary and included lifecycle stages.
7. Gas basis, CO₂ or CO₂e, and conversion basis where applicable.
8. Allocation assumptions and conversion method.
9. Uncertainty and known limitations.
10. Reuse license and attribution requirements.

Include an independent hand calculation and representative test fixtures. A source URL alone is not enough. A factor from one country, grid region, year, or system boundary may not be suitable elsewhere.

Never quietly change the meaning of an existing input. For example, changing commute distance from daily total to one-way distance changes the result contract and must be explained in the UI and changelog.

## 🧪 Testing and review

The repository currently has syntax and documentation-link CI checks, but no automated scientific or calculation test suite.

At minimum:

- Run `python -m py_compile app.py`.
- Run `python -m streamlit run app.py` and complete the manual smoke test.
- Check zero, typical, and boundary values.
- Independently derive expected values for calculation changes.
- Inspect keyboard navigation and responsive behavior for UI changes.
- Review all affected documentation links.
- State exactly what was tested and what was not tested.

See [docs/testing.md](docs/testing.md) and use [the test report template](docs/templates/test-report-template.md).

## ✅ Pull request checklist

- [ ] The change solves a defined problem.
- [ ] Scope is focused and unrelated files are excluded.
- [ ] No secrets, private values, or generated local files are committed.
- [ ] Calculation units and annualization assumptions are explicit.
- [ ] Factor provenance and licensing are included where relevant.
- [ ] Tests or manual verification evidence are described.
- [ ] Accessibility has been reviewed for UI changes.
- [ ] README, docs, roadmap, and changelog are updated where needed.
- [ ] Known limitations are not hidden or overstated.

Use [the pull request template](.github/PULL_REQUEST_TEMPLATE.md). By submitting code or documentation, you confirm you have the right to contribute it under the repository's MIT License and that any included third-party material is properly licensed.
