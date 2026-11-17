# 🛣️ Product and Engineering Roadmap

This roadmap is a prioritization document, not a promise of delivery dates. Scientific validity and user trust take priority over adding more features.

## 🧭 Current baseline

- Single-page Streamlit application in `app.py`.
- India-only country selector.
- Four input categories: commute, electricity, diet, and waste.
- Hard-coded illustrative factors with no source records.
- No automated calculation tests or pinned dependency manifest.
- No persistent storage, authentication, export, or public API.

## 🔴 Priority 1: Establish a defensible methodology

- [ ] Identify credible sources for each factor.
- [ ] Record publication date, reporting year, geography, unit, boundary, gas basis, uncertainty, and license.
- [ ] Resolve the diet factor's dimensional inconsistency.
- [ ] Define commute distance semantics and commute frequency.
- [ ] Define waste composition and treatment assumptions.
- [ ] Replace or remove the uncited national comparison.
- [ ] Arrange subject-matter review before making accuracy claims.

**Exit condition:** each displayed category has a traceable factor and a reviewed calculation definition.

## 🟠 Priority 2: Make calculations independently testable

- [ ] Extract pure calculation functions from Streamlit UI code.
- [ ] Add validation for input ranges and units.
- [ ] Add independent test fixtures for zero, typical, and boundary cases.
- [ ] Define precision and rounding policy.
- [ ] Document error handling and calculation version.

**Exit condition:** core calculations can be tested without importing or launching the Streamlit interface.

## 🟡 Priority 3: Improve reproducibility and maintenance

- [ ] Declare supported Python version.
- [ ] Add a reviewed Streamlit dependency manifest.
- [ ] Add automated calculation tests to CI.
- [ ] Add dependency update and vulnerability review practices.
- [ ] Document a reproducible release procedure.

**Exit condition:** a clean environment can install known dependencies and run the same checks.

## 🟢 Priority 4: Improve user experience

- [ ] Clarify every input's unit and time basis.
- [ ] Add contextual explanations beside each category.
- [ ] Improve keyboard and screen-reader experience.
- [ ] Show source and assumptions alongside result values.
- [ ] Improve error and empty states.
- [ ] Add export only after privacy and retention decisions.

## 🔵 Priority 5: Carefully expand scope

- [ ] Evaluate additional countries only when region-appropriate factors are available.
- [ ] Evaluate additional categories with explicit boundaries and non-overlapping activity definitions.
- [ ] Consider historical comparisons only with versioned factors.
- [ ] Consider APIs or accounts only with a concrete user need and security/privacy design.

## 🚫 Explicit non-goals for the current prototype

Do not add a database, account system, payment integration, or complex infrastructure simply to make the repository appear larger. Do not claim complete or certified accounting while factor provenance remains unresolved.

## 📌 Propose roadmap work

Open an issue with user need, proposed scope, data sources, validation approach, privacy implications, and maintenance cost. Use the methodology-change template for factor updates.
