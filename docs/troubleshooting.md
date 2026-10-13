# Troubleshooting

## `streamlit` is not recognized or not found

The command may not be installed in the active Python environment. From the
repository root, activate `.venv` as described in [installation.md](installation.md),
then run:

```sh
python -m pip install streamlit
python -m streamlit run app.py
```

Using `python -m streamlit` helps ensure Streamlit runs from the same Python
environment where it was installed. On Windows, use the `.venv\Scripts\python.exe`
commands in the installation guide if PowerShell activation is unavailable.

## Python cannot open `app.py`

Change to the cloned repository's root directory before starting Streamlit. The
file is named `app.py` and is currently at the repository root. Confirm it is
present with `Get-ChildItem app.py` in PowerShell or `ls app.py` on macOS/Linux.

## The page is blank or says the address cannot be reached

- Read the terminal output from `streamlit run app.py`; it prints the local URL
  and any Python traceback.
- Open the exact local URL printed by Streamlit, typically
  `http://localhost:8501`.
- If the default port is occupied, stop another local Streamlit process or
  choose another port, for example `streamlit run app.py --server.port 8502`.
- If the app is hosted, check the provider's build and runtime logs, configured
  branch, entrypoint (`app.py`), and expected port settings.

## The result is not visible

The result section is shown only for the run where **Calculate CO2 Emissions**
is clicked. Adjust the controls and click the button again to recalculate. The
current page does not display a continuously updating result before the button
is clicked.

## An estimate looks unexpectedly low or high

Check that each value is entered in the stated period and unit: daily commute
kilometres, monthly electricity kWh, weekly waste kilograms, and meals per day.
The source annualizes daily values using 365 days, monthly electricity using 12
months, and weekly waste using 52 weeks. It then multiplies by fixed example
factors and converts to tonnes. Inspect [architecture.md](architecture.md) for
the implemented formulas.

The factors have no documented source or validation, the commute basis is not
defined, and the diet factor's unit comment is inconsistent. A plausible
looking output does not establish that the result is accurate. Do not use the
estimate for formal reporting or consequential decisions.

## Deployment uses a different dependency than local development

The repository currently has no dependency manifest or Streamlit version pin.
Different environments may therefore install different versions. Review the
deployment logs and add a tested, pinned dependency file before relying on
repeatable deployment. See [deployment.md](deployment.md).

## Reporting an unresolved issue

Open a GitHub issue with steps to reproduce, expected and observed behavior,
operating system, Python and Streamlit versions, and relevant sanitized logs.
Do not include names, private measurements, tokens, passwords, or other
sensitive information. For a suspected vulnerability, use the private process
in [SECURITY.md](../SECURITY.md), not a public issue.
