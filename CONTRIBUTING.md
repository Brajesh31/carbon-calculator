# Contributing

Thank you for considering a contribution to Personal Carbon Calculator. Contributions should improve correctness, transparency, accessibility, usability, or documentation. Emission calculations require traceable sources and explicit units; avoid presenting example values as measured facts.

## Before starting

1. Read README.md and the guides in docs.
2. Check existing issues for related reports or proposals.
3. Open an issue before large changes so the scope and method can be discussed.
4. Do not commit personal data, API keys, private deployment settings, or datasets without clear redistribution rights.

The project is maintained by Brajesh Kumar, GitHub account @brajesh31.

## Report a defect

Open a GitHub issue and include:

- A concise summary and reproduction steps.
- Expected and observed behavior.
- Python and Streamlit versions and operating system.
- The inputs and resulting output, using non-sensitive example values.
- Relevant traceback text with local paths and secrets removed.

Use SECURITY.md for vulnerability reports instead of a public issue.

## Propose a calculation or dataset change

Include the original source and its publication date, geography, reporting period, factor units, system boundary, and conversion method. Explain assumptions such as commute days, return journeys, household allocation, diet definitions, or waste disposal. Include attribution and license information for third-party data.

Do not claim an estimate is accurate or comparable until the methodology has been reviewed. A factor for one country, grid, year, or boundary may not apply elsewhere.

## Prepare a change

1. Fork the repository and create a focused branch from main.
2. Keep changes small and explain the user impact.
3. Preserve explicit units and document how inputs are annualized.
4. Keep external data sources and their attribution close to the factor definitions and in docs.
5. Update documentation when inputs, units, formulas, regions, dependencies, or deployment behavior change.
6. Do not commit virtual environments, bytecode, Streamlit secrets, generated output, or private input data.
7. If adding Python dependencies, declare and pin them in a maintained dependency file after validating the chosen versions.

## Review your change

There is no automated test suite or dependency lockfile in the repository. At minimum, install the declared dependencies in an isolated environment and run the app locally:

    streamlit run app.py

Check representative minimum, typical, and maximum inputs; verify units and annual conversions independently; review output after changing a widget; and inspect terminal/browser errors. Describe what you checked in the pull request. Add automated tests when extracting calculation logic into functions or adding more categories.

## Commit and pull request

Use a concise commit subject such as:

- docs: explain calculation assumptions
- fix: clarify commute distance basis
- feat: add sourced electricity factor

Open a pull request against main with the reason, formula or interface change, sources, validation performed, and remaining assumptions. Include a screenshot for substantial visual changes.

## License and conduct

By submitting a contribution, you agree that it may be distributed under the repository's MIT License. You confirm that you have the right to submit all code and data and include required attribution. Follow CODE_OF_CONDUCT.md.
