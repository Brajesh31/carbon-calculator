# Roadmap

This roadmap describes possible work for the prototype. It is a planning aid,
not a commitment to deliver features by a particular date. Priorities may change
as methodology sources, contributions, and maintenance capacity change.

## Current baseline

- One Streamlit page, implemented in `app.py`.
- India only, with four input categories and hard-coded example factors.
- No documented factor provenance, automated tests, or pinned dependency file.

## Proposed priorities

### 1. Make the estimate reproducible and explainable

- Identify credible, current sources for every factor and the comparison
  statistic, including date, geography, units, boundary, and license.
- Review the calculations with a qualified subject-matter reviewer before
  describing the results as validated.
- State the commute distance basis, travel days, household allocation, and
  treatment of diet and waste explicitly.
- Preserve unrounded intermediate values and define a consistent rounding
  policy; add independently checked examples and tests for the calculation
  functions.

### 2. Improve maintainability

- Separate calculation logic and source data from the Streamlit presentation.
- Declare a supported Python version and maintain a dependency file with
  reviewed, reproducible versions.
- Add automated checks for calculation behavior and basic application
  regressions.
- Document how factor updates are reviewed and attributed.

### 3. Improve usability and accessibility

- Explain each input and its time period beside the control.
- Make units and assumptions visible with each result.
- Review keyboard navigation, screen reader labels, responsive layout, and
  error handling.
- Allow users to understand the category breakdown and limitations without
  interpreting the estimate as a complete personal footprint.

### 4. Consider broader coverage

- Evaluate additional geographies or categories only after suitable factor
  sources and licensing have been reviewed.
- Keep regional, temporal, and methodological coverage visible so users do not
  compare estimates with incompatible boundaries.
- Consider an export or API only after a privacy and data-retention design is
  agreed and documented.

## How to propose a roadmap item

Open an issue describing the user need, proposed scope, data sources, validation
approach, and maintenance implications. Changes to factors require traceable
evidence; see [CONTRIBUTING.md](CONTRIBUTING.md). No target dates are set while
the calculation methodology remains unverified.
