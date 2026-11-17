# 📋 Changelog

All notable repository and application changes are recorded here. The project has not yet established a tagged release cadence. Dates describe repository changes, not validation of the calculation methodology.

## [Unreleased]

### 📚 Documentation and repository structure

- Expanded the root README with a detailed overview, feature matrix, setup, workflow, repository tree, caveats, and contribution guidance.
- Added a documentation hub and guides for methodology, privacy, accessibility, testing, project structure, maintenance, releases, content claims, performance, and design principles.
- Added SVG application and calculation flow diagrams.
- Added architecture decision records and reusable documentation templates.
- Added issue forms for bugs, feature requests, and methodology changes.
- Added a detailed pull request template and repository quality workflows.
- Removed the hourly README timestamp workflow to avoid unnecessary automated commits.

### ⚠️ Known baseline limitations

- The app remains a single-file Streamlit prototype.
- Factors remain hard-coded examples without provenance or validation.
- No automated calculation test suite or pinned dependency manifest exists.
- No database, authentication, export, or public application API exists.
- The application calculation behavior has not been scientifically validated by this documentation work.

## Baseline

The current source collects daily commute distance, monthly electricity consumption, meals per day, and weekly waste. It annualizes the values, multiplies by example factors, converts kilograms to tonnes, and displays a category breakdown and total after a button click.
