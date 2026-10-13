# Development

This guide describes a small, repeatable workflow for changes to the current
Streamlit prototype. Start with the repository [README](../README.md),
[contribution rules](../CONTRIBUTING.md), and [architecture](architecture.md).

## Repository layout

```text
app.py                 Streamlit controls, factors, conversions, and output
docs/                  Project guides
README.md              Project overview and local quick start
```

There is currently no package/module layout, dependency manifest, test suite,
formatter configuration, or CI workflow in the repository. The app and its
calculation logic are in one file. Keep changes focused and avoid introducing
new tooling without documenting how maintainers should use it.

## Set up a worktree

1. Fork the repository or use a branch in your authorized clone.
2. Fetch the latest `main` branch and create a focused topic branch.
3. Follow [installation.md](installation.md) to create `.venv` and install
   Streamlit.
4. Run the app from the repository root with `streamlit run app.py` when
   changing application behavior.

Do not commit `.venv`, Python caches, local environment files, Streamlit
secrets, private inputs, or editor-specific local settings. The repository
`.gitignore` excludes common generated files and local secrets.

## Working with calculations

The present factors are fixed example values in `app.py`; they are not
validated references. Before changing or adding a factor, provide its source,
publication or effective date, geography, unit, boundary, conversion method,
and redistribution license. Explain the assumptions for each input period and
annualization. Keep those details near the data and in the documentation so
future readers can trace them.

The current app rounds each category to two decimal tonnes before summing the
total. A change to rounding, units, or annualization changes user-visible
results and should explain that impact. Separate arithmetic from the interface
if the calculation grows; independently verifiable examples and automated
checks should accompany calculation logic when such a suite is introduced.

## Review checklist

- Does the change match the stated input units and time period?
- Are factors traceable, licensed for use, and appropriate to the geography and
  time period?
- Are assumptions and limitations visible in the interface or docs?
- Does the page remain understandable with zero and boundary values?
- Are errors and missing configuration described clearly?
- Were affected guides, README details, and changelog notes updated?
- Does the diff exclude generated files, credentials, and personal data?

The current repository has no automated test command or lint command. Do not
assume CI validates changes; explain the review or manual checks performed in
the pull request. For a broader proposal or new factor coverage, first open an
issue with the method and sources as described in [CONTRIBUTING.md](../CONTRIBUTING.md).

## Pull requests

Open a pull request against `main`. Describe the user problem, the implementation
and calculation assumptions, the sources and licenses for data, the checks
performed, and any known limitations. Include screenshots for substantial
interface changes and avoid including sensitive user or deployment data.
